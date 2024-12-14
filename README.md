

# DKWDRV
[![Github All Releases](https://img.shields.io/github/downloads/DKWDRV/DKWDRV/total.svg)]()
## Unified Single PS1DRV Replacement, compatible with mostly all PS2 models. 

DKWDRV is a replacement for the original PS1DRV of Playstation 2 consoles. 
The original driver was heavily limited in features (sometimes on purpose and sometimes not) making user experience a real hassle.
DKWDRV aims at overcoming this issues and making a much better gaming experience.
Built from scratch by reversing both types of original drivers and merging them into one single unified driver. This project is not related in any way with any existing PS1 related PS2 homebrews out there.

At the moment the project can be considered BETA and many issues can come due to the big number of hardware and game differences.
Users are welcome to submit issues or request features.

With time more details and documentation about PS1 operation in PS2 mode will be provided.


<br>



<br>

## Features

- USB game loading(beta). DECKARD consoles only.
- Almost exact emulation behaviour as the original drivers.
- Single file for both types of consoles(PGIF and DECKARD) with a reasonable final compressed size of around 70-80kb. PGIF drivers were alone ~120kb and DECKARD compressed drivers were ~180kb. 
- Internal separate game config database for both PGIF and DECKARD. All games from all drivers are included and automatically applied. Previously users would get wrong experience with out of region discs because PGIF drivers only had configs for the console version and DECKARD drivers have all region but again look for title code only in the table of game configs for console region.
- Automatic PS1 video mode change. Another limitation of the original drivers was using one single mode sometimes making game appear too fast or too slow and off screen. PS1VmodeNeg was a good progress but still limited. Now the driver will auto adjust to whatever video mode the game requests. Users can also force a mode on purpose. This solves many problems for users of MechaPwn and Tonyhax.
- PS2HDMI Fix for PS2 HDMI dongles. Despite being called this way it can be used for all cases when component fails to display anything right after PS1 boot logo or right after it.
- Fix for GPU GP1 reset used a lot in PS1 homebrews making them stop working in PS2. Such as [this](http://www.psxdev.net/forum/viewtopic.php?t=401) and many others.
- Dithering can be forced enabled or disabled. No more need for game patches and cheats.
- Screen offsets are also an option too.
- GPU color banding can be also controlled. PS1DRV was applying it on sprites only. More information [here](http://www.psxdev.net/forum/viewtopic.php?t=1035).
- Automatic PS1 license and logo check patching for DECKARD consoles. At the moment is not possible to patch PGIF consoles but perhaps later. PGIF users will still get a warning for such cases so they can know why all they get is a blackscreen. It is still possible to proceed in case the user has some other form of booting games(modchip, swapping, etc).
- All PS1 config options can be tweaked and saved. 
- More Filtering values possible for Polygon sharpening.
- Filtering option for sprites. The original driver would only apply sharpening (if selected from the OSDSYS menu) to only textured polygons. Results vary from game to game.
- Crackto Fix for many patches and trainers/crackto and also homebrews being offscreen.
- Cheats can be applied on DECKARD consoles only. See Cheats section for more.
- Custom button combos while can ingame can perfrom specific actions. DECKARD consoles only.
- Ability to swap X and O buttons. So when X is pressed the game thinks that it's O and vice-versa. Can be used on all games and homebrew. Useful for users who play Japanese games. DECKARD consoles only.
- Automatic Libcrypt patching for Libcrypt protected games by setting the final key to Cop registers. All magic words from [gamedb.py](https://github.com/sahlberg/pop-fe/blob/master/gamedb.py) of [sahlberg pop-fe](https://github.com/sahlberg/pop-fe).
- Users can also control VERSTR letter to make PS1 games think they are running on different region. May be useful for certain games or homebrews. DECKARD consoles only.
- Analog mapping for games that do not use it like Crash Bandicoot 1 etc. Users can apply specify deadzones for the analog.
- Useful for PCSX2 users who have only newer DECKARD bios and emulation won't work for them. Can simply launch the elf directly.
- Useful for TOOL users with must have switches and properly flashed rom.
- Many many bugfixes to original code especially those related to interrupts.


A full list of internal configs with proper documentation will be coming in the future.


<br>

## Usage
Download the lastest release from the [release](https://github.com/DKWDRV/DKWDRV/releases/latest) page.
Simple run the ELF files in any way you can. Make sure that you have a valid PS1 disc inserted prior to running.
Users must configure options for the fixes and features that they want. If they want to save changes they have to use the Save Game Config option in the menu. Selection Run will boot into the game.
Most options are easy to understand. Better naming and documentation coming soon.
Do note that modchip CAN and WILL impact the boot sometimes and you might get black screens.
Report issues in Github issues and remember to post AS MUCH INFO AS POSSIBLE.
Your model, DKWDRV version, type of media, id, ids, redump links, modchip everything you find relevant.
"Does not work" and "Black screen" are horrible reports!
Remember to also note the information in the "INFO" section of DKWDRV. Make sure to always use the latest version.


<br>
<br>


## USB Loading 

The project has been delayed due to insane technical difficulties in implementing the emulation code and especially debugging. 

<strike>This is stage 1 of releasing. Since it is impossible to test many games we are releasing in the hope to gather bug reports and improve the current state. After this stage we will implement XA/CDDA audio. A POC for it has proven to be successful so far.</strike>

Thanks to the amazing support of the community with the issues we have reached stage 2 where with 1.7.6 emulation should be heavily improved. There are still some edge cases waiting to be solved. At the moment issues regarding regressions are welcomed.


<details>
  <summary>Usage</summary>

<br>

Create a folder called "DKWDRV" in root of USB.
Inside it create a folder named "BIN".
Inside "BIN" create folder for each game and inside each game put the bin/cue files (merged) (see Limitations for more info).
You can also place CHEATS.TXT for the game.
Example:

```
USB
    DKWDRV
        BIN
            Crash Bandicoot
                Crash Bandicoot.bin
                Crash Bandicoot.cue

            Crash Bandicoot 2 - Cortex Strikes Back
                Crash Bandicoot 2 - Cortex Strikes Back.bin
                Crash Bandicoot 2 - Cortex Strikes Back.cue
                CHEATS.TXT

            ....    
```

Run DKWDRV.ELF from [release](https://github.com/DKWDRV/DKWDRV/releases/latest) and select "Select USB Game".
Pressing [] on a game allows you to selection options for it. 
The first time you run a game it will try to create a config for it by analyzing the game files.

</details>


<details>
  <summary>Limitations</summary>

<br>

- USB must be FAT32.
- All .bin tracks must be merged. Use IsoBuster or CDMage.
- .cue file must be provided and the .bin name must match the main binary file.
- All bin dumps must be 2352 sector sizes.
- All games must be defragemented! You can still proceed but be warned it can crash anytime.
- No XA/CDDA sounds effect yet. That is a WIP and it will be added in the future. This means that BMG, FMV audio
and other SFX might be missing from the game.
- No disc swapping implemented yet but planned and doable.

</details>


<details>
  <summary>Troubleshooting</summary>

<br>

- Remember that this version is VERY BETA. It is still WIP.
- Try different USB.
- Try USB directly (no usb hub or extra usb type device connected at same time).
- Verify game structure and installation is correct.
- Verify game is defragmented.
- Play around with game options, setting VERSTR to game default region is a good idea.
- XA/CDDA missing is a known issue, they will be released later on. You can create report issues on here for different games.
- Many subq protected games run fine but there might be some rares cases when magic word patching won't work well. See if you can patch the game in that case.
- Same games load quickly because seek times are set to minimal. To be updated in the future.
- If you use a HDMI adapter remember to toggle the setting in general VIDEO options. Sometimes the adapter and TV can get unsynced between video mode changes causing a NO SIGNAL in TV. Reset reset the adapter.


</details>

<br>

## Future Features Planned (no ETA)
- Higher videomodes ingame (investigating)
- XA/CDDA Audio (partly done)
- Disc Swap (partly done)
- VMC from USB
- IGR
- Custom BIOS
- ....


<br>

## Changelog

<details>
  <summary>1.7.6</summary>
    
<br>

- Improved USB reset and detection code.
- Improved error handling display information.
- USB - Play cmd bugfixes (Final Doom, AZITO, Mortal Kimbar 3 ingame, games using CCDA tracks)
- USB - Antipiracy check fixes (Um Jammer Lammy, Saru Get You, games using APV1/2 protection)
- USB - Major DMA changes (fixes FMV freeze, black screens, impacts all games)
</details>

<details>
  <summary>1.7.5</summary>

<br>

- USB cmd implemented. Fixed a lot of games using ReadToc cmd. (Rockman Complete Works etc....)
</details>

<details>
  <summary>1.7.4</summary>

<br>

- BETA USB Support
- Misc Bug Fixes
</details>

<details>
    <summary>1.7.2</summary>

<br>

- Fixed an IOP init bug which might have impacted boot up on some systems.
- Allows config saving for PSX.EXE games with no SYSTEM.CNF
- Memory card 1 or 2 can be selected for saving game config.
- Config and cheats are now searched in both slots instead of just first slot.
- AutoDiag is enabled if found in config.
- Added and improved documentation.
- User warning if disc not valid.
- Controller input from both slots.
- Limited mecha config to possible values and added some info for them.
- Fixed more minor bugs.

</details>

<details>
    <summary>1.7.1</summary>

<br>

- Fixed a race condition causing crash on game boot in some PS2 models.
- Added Sprite Filtering option.
- Libcrypt patching. DECKARD ONLY
- Fixed some small bugs.
</details>

## User Configs
<details>
  <summary>Show detailed info for user configs</summary>

<br>

All user per game configs are stored in the memory card. Each game will create it's own save which can be managed from OSDSYS too in case you want to copy or delete it.
The reason for having a save per game and not all configs inside a main save dir is because with many files OSDSYS won't copy or delete the main file.
The main file will have a formatted game copy. For example Crash Bandicoot will have SCUS-94900 as game id but the save folder will be "SCUS94900".
Inside it there will be two possible files, CONFIG.TXT and CHEATS.TXT for cheats.
An import other case is the problem of games with no SYSTEM.CNF which only have PSX.EXE or that do indeed have SYSTEM.CNF but BOOT filename is still PSX.EXE.
Since many games share the same id for this games the save name will be PSXyyyyyyyy where yyyyyy is hex value for CRC32 of PSX.exe from that game. This is the only proper way to be able to handler that many PSX.EXE titles out there where many are homebrews.
Example of a memory card listing
```
mc0:
    SCUS147895 (folder for regular game)
              CONFIG.TXT
              CHEATS.TXT
    PSX1DBA2151 (folder for PSX.EXE game)
              CONFIG.TXT
              CHEATS.TXT
```
In order to create the folder automatically you need to run Save Game config at least once.
If many games with PSX.EXE and unsure which is which you can find it out by the hex value of CRC32 in the filename. Extract PSX.EXE from your disc in a PC and calculate it's CRC32. 7zip right click context menu would do the job just fine. Select CRC SHA and in submenu CRC32.
</details>

<br>

## DECKARD button combos
For DECKARD consoles users can press specific combos even while ingame.
<details>
  <summary>Show button combos</summary>

<br>

- L1 + L2 + R1 + R2  + Any DPAD will live adjust screen offsets.
- L1 + L2 + R1 + R2  + SELECT will toggle game cheats. Sometimes it may be useful to have a cheat active only at certain parts of the game. The combo can disable and enables all applied cheats.
- L1 + L2 + R1 + R2  + TRIANGLE Will toggle Polygon MMAG filtering 2. Just 0 and 1
- L1 + L2 + R1 + R2  + CROSS(X) Will toggle Polygon MMIN filtering. Up to 7 values can be used. Once 7 is reached it's wraps back to 0.
- L1 + L2 + R1 + R2  + SQUARE Will toggle Sprite MMAG filtering 2. Just 0 and 1. Results vary. Original drivers was never applying filtering to sprites.
- L1 + L2 + R1 + R2  + CIRCLE Will toggle Sprite MMIN filtering. Up to 7 values can be used. Once 7 is reached it's wraps back to 0. Results vary. Original drivers was never applying filtering to sprites.
</details>

<br>

## Cheats
<details>
  <summary>Show detailed cheats info</summary>

<br>

For DECKARD consoles only cheats can be applied. Cheats must be placed inside memory folder with the game name. Users can save general config to automatically create this folder. At the root of the folder a CHEATS.TXT must be present for cheats to show. Refer to "User Configs" for more info on how to find the save folder.
The desired cheats must be enabled from the menu every time prior to booting the game.
Cheats are applied every vblank.
An example of a cheat file:
```sh
#Infinite Lives "Boulders" Stage
8009E584 6300
#Infinite Lives "Castle Machinery" Stage
8009E88C 6300
#Infinite Lives "Cortex Power" Stage
8009E77C 6300
....
```

Supported cheat types:
| Code(Hex) | Type([Duckstation Naming](https://github.com/stenzek/duckstation) ) |
| :---:  |  :---:  |
|00 |CodeNop |
|30 |ConstantWrite8  |
|80 |ConstantWrite16  |
|90 |ExtConstantWrite32  |
|31 |ExtConstantBitSet8  |
|81 |ExtConstantBitSet16  |
|91 |ExtConstantBitSet32  |
|32 |ExtConstantBitClear8 |
|82 |ExtConstantBitClear16  |
|92 |ExtConstantBitClear32  |
|60 |ExtIncrement32  |
|61 |ExtDecrement32  |
|10 |Increment16  |
|11 |Decrement16  |
|20 |Increment8  |
|21 |Decrement8  |
|A0 |ExtCompareEqual32  |
|A1 |ExtCompareNotEqual32  |
|A2 |ExtCompareLess32 |
|A3 |ExtCompareGreater32 |
|A6 |ExtConstantWriteIfMatch16  |
|A7 |ExtConstantWriteIfMatchWithRestore16  |
|D0 |CompareEqual16  |
|D1 |CompareNotEqual16 |
|D3 |CompareLess16  |
|D3 |CompareGreater16 |
|E0|CompareEqual8  |
|E1 |CompareNotEqual8  |
|E2 |CompareLess8  |
|E3 |CompareGreater8  |
|50 |Slide  |
|53 |ExtImprovedSlide  |
|C2 |MemoryCopy |

</details>

<br>

## Supporting the project
If you really happen to like what we have done here, and you are so amazed from you it you can help us move forward faster. 
There are several this can be done:

<br>

- Donations (some people offered donations before but now we have a way for them)
    - [![patreon](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/DKWDRV)
    - A BIG THANK YOU goes to our current supporters (listed alphabetically, past and current ones):
      - Beandip
      - Manel
      - emoji de fuego
      - gaopringao
      - JonasK
        
- Testing and documenting problematic games and features. There are so much games out there it's impossible to test everything.
  
<br>

## Technical documentation
Some initial documentation is now online. You can view it [here](https://github.com/DKWDRV/DKWDRV/blob/main/docs/tech_docs.md).
With time it will be updated so make sure to check regularly.

## Old Repo
https://github.com/wisi-w/DKWDRV/



