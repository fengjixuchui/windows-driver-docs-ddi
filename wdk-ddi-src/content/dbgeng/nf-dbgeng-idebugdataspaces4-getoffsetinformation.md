---
UID: NF:dbgeng.IDebugDataSpaces4.GetOffsetInformation
title: IDebugDataSpaces4::GetOffsetInformation (dbgeng.h)
description: The GetOffsetInformation method provides general information about an address in a process's data space.
old-location: debugger\getoffsetinformation.htm
tech.root: debugger
ms.assetid: 5ef00c92-7b32-473a-8401-4c02e864c181
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces4::GetOffsetInformation"]
ms.keywords: GetOffsetInformation, GetOffsetInformation method [Windows Debugging], GetOffsetInformation method [Windows Debugging],IDebugDataSpaces4 interface, IDebugDataSpaces4 interface [Windows Debugging],GetOffsetInformation method, IDebugDataSpaces4.GetOffsetInformation, IDebugDataSpaces4::GetOffsetInformation, IDebugDataSpaces_c434b12b-78ff-4f6a-ac69-6069dd273ba8.xml, dbgeng/IDebugDataSpaces4::GetOffsetInformation, debugger.getoffsetinformation
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugDataSpaces4::GetOffsetInformation
 - dbgeng/IDebugDataSpaces4::GetOffsetInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces4.GetOffsetInformation
---

# IDebugDataSpaces4::GetOffsetInformation


## -description

The <b>GetOffsetInformation</b> method provides general information about an address in a process's data space.

## -parameters

### -param Space 

[in]
Specifies the data space to which the <i>Offset </i>parameter applies.  The allowed values depend on the <i>Which</i> parameter.

### -param Which 

[in]
Specifies which information about the data is being queried.  This determines the possible values for <i>Space</i> and the type of the data returned in <i>Buffer</i>.  Possible values are:





#### DEBUG_OFFSINFO_VIRTUAL_SOURCE

Returns the source of the target's virtual memory at <i>Offset</i>.  This is where the debugger engine reads the memory from.  <i>Space</i> must be set to DEBUG_DATA_SPACE_VIRTUAL.  A ULONG is returned to <i>Buffer</i>.  This ULONG can take the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_VSOURCE_INVALID

</td>
<td>
The <i>Offset</i> offset is not available in the process's virtual address space.

This could mean that the address is invalid, or that the memory is unavailable -- for example, a crash-dump file might not contain all of the memory for the process or for the kernel.

</td>
</tr>
<tr>
<td>
DEBUG_VSOURCE_DEBUGGEE

</td>
<td>
The virtual memory at the <i>Offset</i> offset is provided by the target.

</td>
</tr>
<tr>
<td>
DEBUG_VSOURCE_MAPPED_IMAGE

</td>
<td>
The debugger engine reads the target's virtual memory at <i>Offset </i>offset from a local image file.  This is often the case in minidump files where the module images are not included in the dump file and are instead loaded by the debugger engine.

</td>
</tr>
</table>

### -param Offset 

[in]
Specifies the offset in the target's data space for which the information is returned.

### -param Buffer 

[out, optional]
Specifies the buffer to receive the information.  The type of the data returned depends on the value of <i>Which</i>.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size, in bytes, of the <i>Buffer </i>buffer.

### -param InfoSize 

[out, optional]
Receives the size, in bytes, of the information that is returned.  If <i>InfoSize</i> is <b>NULL</b>, this information is not returned.

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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