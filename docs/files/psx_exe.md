## PSX.EXE Games
PS1 expects a SYSTEM.CNF or PSX.EXE in root of disc to find the executable to load. If the BOOT param in SYSTEM.CNF is PSX.EXE or there is no SYSTEM.CNF and only PSX.EXE is left another way is needed for identify the game id. PS1DRV would search for a specific unique file in disc to see if it is present.

The following list is from DECKARD PS1DRV which is the most updated one. PGIF models have weird different drivers with very limited searching.

| File | Game ID | Game Name |
| :---:  |  :---:  |  :---: |
|cdrom0:\\LADIES.DA;1|SLPS_000.23|CYBER SLED|
|cdrom0:\\OP\\A4OP.STR;1|SLPS_000.04|A IV EVOLUTION|
|cdrom0:\\NP_ISHI0.SPL;1|SLPS_001.13|SOTSUGYOU II - NEO GENERATION|
|cdrom0:\\G9_100L.DA;1|SLPS_000.38|NICHIBUTSU MAHJONG|
|cdrom0:\\PSXMYST\\MYST.CCS;1|SLPS_000.24|MYST|
|cdrom0:\\BOZU\\BG0B.BIN;1|SLPS_001.04|GOUKETSUJI ICHIZOKU 2 - CHOTTODAKE SAIKYOU DENSETSU|
|cdrom0:\\PDATA\\ATKDAT.CFL;1|SCPS_100.02|VICTORY ZONE|
|cdrom0:\\TMD\\RX78.TMD;1|SLPS_000.35|MOBILE SUIT GUNDAM|
|cdrom0:\\_HA30.STR;1|SCPS_100.16|HORNED OWL|
|cdrom0:\\SOUND\\TOMASON.STR;1|SCPS_100.87|GEKISOU TOMARUNNER|
|cdrom0:\\STORY4_1\\4S05B.MKO;1|SLPS_000.85|HOUMA HUNTER LIME - SPECIAL COLLECTION VOL.2|
|cdrom0:\\FLT\\ENTSTAR.STR;1|SLPS_000.22|STARBLADE ALPHA|
|cdrom0:\\XA\\TEST3.XAP;1|SLPS_000.89|THE ONI TAIJI - MEZASE! 2-DAIME MOMOTAROU|
|cdrom0:\\STR\\DEGI3.STR;1|SLPS_005.49|DIGCRO - DIGITAL NUMBER CROSSWORD|
|cdrom0:\\THATSPON\\LOG.BAK;1|SLPS_000.51|THAT'S PON!|
|cdrom0:\\EISEI\\KOMAGUMI.BIN;1|SLPS_000.90|EISEI MEIJIN|
|cdrom0:\\TITLE\\PACHI2BG.TIM;1|SLPS_000.21|KIKUNI MASAHIKO - JIRUSHI WARAU FUKEI-SAN PACHI-SLOT HUNTER|
|cdrom0:\\SIM\\DAT\\RDATWI.BIN;1|SLPS_000.37| PACHIOKUN - PACHINKO LAND ADVENTURE|
|cdrom0:\\AH1\\AH1MAP.MAP;1|SLPS_000.60|AQUANAUT NO KYUUJITSU|
|cdrom0:\\TPC\\TORNYA.TPC;1|SLPS_000.92| KING OF BOWLING|
|cdrom0:\\zzzzzzzz.dum;1|SLPS_013.83| SANKYO FEVER VOL.3 - MIHATA SIMULATION|
|cdrom0:\\EPI_MCH.STR;1|SCPS_100.09|PHILOSOMA|
|cdrom0:\\FJTCERE\\H_TAISOH.VHB;1|SLPS_001.37| 	 SUIKO ENBU - OUTLAWS OF THE LOST DYNASTY|
|cdrom0:\\OBJ.RRO;1|SLPS_000.01| RIDGE RACER|
|cdrom0:\\MOVIE\\VTENNIS.STR;1|SLPS_001.03|V-TENNIS|
|cdrom0:\\DATA2\\QUE184.TIM;1|SLPS_000.07|GEOM CUBE|
|cdrom0:\\DT_GO\\GOACC.TIM;1|SLPS_000.48|GOKUU DENSETSU - MAGIC BEAST WARRIORS|
|cdrom0:\\CDROM\\LASTPHOT\\ALL_C.NBN;1|SLPS_000.65|TOKIMEKI MEMORIAL - FOREVER WITH YOU|

<br>

Alternatively if game has only PSX.EXE and the above fails, PS1DRV (DECKARD and only specific PGIF models) does a specific check for the game Toushinden to apply compability only to original release.

<br>

| Title | Revision | EXE Date |
| :---:  |  :---:  |  :---: |
|SLPS_000.25| Original |1994-11-30|
|SLPS_000.25| Rev 1| 1995-01-25|

<br>

Only the 1994 release needs config. The version is determined by seeking to offset 0x380d0 of PSX.EXE and checking for <code>"KAYIN,NEXT TIME "</code> string.

