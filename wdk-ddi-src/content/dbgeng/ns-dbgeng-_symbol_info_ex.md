---
UID: NS:dbgeng._SYMBOL_INFO_EX
title: _SYMBOL_INFO_EX (dbgeng.h)
description: The SYMBOL_INFO_EX structure describes the extended line symbol information.
old-location: debugger\symbol_info_ex.htm
tech.root: debugger
ms.assetid: BDB8179A-4A97-4E83-B4A4-7B8358B3510C
ms.date: 05/03/2018
ms.keywords: "*PSYMBOL_INFO_EX, PSYMBOL_INFO_EX, PSYMBOL_INFO_EX structure pointer [Windows Debugging], SYMBOL_INFO_EX, SYMBOL_INFO_EX structure [Windows Debugging], _SYMBOL_INFO_EX, dbgeng/PSYMBOL_INFO_EX, dbgeng/SYMBOL_INFO_EX, debugger.symbol_info_ex"
ms.topic: struct
f1_keywords:
 - "dbgeng/SYMBOL_INFO_EX"
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- DbgEng.h
api_name:
- SYMBOL_INFO_EX
product:
- Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# _SYMBOL_INFO_EX structure


## -description


The SYMBOL_INFO_EX structure describes the extended line symbol information.


## -struct-fields




### -field SizeOfStruct

Set to sizeof(SYMBOL_INFO_EX).


### -field TypeOfInfo

Type of the symbol information stored.  DEBUG_SYMINFO_BREAKPOINT_SOURCE_LINE is the only supported type.


### -field Offset

Address of the first line that does not correspond to compiler added glue line.


### -field Line

First line number that does not correspond to a compiler added glue line.


### -field Displacement

Line displacement: Offset between given address and the first instruction of the line.


### -field Reserved

 




#### - Reserved[4]

Reserved for future use. This parameter can be set to any value.


## -remarks



Glue lines are code lines added to the binary by the compiler/linker. Glue lines do not have corresponding lines in the original source code. They are added to bind together functionality inside of the PE generated binary, for example calling NET framework functions inside of a native binary.



