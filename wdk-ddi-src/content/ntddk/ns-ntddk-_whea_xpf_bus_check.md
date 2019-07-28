---
UID: NS:ntddk._WHEA_XPF_BUS_CHECK
title: _WHEA_XPF_BUS_CHECK (ntddk.h)
description: The WHEA_XPF_BUS_CHECK union describes bus error information for an x86 or x64 processor.
old-location: whea\whea_xpf_bus_check.htm
tech.root: whea
ms.assetid: 7886a796-2755-4367-bbbd-2017e7900bf4
ms.date: 02/20/2018
ms.keywords: "*PWHEA_XPF_BUS_CHECK, PWHEA_XPF_BUS_CHECK, PWHEA_XPF_BUS_CHECK union pointer [WHEA Drivers and Applications], WHEA_XPF_BUS_CHECK, WHEA_XPF_BUS_CHECK union [WHEA Drivers and Applications], _WHEA_XPF_BUS_CHECK, ntddk/PWHEA_XPF_BUS_CHECK, ntddk/WHEA_XPF_BUS_CHECK, whea.whea_xpf_bus_check, whearef_fff50a8d-8ab0-4f25-adb3-b33e1ea80aed.xml"
ms.topic: struct
f1_keywords:
 - "ntddk/WHEA_XPF_BUS_CHECK"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WHEA_XPF_BUS_CHECK
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_BUS_CHECK, *PWHEA_XPF_BUS_CHECK
---

# _WHEA_XPF_BUS_CHECK structure


## -description


The WHEA_XPF_BUS_CHECK union describes bus error information for an x86 or x64 processor.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.TransactionTypeValid

A single bit that indicates that the <b>TransactionType</b> member contains valid data.


### -field DUMMYSTRUCTNAME.OperationValid

A single bit that indicates that the <b>Operation</b> member contains valid data.


### -field DUMMYSTRUCTNAME.LevelValid

A single bit that indicates that the <b>Level</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ProcessorContextCorruptValid

A single bit that indicates that the <b>ProcessorContextCorrupt</b> member contains valid data.


### -field DUMMYSTRUCTNAME.UncorrectedValid

A single bit that indicates that the <b>Uncorrected </b>member contains valid data.


### -field DUMMYSTRUCTNAME.PreciseIPValid

A single bit that indicates that the <b>PreciseIP</b> member contains valid data.


### -field DUMMYSTRUCTNAME.RestartableIPValid

A single bit that indicates that the <b>RestartableIP</b> member contains valid data.


### -field DUMMYSTRUCTNAME.OverflowValid

A single bit that indicates that the <b>Overflow</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ParticipationValid

A single bit that indicates that the <b>Participation</b> member contains valid data.


### -field DUMMYSTRUCTNAME.TimeoutValid

A single bit that indicates that the <b>Timeout</b> member contains valid data.


### -field DUMMYSTRUCTNAME.AddressSpaceValid

A single bit that indicates that the <b>AddressSpace</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ReservedValid

Reserved for system use.


### -field DUMMYSTRUCTNAME.TransactionType

The type of transaction that was in progress when the error occurred. Possible values are:



This member contains valid data only if the <b>TransactionTypeValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Operation

The type of bus operation that caused the error. Possible values are:



This member contains valid data only if the <b>OperationValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Level

The level of the bus hierarchy where the error occurred.

This member contains valid data only if the <b>LevelValid</b> bit is set.


### -field DUMMYSTRUCTNAME.ProcessorContextCorrupt

A single bit that indicates that the processor context might have been corrupted.

This member contains valid data only if the <b>ProcessorContextCorruptValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Uncorrected

A single bit that indicates that the error has not been corrected.

This member contains valid data only if the <b>UncorrectedValid</b> bit is set.


### -field DUMMYSTRUCTNAME.PreciseIP

A single bit that indicates that the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structure that contains this WHEA_XPF_BUS_CHECK union is directly associated with the error.

This member contains valid data only if the <b>PreciseIPValid</b> bit is set.


### -field DUMMYSTRUCTNAME.RestartableIP

A single bit that indicates that program execution can be restarted reliably at the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> union that contains this WHEA_XPF_BUS_CHECK structure.

This member contains valid data only if the <b>RestartableIPValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Overflow

A single bit that indicates that an error overflow occurred.

This member contains valid data only if the <b>OverflowValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Participation

The type of participation by the local processor. Possible values are:



This member contains valid data only if the <b>ParticipationValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Timeout

A single bit that indicates that a timeout occurred.

This member contains valid data only if the <b>TimeoutValid</b> bit is set.


### -field DUMMYSTRUCTNAME.AddressSpace

The type of address space that was associated with the transaction that caused the error. Possible values are:



This member contains valid data only if the <b>AddressSpaceValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field XpfBusCheck

A ULONGLONG representation of the contents of the WHEA_XPF_BUS_CHECK union.


##### - AddressSpace.XPF_BUS_CHECK_ADDRESS_IO

I/O address space.


##### - AddressSpace.XPF_BUS_CHECK_ADDRESS_MEMORY

Memory address space.


##### - AddressSpace.XPF_BUS_CHECK_ADDRESS_OTHER

An unclassified type of address space.


##### - AddressSpace.XPF_BUS_CHECK_ADDRESS_RESERVED

Reserved.


##### - Operation.XPF_BUS_CHECK_OPERATION_DATAREAD

A data read operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_DATAWRITE

A data write operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_GENERIC

The type of operation cannot be determined.


##### - Operation.XPF_BUS_CHECK_OPERATION_GENREAD

A generic read operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_GENWRITE

A generic write operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_INSTRUCTIONFETCH

An instruction fetch operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_PREFETCH

An instruction prefetch operation.


##### - Participation.XPF_BUS_CHECK_PARTICIPATION_GENERIC

A generic value for this member if none of the other values are applicable.


##### - Participation.XPF_BUS_CHECK_PARTICIPATION_PROCOBSERVED

The local processor observed the request.


##### - Participation.XPF_BUS_CHECK_PARTICIPATION_PROCORIGINATED

The local processor originated the request.


##### - Participation.XPF_BUS_CHECK_PARTICIPATION_PROCRESPONDED

The local processor responded to the request.


##### - TransactionType.XPF_BUS_CHECK_TRANSACTIONTYPE_DATAACCESS

A data access transaction.


##### - TransactionType.XPF_BUS_CHECK_TRANSACTIONTYPE_GENERIC

A generic transaction.


##### - TransactionType.XPF_BUS_CHECK_TRANSACTIONTYPE_INSTRUCTION

A processor instruction transaction.


## -remarks



If the <b>CheckInfoId</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structure contains WHEA_BUSCHECK_GUID, the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains a WHEA_XPF_BUS_CHECK union.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_procinfo">WHEA_XPF_PROCINFO</a>
 

 

