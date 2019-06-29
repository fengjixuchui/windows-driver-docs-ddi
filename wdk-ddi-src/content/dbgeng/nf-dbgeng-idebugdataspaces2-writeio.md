---
UID: NF:dbgeng.IDebugDataSpaces2.WriteIo
title: IDebugDataSpaces2::WriteIo (dbgeng.h)
description: The WriteIo method writes to the system and bus I/O memory.
old-location: debugger\writeio.htm
tech.root: debugger
ms.assetid: 3bc84b15-7c13-4ad9-b9a1-6abd5a7389eb
ms.date: 05/03/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging],WriteIo method, IDebugDataSpaces2 interface [Windows Debugging],WriteIo method, IDebugDataSpaces2.WriteIo, IDebugDataSpaces2::WriteIo, IDebugDataSpaces3 interface [Windows Debugging],WriteIo method, IDebugDataSpaces3::WriteIo, IDebugDataSpaces4 interface [Windows Debugging],WriteIo method, IDebugDataSpaces4::WriteIo, IDebugDataSpaces::WriteIo, IDebugDataSpaces_d36b33ec-db19-4df1-8813-b77f22705279.xml, WriteIo, WriteIo method [Windows Debugging], WriteIo method [Windows Debugging],IDebugDataSpaces interface, WriteIo method [Windows Debugging],IDebugDataSpaces2 interface, WriteIo method [Windows Debugging],IDebugDataSpaces3 interface, WriteIo method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::WriteIo, dbgeng/IDebugDataSpaces3::WriteIo, dbgeng/IDebugDataSpaces4::WriteIo, dbgeng/IDebugDataSpaces::WriteIo, debugger.writeio
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
- IDebugDataSpaces.WriteIo
- IDebugDataSpaces2.WriteIo
- IDebugDataSpaces3.WriteIo
- IDebugDataSpaces4.WriteIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces2::WriteIo


## -description


The <b>WriteIo</b> method writes to the system and bus I/O memory.


## -parameters




### -param InterfaceType [in]

Specifies the interface type of the I/O bus.  This parameter may take values in the INTERFACE_TYPE enumeration defined in wdm.h.


### -param BusNumber [in]

Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same interface type.


### -param AddressSpace [in]

Set to one.


### -param Offset [in]

Specifies the location of the requested data.


### -param Buffer [in]

Specifies the data to write to the I/O bus.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.


### -param BytesWritten [out, optional]

Receives the number of bytes written to I/O bus.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



This method is only available in kernel-mode debugging.



