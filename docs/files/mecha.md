## Mecha possible config values

Mechacon compability values come from internal database of drivers. PS1DRV writes them to 0x1F402014 register. 
When IOP is reset to PS1 mode mechacon detects the reset and initializes PS1 mode after parsing the value from this register.


| Value | Description| 
| :---:  |     :--- |
|0x0|Default/NoChange (gets set as 2)|
|0x2|Default|
|0x3|Obsolete in Dragon mecha. Unknown for old mecha.|
|0x4|Obsolete in Dragon mecha. Unknown for old mecha.|
|0x5|Obsolete in Dragon mecha. Unknown for old mecha.|
|0x6|Obsolete in Dragon mecha. Unknown for old mecha.|
|0x7|Obsolete in Dragon mecha. Unknown for old mecha.|
|0x8|Obsolete in Dragon mecha. Unknown for old mecha.|
|0x9|Obsolete in Dragon mecha. Unknown for old mecha.|
|0xA|Obsolete in Dragon mecha. Unknown for old mecha.|
|0xB|Obsolete in Dragon mecha. Unknown for old mecha.|
|0xC|Obsolete in Dragon mecha. Unknown for old mecha.|
|0xD|Obsolete in Dragon mecha. Unknown for old mecha.|
|0xE|Obsolete in Dragon mecha. Unknown for old mecha.|
|0xF|Obsolete in Dragon mecha. Unknown for old mecha.|
|0x10|Obsolete in Dragon mecha. Unknown for old mecha.|
|0x11|All PS1 cmd 158us/316us delay (0x2780 PS1 clock cycles).|
|0x12|Allow Stop cmd (0x08) to succeed with INT3 instead of INT5 error in case there is no disc present.|
|0x13|Sets some obsolete compatibility flag in Dragon mecha. Unknown for old mecha.|
|0x14|GetStat response cmd 158us/316us delay (0x2780 PS1 clock cycles)|
|0x15|Allow Pause cmd (0x09) to succeed with INT3 instead of INT5 error in case the drive is still in seeking phase. Delay Pause cmd second reply (INT1) by 40ms.|
|0x16|Delay INT1 interrupt from ReadNS cmd being raised by 0x400 PS1 clock cycles.|
|0x17|Delay Pause cmd second reply (INT1) by 70ms.|
|0x18|Delay ReadS cmd (0x1b) second reply (INT1) by 400ms (first INT1 only).|
|0x19|Allow Pause cmd (0x09) to succeed with INT3 instead of INT5 error in case the drive is still in seeking phase.|
|0x1A|Delay Pause cmd second reply (INT1) by 70ms.|
|0x1B|Delay Pause cmd second reply (INT1) by 100ms.|
|0x1C|All PS1 cmd 106us/212 delay" (0x1a80 PS1 clock cycles).|
|0x1D|Delay SeekLP cmd second reply (INT1) by 50ms.|
|0x1E|When SetMode cmd (0x0E) is executed and drive is Play mode and the speed mode is different from current one, reforce a read right away.|
|0x1F|Delay Pause cmd second reply (INT1) by 40ms. All PS1 cmd 106us/212 delay" (0x1a80 PS1 clock cycles).|
|0x20|Delay INT1 interrupt from ReadNS cmd being raised by 0xd00 PS1 clock cycles.|
|0x21|Delay INT1 interrupt from ReadNS cmd being raised by 0x2780 PS1 clock cycles. Delay Pause cmd second reply (INT1) by 40ms.|
|0x90|Obsolete in Dragon mecha. Unknown for old mecha.|
|0xA0|Obsolete in Dragon mecha. Unknown for old mecha.|
|0xFE|Fast Disc Speed|

