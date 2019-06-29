---
UID: NF:dbgeng.IDebugSymbols3.GetNameByOffset
title: IDebugSymbols3::GetNameByOffset (dbgeng.h)
description: The GetNameByOffset method returns the name of the symbol at the specified location in the target's virtual address space.
old-location: debugger\getnamebyoffset.htm
tech.root: debugger
ms.assetid: 47f87684-339a-49e0-a349-491054ab26ff
ms.date: 05/03/2018
ms.keywords: GetNameByOffset, GetNameByOffset method [Windows Debugging], GetNameByOffset method [Windows Debugging],IDebugSymbols interface, GetNameByOffset method [Windows Debugging],IDebugSymbols2 interface, GetNameByOffset method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetNameByOffset method, IDebugSymbols2 interface [Windows Debugging],GetNameByOffset method, IDebugSymbols2::GetNameByOffset, IDebugSymbols3 interface [Windows Debugging],GetNameByOffset method, IDebugSymbols3.GetNameByOffset, IDebugSymbols3::GetNameByOffset, IDebugSymbols::GetNameByOffset, IDebugSymbols_5045ed52-43b3-4f5c-90fe-d9725aeb5782.xml, dbgeng/IDebugSymbols2::GetNameByOffset, dbgeng/IDebugSymbols3::GetNameByOffset, dbgeng/IDebugSymbols::GetNameByOffset, debugger.getnamebyoffset
ms.topic: method
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
- IDebugSymbols.GetNameByOffset
- IDebugSymbols2.GetNameByOffset
- IDebugSymbols3.GetNameByOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetNameByOffset


## -description


The <b>GetNameByOffset</b>  method returns the name of the symbol at the specified location in the target's virtual address space.


## -parameters




### -param Offset [in]

Specifies the location in the target's virtual address space of the symbol whose name is requested.  <i>Offset</i> does not need to specify the base location of the symbol; it only needs to specify a location within the symbol's memory allocation.


### -param NameBuffer [out, optional]

Receives the symbol's name.  The name is qualified by the module to which the symbol belongs (for example, <b>mymodule!main</b>).  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size in characters of the buffer <i>NameBuffer</i>.


### -param NameSize [out, optional]

Receives the size in characters of the symbol's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param Displacement [out, optional]

Receives the difference between the value of <i>Offset</i> and the base location of the symbol.  If <i>Displacement</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the buffer was not large enough to hold the symbol's name, so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
No symbol could be found at the specified location.

</td>
</tr>
</table>
 




## -remarks



For more information about symbols and symbol names, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnearnamebyoffset">GetNearNameByOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getoffsetbyname">GetOffsetByName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

