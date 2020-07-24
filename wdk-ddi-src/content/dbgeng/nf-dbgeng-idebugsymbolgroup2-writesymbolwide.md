---
UID: NF:dbgeng.IDebugSymbolGroup2.WriteSymbolWide
title: IDebugSymbolGroup2::WriteSymbolWide (dbgeng.h)
description: The WriteSymbolWide method sets the value of the specified symbol.
old-location: debugger\writesymbolwide.htm
tech.root: debugger
ms.assetid: ed77fddf-c23c-4522-a2c4-875f07d249fb
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup2::WriteSymbolWide"]
ms.keywords: IDebugSymbolGroup2 interface [Windows Debugging],WriteSymbolWide method, IDebugSymbolGroup2.WriteSymbolWide, IDebugSymbolGroup2::WriteSymbolWide, WriteSymbolWide, WriteSymbolWide method [Windows Debugging], WriteSymbolWide method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::WriteSymbolWide, debugger.writesymbolwide
f1_keywords:
 - "dbgeng/IDebugSymbolGroup2.WriteSymbolWide"
 - "IDebugSymbolGroup2.WriteSymbolWide"
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSymbolGroup2.WriteSymbolWide
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::WriteSymbolWide


## -description


The <b>WriteSymbolWide</b> method sets the value of the specified symbol.


## -parameters




### -param Index [in]

The index of the symbol whose value will be changed. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Value [in]

A C++ expression that is evaluated to give the symbol's new value.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



This method can change symbols only if the symbols are stored in a register or memory location that the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> knowns and if they have not had their type changed to an extension by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-outputastype">OutputAsType</a> method.  

For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolvaluetext">GetSymbolValueText</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>
 

 

