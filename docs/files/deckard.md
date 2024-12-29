# RAW OLD OUTDATED DOCUMENTATION FOR THE CURIOUS ONE
# DO NOT PR ANYTHING IN HERE (WILL BE REJECTED) SINCE IT WIlL BE UPDATED IN THE FUTURE
# SOME NAMES ARE MATCHED BY DIFFERENT SOURCES, OTHERS WERE MADE UP
# SOME INFO MIGHT BE WRONG SO VERIFY ON YOUR OWN


# DECKARD

DECKARD is a IBM PowerPC custom CPU (404x/440x/custom hybrid build perhaps) running at 440 MHz (confirmed) included in the following PS2 models:

|Model|
|:---|
|DTL/SCPH-7500x|
|DTL/SCPH-7700x|
|DTL/SCPH-7900x|
|DTL/SCPH-9000x|
|PX300 (Sony Bravia TV)|

<br>

All models have the same exact code, only the timestamp changes.

|Timestamp|
|:---|
|20050620-173635,deckard.conf,deckard.bin,knaka@rom-server/~/build/20050620/deckard/src|
|20060210-140700,deckard.conf,deckard.bin,knaka@rom-server/~/build/20060210/deckard/src| 
|20060412-222127,deckard.conf,deckard.bin,knaka@rom-server/~/build/20060412/deckard/src|

<br>

<code>knaka</code> = Koji Nakamura
<br>

DECKARD patent was filed 7 days later than the first build timestamp 20050620. 

|Patent|
|:---|
|[JP Patent #4397858B2](https://patents.google.com/patent/JP4397858B2/en)|
|[US PATENT #7756697B2](https://patents.google.com/patent/US7756697B2/en)|

<br>


|Address|Name|
|:---:| :---|
00a031d8 | __SetMipsPC
00a031e8 | __SetApuClock
00a031f0 | __GetApuClock
00a04980 | ReadTimebase
00a04bf8 | CoreReset(mode)
00A04CD4 | CoreInit()
00A04E48 | main()
00a04e9c | EventsInsert
00a04eb4 | EventsDelete
00A04FF4 | AddEvent
00a05338 | EventsReset
00a0547c | EventsInit
00A05480 | GetMipsClock
00a0560c | HandleExcInterrupt
00a057b8 | HandleExcDataBP
00a05874 | GetApuClock
00A05894 | SetMipsClock
00A05924 | RaiseInterrupt
00A0594C | LowerInterrupt
00a05970 | SetC0Register
00a05ad0 | GetC0Register
00a05cdc | GetCop0StatusIEc 
00a05c44 | CpuReset
00a05cd4 | CpuInit
00a060f8 | BiuRead
00A064C8 | BiuWrite
00A06840 | Busc1Read
00A06874 | Busc1Write
00A068F0 | Busc2Read
00A06938 | Busc2Write
00a06748 | HwReadDefault
00A067D0 | HwWriteDefault
00a069a4 | MemMapHardware
00a06a20 | MemReset
00a06bec | MemInit
00A06D04 | IntcAssertRequest
00a06d68 | IntcDeassertRequest
00A06D6C | IntcRead
00a06e74 | IntcWrite
00a06fc0 | IntcUpdateIstat
00A07300 | IntcReset
00a073b8 | IntcInit
00a073dc | IntcWriteHwImask
00A09DA4 | SpuRead
00A09E60 | SPUWrite
00a0a24c | _SPUDMAExecHandler
00a0a5dc | SpuReset
00a0a714 | SpuInit
00a07468 | DmacGetScheduleCycles
00a0789c | DmacRead
00a07a18 | DmacWrite
00a07c7c | Dmac2Read
00a07d44 | DmacWrite
00a07e68 | DmacRegisterTransfer
00A08040 | DmacScheduleTransfer
00a080e8 | DmacRegisterHandler
00a08104 | DmacRegisterMBTHandlers
00a0829c | MdecToStartHandler
00a082d4 | MdecToExecHandler
00a08320 | MdecFromStartHandler
00a08358 | MdecFromExecHandler
00a083a4 | Sif2StartHandler
00a083dc | Sif2ExecHandler
00a08428 | CdromDMAStartHandler
00A084B0 | CdromDMAExecHandler
00a0850c | SpuStartHandler
00a08550 | SpuExecHandler
00a085ac | PioStartHandler
00a085e4 | PioExecHandler
00a08630 | OtcHandler
00a086e8 | OtcExecHandler
00a08734 | Spu2StartHandler
00a0876c | Spu2ExecHandler
00a087b8 | Dev9StartHandler
00a087f0 | Dev9ExecHandler
00a0883c | Sif0StartHandler
00a08880 | Sif0ExecHandler
00a088dc | Sif1StartHandler
00a08914 | Sif1ExecHandler
00a08960 | Sio2ToStartHandler
00a08998 | Sio2ToExecHandler
00a089e4 | Sio2FromStartHandler
00a08a1c | Sio2FromExecHandler
00a08a6c | DmacReset
00A08D14 | DmacInit
00A08D28 | TimerRead
00A08E2C | TimerWrite
00a08e9c | TimerReset
00a08f90 | TimerInit
00a08fac | nullsub Init sub for something in CoreInit, dummied out.
00A08FB4 | GmifRead
00A08FBC | GmifWrite
00a08fe8 | GmifSetPSMode
00a09004 | GmifReset
00a09060 | GmifInit
00a09590 | PGPUStartHandler
00a0997c | PGPUExecHandler
00a091d0 | PGPURead
00a092d0 | PGPUWrite
00a09c0c | PGPUReset
00a09d9c | PGPUInit
00A0ADB0 | CdromReset
00a0ae44 | CdromInit
00A0A71C | Dev5Read
00a0a724 | Dev5Write
00a0a744 | Dev5Reset
00a0a748 | Dev5Init
00a0a750 | Dev9SetMacLValue
00a0a768 | Dev9SetMacHValue
00a0a910 | Dev9SetSLFunc
00a0aabc | Dev9Read
00a0ab2c | Dev9Write
00a0ac5c | Dev9Reset
00A0AD28 | Dev9Init
00a0ae88 | Sio0DataWrite
00a0af90 | Sio0CtrlWrite
00a0b0b8 | Sio0Read 
00a0b12c | Sio0Write
00A0B1B8 | Sio0Reset
00a0b214 | Sio0Init
00a0b21c | Sio1Read
00a0b270 | Sio1Write
00A0B2D4 | Sio1Reset 
00a0b344 | Sio1Init
00a0b34c | Sio2Read 
00a0b3a8 | Sio2Write
00A0B5F8 | Sio2Reset
00a0b644 | Sio2Init
00a0b64c | DeciPioRead
00a0b66c | DeciPioWrite
00A0B6DC | DeciPioReset
00a0b72c | DeciPioInit
00a0b734 | UsbRead
00a0b7d8 | UsbWrite
00a0b88c | UsbReset
00a0b90c | UsbEnableDelayIntr
00a0b928 | UsbIntrCallback
00A0B970 | UsbInit
00a0b984 | UsbCheckIntrType
00a0b998 | UsbSetIntrTypeReceived
00a0b9b4 | InitBiosArea
00a0b9fc | SetDev2BiosAreaAddr
00a0ba38 | SetDev2BiosAreaData
00a0bdf4 | MdecInit
00A0BE08 | MdecReset
00a0c698 | ILinkReset
00a0c7bc | ILinkInit
00a0c7c4 | CoreGetParam
00a0c7f0 | CoreSetParam
00a0c864 | CoreParamsReset
00a0c948 | CoreSetFunction
00a0c964 | CoreParamsInit
00a0c98c | memcpy
00A0C9B4 | memset


<br>


```
//Base 0x1ffe000
#define BIU_CACHE_CONFIG  (0x0130)
#define BIU_SPAD0_CONFIG  (0x0140)  //scratchpad config 0
#define BIU_SPAD1_CONFIG  (0x0144)  //scratchpad config 1

#define BIU_BIOS_ADDR     (0x0180)
#define BIU_BIOS_DATA     (0x0184)
#define BIU_MAC_L    (0x0188)
#define BIU_MAC_H    (0x018c)

#define BIU_EEPROM_FUNC     (0x0190)
#define BIU_PARAM_ID          (0x01a0)
#define BIU_PARAM_VALUE       (0x01a4)


//00a0e954 to 00A0E988 = 0x34 size, 13 entries.
int DMAC_ICR_LUT[13] {
	0xFFFFFFFF, 0xFFFFFFFF, 0x1, 0x2, 0x9, 0x17, 0xFFFFFFFF, 0xC, 0x1A,0xFFFFFFFF,
    0xFFFFFFFF, 0x11, 0x11
};

//00A0E988 to 0xA0E9F0 = 0x64 size, 2 table for 13 entries.
int DMAC_CYCLES_LUT[2][13] {
	//Transfer mode 0 = To Main RAM
	{1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1},
	
	//Transfer mode 1 = From Main RAM
	{1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1},
};


//DAT_00a80000 MemHwReadLut    00a80000 to 00ac0000
int MemHwReadLut[0x10000];

//DAT_00ac0000 MemHwWriteLut   00ac0000 to  0xB00000
int MemHwWriteLut[0x10000];


//DAT_00be00a4
int CoreMode;   // 0 = PS2  1 = PS1

/* 0x14 in size. */
struct t_event {
   struct t_event *pPrev;
   struct t_event *pNext;
   int FireTime;
   int Callback;
   int Param;
};


#define MAX_EVENTS (24)

//00be00b4 - 0xBE0294 
struct t_event Events[MAX_EVENTS];

#define EVENTS_SIZE (sizeof(Events) / sizeof(Events[0]))

//00be0298
int MipsClock;

//00be029c
int MipsEventTrigger;

//DAT_00be02a0
struct t_event *g_pIdleEvents

//DAT_00be02a4
struct t_event *g_pActiveEvents

//DAT_00be02a8
//DAT_00be02aC


#define CPRI_BPC    (3)
#define CPRI_BDA    (5)
#define CPRI_WIRED  (6)
#define CPRI_DCIC   (7)
#define CPRI_BADV   (8)
#define CPRI_BDAM   (9)
#define CPRI_BPCM   (11)
#define CPRI_STATUS (12)
#define CPRI_CAUSE  (13)
#define CPRI_EPC    (14)
#define CPRI_PRID   (15)


//0xBE02C4  + 0x11c =  0xBE03E0
typedef struct gpr_t {
    int zr; // BE02C4
    int at; // BE02C8
    int v0; // BE02CC
    int v1; // BE02D0 
    int a0; // BE02D4 
    int a1; // BE02D8 
    int a2; // BE02DC 
    int a3; // BE02E0 
    int t0; // BE02E4 
    int t1; // BE02E8 
    int t2; // BE02EC 
    int t3; // BE02F0
    int t4; // BE02F4
    int t5; // BE02F8
    int t6; // BE02FC
    int t7; // BE0300
    int s0; // BE0304
    int s1; // BE0308
    int s2; // BE030C
    int s3; // BE0310
    int s4; // BE0314
    int s5; // BE0218
    int s6; // BE021C
    int s7; // BE0220
    int t8; // BE0224 
    int t9; // BE0228
    int k0; // BE022C
    int k1; // BE0230
    int gp; // BE0234
    int sp; // BE0238
    int fp; // BE023C
    int ra; // BE0340
}



typedef struct cpr_t {

	int index;     // BE0344   0  INDX	Index
	int random;    // BE0348   1  RAND	Random	
	int entrylo0;  // BE034C   2  TLBL	TBL low	
	int entrylo1;  // BE0350   3  BPC	Breakpoint PC	
	int context;   // BE0354   4  CTXT	Context	
	int pagemask;  // BE0358   5  BDA	Breakpoint data
	int wired;     // BE035C   6  PIDMASK	PID Mask	
	int dcic;      // BE0360   7  DCIC	Data/Counter interrupt control
	int badvaddr;  // BE0364   8  BADV	Bad Virtual Address
	int count;     // BE0368   9  BDAM	Break data mask	
	int entryhi;   // BE036C  10  TLBH	TBL high
	int compare;   // BE0370  11  BPCM	Break point counter mask	
	int status;    // BE0374  12  SR	System status register	
	int cause;     // BE0378  13  CAUSE	Cause
	int epc;       // BE037C  14  EPC	Exception Program Counter
	int prid;      // BE0380  15
    
	int config;    // BE0384  16  config
	int rsvd17;    // BE0388  17  rsvd17
	int rsvd18;    // BE038C  18  rsvd18
	int rsvd19;    // BE0390  19  rsvd19
	int rsvd20;    // BE0394  20  rsvd20
	int rsvd21;    // BE0398  21  rsvd21
	int rsvd22;    // BE039C  22  rsvd22
	int badpaddr;  // BE03A0  23  badpaddr
	int debug;     // BE03A4  24  debug
	int perf;      // BE03A8  25  perf
	int rsvd26;    // BE03AC  26  rsvd26
	int rsvd27;    // BE03B0  27  rsvd27
	int taglo;     // BE03B4  28  taglo
	int taghi;     // BE03B8  29  taghi
	int errorepc;  // BE03BC  30  errorepc
}


//0xBE02C4
typedef struct cpuregs_t {
	gpr_t gpr;
	
	//BE0344
	cpr_t cpr;
	
	//BE03C0
	int ???;     // BE03C0  0x0FC
	int pc;      // BE03C4  0x100
	int ???;     // BE03C8  0x104
	int ???;     // BE03CC  0x108
	int ???;     // BE03D0  0x10C
	int ???;     // BE03D4  0x110
	int ???;     // BE03D8  0x114 some sort of flag forcing to get (E)PC from HW
	int ???;     // BE03DC  0x118
	
}


//0x11C in size.
#define CPUREGS_SIZE (sizeof(cpu_regs) / sizeof(cpu_regs[0]))


//DAT_00be03e8
int sBiu; //software Biu

//DAT_00be03ec
int MACdone; // flag when EEconf has finished setting MAC.

//DAT_00be03f0
int sSpad0Config;

//DAT_00be03f4
int sSpad1Config;


//DAT_00be03f8
int sBusc2Dev9Delay2;

//DAT_00be03fc
int sBusc1SpuDelay;

//DAT_00be0400 set by EECONF
int sBiuParamId;

//DAT_00be0404 set by EECONF
int sBiuParamValue;



/* INTC VALUES */

//DAT_00be0408
int sIntGmask; // global mask

//DAT_00be040c   
int sIntcStat; // software/show 0x1F801070 "INTC_ISTAT"

//DAT_00be0410
int sIntcMask;

//DAT_00be0414
int sIntcEdir;


typedef struct DmaChReg {
	int madr;
	int bcr;
	int chcr;
	int tadr;
	int StartHandler;
	int ExecHandler;
	int MadrWriteHandler
	int BcrWriteHandler
	int TadrWriteHandler;
	int DmaEventPtr;
	int unk;
}

//memset(&DAT_00be0428,0,0x28);  0x0be0428 + 0x28 = 0xBE0450

typedef struct dmac_regs_t{
	int DmacPcr;    //DAT_00be0428    //0x1F8010F0 "DMAC_PCR"
	int DmacPcr2;   //DAT_00be042C   //DMAC_PCR2
	int DmacEn;     //DAT_00be0430 DMAC_EN
	int DmacIntEn;  //DAT_00be0434 DMAC_INTEN
	DAT_00be0438;
	DAT_00be043C;
	DAT_00be0440;
	DAT_00be0444;
	int DmacDicrMasterEnable; //DAT_00be0448 bit31
	DAT_00be044C;
}


//DAT_00be0454 to 0xBE0690  0x2c*13 = 0x23c 

#define DMA_CHANELS_COUNT (13)
DmaChReg sDmac[DMA_CHANELS_COUNT];

#define SDMAC_SIZE (sizeof(sDmac) / sizeof(sDmac[0]))


// Timers
//DAT_00be0690
int Rtc0ModeNeedDelay;

//DAT_00be0694
int Rtc0DelayPastCycles;

//DAT_00be0698 
int sRtc0ModeValue;


//GMIF
//DAT_00be069c
int GmifEnabledEEaccess;


//DAT_00be0824
int sUsbDescrA;

//DAT_00be0828
int usbIntrType;

#define USB_INTR_TYPE_DIRECT   (0)
#define USB_INTR_TYPE_DELAY    (1)
#define USB_INTR_TYPE_RECEIVED (2)



//DAT_00be082c
int BiosAreaDone;

//DAT_00be0830
int Dev2BiosAreaAddr;

// 00be0834 - 0xBE0934
char ROMVERtbl[0x100];


/* 0xC in size. */
struct t_param {
   int id;
   int value;
   char* name;
};

//0xA0F14C - 0xA0F224
struct t_param PARAMS_DEFAULT[] = { 
	{0x01, 0x1F4,  "PARAM_MDEC_DELAY_CYCLE"},
	{0x01, 0x7D0   "PARAM_SPU_INT_DELAY_LIMIT"},
	{0x02, 0x23,   "PARAM_SPU_INT_DELAY_PPC_COEFF"},
	{0x03, 0x7D0,  "PARAM_SPU2_INT_DELAY_LIMIT"},
	{0x04, 0x14,   "PARAM_SPU2_INT_DELAY_PPC_COEFF"},
	{0x05, 0x0,    "PARAM_DMAC_CH10_INT_DELAY"},
	{0x06, 0x1,    "PARAM_CPU_DELAY"},
	{0x07, 0x20,   "PARAM_SPU_DMA_WAIT_LIMIT"},
	{0x08, 0x0,    "PARAM_GPU_DMA_WAIT_LIMIT"},
	{0x09, 0x0,    "PARAM_DMAC_CH10_INT_DELAY_DPC"},
	{0x0A, 0x0,    "PARAM_CPU_DELAY_DPC"},
	{0x0B, 0x0,    "PARAM_USB_DELAYED_INT_ENABLE"},
	{0x0C, 0x0,    "PARAM_TIMER_LOAD_DELAY"},
	{0x0D, 0x229C, "PARAM_SIO0_DTR_SCK_DELAY"},
	{0x0E, 0x6EC,  "PARAM_SIO0_DSR_SCK_DELAY_C"},
	{0x0F, 0x6EC,  "PARAM_SIO0_DSR_SCK_DELAY_M"},
	{0x10, 0x1,    "PARAM_MIPS_DCACHE_ON"},
	{0x11, 0x90,   "PARAM_CACHE_FLASH_CHANNELS"}
};

//18 params in total.
#define PARAMS_COUNT (sizeof(PARAMS_DEFAULT) / sizeof(PARAMS_DEFAULT[0]))

//00be09e0 - 0xBE0A28
int PARAMS_VALUES[PARAMS_COUNT];

//00be0a30 - 0xBE0A78
int PARAMS_NAMES[PARAMS_COUNT];

//00be0a78 - 0xBE0AC0
void (*PARAMS_FUNC[PARAMS_COUNT])();


//Indexes for the Params.
#define PARAM_MDEC_DELAY_CYCLE          (0x00)
#define PARAM_SPU_INT_DELAY_LIMIT       (0x01)
#define PARAM_SPU_INT_DELAY_PPC_COEFF   (0x02)
#define PARAM_SPU2_INT_DELAY_LIMIT      (0x03)
#define PARAM_SPU2_INT_DELAY_PPC_COEFF  (0x04)
#define PARAM_DMAC_CH10_INT_DELAY       (0x05)
#define PARAM_CPU_DELAY                 (0x06)
#define PARAM_SPU_DMA_WAIT_LIMIT        (0x07)
#define PARAM_GPU_DMA_WAIT_LIMIT        (0x08)
#define PARAM_DMAC_CH10_INT_DELAY_DPC   (0x09)
#define PARAM_CPU_DELAY_DPC             (0x0A)
#define PARAM_USB_DELAYED_INT_ENABLE    (0x0B)
#define PARAM_TIMER_LOAD_DELAY          (0x0C)
#define PARAM_SIO0_DTR_SCK_DELAY        (0x0D)
#define PARAM_SIO0_DSR_SCK_DELAY_C      (0x0E)
#define PARAM_SIO0_DSR_SCK_DELAY_M      (0x0F)
#define PARAM_MIPS_DCACHE_ON            (0x10)
#define PARAM_CACHE_FLASH_CHANNELS      (0x11)

```

