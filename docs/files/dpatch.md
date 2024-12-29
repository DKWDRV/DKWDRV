## DPATCH Values
For a small list of specific games Sony has specificed ppc code provided with DECKARD's DPATCH bios entry file which patched the default DECKARD file. 
Patches are applied for a specific list of games. 
PS1DRV applies them before even uncompressing. OSDSYS sends the game title code as param to the driver. Due to a bug this small list of games was not playable with PS1VmodeNeg or Ulaunchelf loading. This is because these apps all send full PSX EXE path together with "cdrom" instead of just sending only the title as it should be. DKWDRV correctly applies these patches just like the original driver.

All DECKARD files are supposed to be the same (other than the timestamp). DPATCH was the mechanism designed to apply patches to the original files. Despite that all DPATCH files are the same in all version. This file is raw PPC code located at ROM address FFFFD000. 

Although it could had been used for anything it seems to be used only on PS1 games. A sif register is used to set the DPATCH value. 

0x1000F220 SIF register is written zero by PS1DRV. If the game code is found in compability list then it will write the DPATCH index to it. 
PS1 mode reset jumps to MIPS reset vector and before jumping to TBIN (PS1 bios in PS2) checks 0xBD000020 (which is reg 0x1000F220 from EE side) for any value different than zero.
It then writes to (0x2000000 + value) address the value zero and clears the 0xBD000020 reg by writing the same value back. 
PPC code triggers an exception because memory 0x2000000 is not mapped. The exception handler specificically checks if the address of the instruction trying to write is from the ROM itself by checking for instruction which tried to write there is in 0x1FC00000 ROM memory range or not. This was done on purpose, so only ROM code can intentionally trigger DPATCHES and not some IRX module loaded in RAM.

If it is from ROM and it tries to write to 0x2000000 base address then it executes func_0xffffd000(addr & 0x1F). This is DPATCH sub which simply jumps to a sub from a LUT of 32 entries. Entry with index zero does nothing so only the rest are used. Up to 7 patches are found, the rest do nothing.


| Game Code | DECKARD PATCH Sub | Game Name |
| :---:         |     :---:      |          :---: |
|SCPS101.01|1|FORMULA ONE 99|
|SLUS_008.70|1|FORMULA ONE 99|
|SLUS_011.34|2|FORMULA ONE 2000|
|SCUS_942.33|3|MLB 99|
|SCES_019.79|1|FORMULA ONE 99|
|SCES_022.22|1|FORMULA ONE 99|
|SCES_027.77|2|FORMULA ONE 2000|
|SCES_034.23|4|FORMULA ONE 2001|
|SCES_034.24|4|FORMULA ONE 2001|
|SLES_009.10|5|ROAD RASH 3D|
|SLES_025.52|5|ROAD RASH - JAILBREAK|
|SLUS_005.24|5|ROAD RASH 3D|
|SLUS_010.53|5|ROAD RASH - JAILBREAK|
|SLPS_003.50|6|SAMURAI SPIRITS - ZANKUROU MUSOUDEN|
|SLPS_910.24|6|SAMURAI SPIRITS - ZANKUROU MUSOUDEN [PLAYSTATION THE BEST]|
|SCUS_942.06|6|SAMURAI SHOWDOWN III - BLADES OF BLOOD|
|SCES_005.63|6|SAMURAI SHOWDOWN III - BLADES OF BLOOD|
|SLES_041.20|7|XS JUNIOR LEAGUE SOCCER|
|SCES_034.04|4|FORMULA ONE 2001|
|slus_015.20|7|XS JUNIOR LEAGUE SOCCER|
|SLES_009.44|7|ONE|
|SLUS_006.65|7|COMMAND & CONQUER - RED ALERT - RETALIATION [ DISC 1 ]|
|SLUS_006.67|7|COMMAND & CONQUER - RED ALERT - RETALIATION [ DISC 2 ]|

<br>

All found DPATCH functions patch the RAM memory of PPC running code and flush the data/instruction cache.
<br>

| DECKARD PATCH Sub | Operation | Change | Notes |
| :---:         |     :---:      |          :---: |         :---: |
|0|||Does nothing.|
|1|<code>*(u32*)0xA04778 = 0x4BFFD0C6</code><br><code>*(u32*)0xA097A0 = 0x54A3F0BE</code>|<code>ba        loc_FFFFD0C4</code><br><code>srwi r3, r5, 1</code> to <code>srwi r3, r5, 2</code>|Patch interpreter loop section to custom DPATCH function.<br>Patch PGPU dma event cycles calculation.|
|2|<code>*(u32*)0xA04778 = 0x4BFFD222</code>|<code>ba        loc_FFFFD220</code>|Patch interpreter loop section to custom DPATCH function.
|3|<code>*(u32*)0xA04778 = 0x4BFFD31E</code>|<code>ba        loc_FFFFD31C</code>|Patch interpreter loop section to custom DPATCH function.
|4|<code>*(u32*)0xA04778 = 0x4BFFD3DE</code>|<code>ba        loc_FFFFD3DC</code>|Patch interpreter loop section to custom DPATCH function.
|5|<code>*(u32*)0xA03AE0 = 0x4BFFD4DE</code><br><code>*(u32*)0xA03350 = 0x4BFFD556</code>|change custom APU instr<br><code>ba        loc_FFFFD554</code>|<br>Patch interpreter loop section to custom DPATCH function.|
|6|<code>*(*u16*)0xa047b6 = 0xffb4</code>|<code>bso       cr6, unk_A03540</code><br>to<br><code>bso       cr6, unk_A04768</code>|
|7|<code>*(u32*)0x00a0b1b0 = 0x4b5f243d</code>|<code>bl       sub_FFFFD5EC</code>| Jump to custom Sio0CtrlWrite handler in DPATCH code.|

