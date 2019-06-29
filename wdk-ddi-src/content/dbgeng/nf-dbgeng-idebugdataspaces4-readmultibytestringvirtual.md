---
UID: NF:dbgeng.IDebugDataSpaces4.ReadMultiByteStringVirtual
title: IDebugDataSpaces4::ReadMultiByteStringVirtual (dbgeng.h)
description: The ReadMultiByteStringVirtual method reads a null-terminated, multibyte string from the target.
old-location: debugger\readmultibytestringvirtual.htm
tech.root: debugger
ms.assetid: b86caa13-bdb3-4bc4-b2c1-3e51cbcf396f
ms.date: 05/03/2018
ms.keywords: IDebugDataSpaces4 interface [Windows Debugging],ReadMultiByteStringVirtual method, IDebugDataSpaces4.ReadMultiByteStringVirtual, IDebugDataSpaces4::ReadMultiByteStringVirtual, IDebugDataSpaces_43ca08e3-d4f0-43f8-b84e-514d3b52c6c4.xml, ReadMultiByteStringVirtual, ReadMultiByteStringVirtual method [Windows Debugging], ReadMultiByteStringVirtual method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces4::ReadMultiByteStringVirtual, debugger.readmultibytestringvirtual
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
- IDebugDataSpaces4.ReadMultiByteStringVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces4::ReadMultiByteStringVirtual


## -description


The <b>ReadMultiByteStringVirtual</b> method reads a null-terminated, multibyte string from the target.


## -parameters




### -param Offset [in]

Specifies the location of the string in the process's virtual address space.


### -param MaxBytes [in]

Specifies the maximum number of bytes to read from the target.


### -param Buffer [out, optional]

Receives the string from the target.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

<div class="alert"><b>Note</b>    The remainder of the buffer, following the returned string, might be overwritten by this method.</div>
<div> </div>

### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param StringBytes [out, optional]

Receives the size, in bytes, of the string.  If <i>StringBytes</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However <i>Buffer</i> was not large enough to hold the string and the string was truncated to fit in <i>Buffer</i>.  The truncated string is null-terminated if <i>Buffer</i> has space for at least one character.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
A null-terminator was not found after reading <i>MaxBytes</i> from the target.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



The engine will read up to <i>MaxBytes</i> from the target looking for a null-terminator.  If the string has more than <i>BufferSize</i> characters, the string will be truncated to fit in <i>Buffer</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readmultibytestringvirtualwide">ReadMultiByteStringVirtualWide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readunicodestringvirtual">ReadUnicodeStringVirtual</a>
 

 

