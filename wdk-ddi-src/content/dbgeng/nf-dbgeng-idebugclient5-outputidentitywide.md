---
UID: NF:dbgeng.IDebugClient5.OutputIdentityWide
title: IDebugClient5::OutputIdentityWide (dbgeng.h)
description: The OutputIdentityWide method formats and outputs a string describing the computer and user this client represents.
old-location: debugger\outputidentitywide.htm
tech.root: debugger
ms.assetid: e8f91713-ea1d-4262-bc0b-dd4e39d1c2c3
ms.date: 05/03/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],OutputIdentityWide method, IDebugClient5.OutputIdentityWide, IDebugClient5::OutputIdentityWide, OutputIdentityWide, OutputIdentityWide method [Windows Debugging], OutputIdentityWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::OutputIdentityWide, debugger.outputidentitywide
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
- IDebugClient5.OutputIdentityWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::OutputIdentityWide


## -description


The <b>OutputIdentityWide</b> method formats and outputs a string describing the computer and user this client represents.


## -parameters




### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Set to zero.


### -param Format [in]

Specifies a format string similar to the <b>printf</b> format string.  However, this format string must only contain one formatting directive, <b>%s</b>, which will be replaced by a description of the computer and user this client represents.


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
</table>
 




## -remarks



The specific content of the string varies with the operating system.  If the client is remotely connected, some network information may also be present.

For more information about client objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/client-objects">Client Objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-getidentity">GetIdentity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

