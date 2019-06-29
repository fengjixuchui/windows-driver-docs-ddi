---
UID: NF:wdbgexts.GetFieldOffset
title: GetFieldOffset function (wdbgexts.h)
description: The GetFieldOffset function returns the offset of a member from the beginning of a structure.
old-location: debugger\getfieldoffset.htm
tech.root: debugger
ms.assetid: 3e5e782b-1a72-446d-9d15-c0f513f3440c
ms.date: 05/03/2018
ms.keywords: GetFieldOffset, GetFieldOffset function [Windows Debugging], WdbgExts_Ref_22c8a9bc-dec9-4eec-95c6-b265694b4385.xml, debugger.getfieldoffset, wdbgexts/GetFieldOffset
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
- wdbgexts.h
api_name:
- GetFieldOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetFieldOffset function


## -description


The <b>GetFieldOffset</b> function returns the offset of a member from the beginning of a structure.


## -parameters




### -param Type [in]

Specifies the name of the type of the structure.  This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.


### -param Field [in]

Specifies the name of the member in the structure.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield".


### -param pOffset [out]

Receives the offset of the member from the beginning of an instance of the structure.


## -returns



If the function succeeds, the return value is zero. Otherwise, the return value is an <a href="https://docs.microsoft.com/previous-versions/ff550910(v=vs.85)">IG_DUMP_SYMBOL_INFO error code</a>. 



