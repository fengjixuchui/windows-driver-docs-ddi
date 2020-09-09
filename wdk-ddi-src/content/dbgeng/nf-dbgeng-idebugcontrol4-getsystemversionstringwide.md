---
UID: NF:dbgeng.IDebugControl4.GetSystemVersionStringWide
title: IDebugControl4::GetSystemVersionStringWide (dbgeng.h)
description: The GetSystemVersionStringWide method returns a string that describes the target's operating system version.
old-location: debugger\getsystemversionstringwide.htm
tech.root: debugger
ms.assetid: a98dee8a-1911-40e0-b1fd-c7a1ee40a8d7
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetSystemVersionStringWide"]
ms.keywords: GetSystemVersionStringWide, GetSystemVersionStringWide method [Windows Debugging], GetSystemVersionStringWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetSystemVersionStringWide method, IDebugControl4.GetSystemVersionStringWide, IDebugControl4::GetSystemVersionStringWide, dbgeng/IDebugControl4::GetSystemVersionStringWide, debugger.getsystemversionstringwide
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
 - IDebugControl4::GetSystemVersionStringWide
 - dbgeng/IDebugControl4::GetSystemVersionStringWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4.GetSystemVersionStringWide
---

# IDebugControl4::GetSystemVersionStringWide


## -description

The <b>GetSystemVersionStringWide</b>  method returns a string that describes the target's operating system version.

## -parameters

### -param Which 

[in]
Specifies which version string to return.  The possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Version string</th>
</tr>
<tr>
<td>
DEBUG_SYSVERSTR_SERVICE_PACK

</td>
<td>
Returns a description of the service pack for the target's operating system.  For example, "Service Pack 1".

</td>
</tr>
<tr>
<td>
DEBUG_SYSVERSTR_BUILD

</td>
<td>
Returns a description of the target's operating system build version.  For example, "kernel32.dll version: 5.1.2600.1106 (xpsp1.020828-1920)".

</td>
</tr>
</table>

### -param Buffer 

[out, optional]
Receives the version string.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.

### -param StringSize 

[out, optional]
Receives the size, in characters, of the string that identifies the build.  If <i>SizeString</i> is <b>NULL</b>, this information is not returned.

## -returns

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful. However, the buffer was too small, so the string was truncated.

</td>
</tr>
</table>

## -remarks

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/target-information">Target Information</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getsystemversion">GetSystemVersion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getsystemversionvalues">GetSystemVersionValues</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>

