---
UID: NF:dbgeng.IDebugDataSpaces.ReadBusData
title: IDebugDataSpaces::ReadBusData (dbgeng.h)
description: The ReadBusData method reads data from a system bus.
old-location: debugger\readbusdata.htm
tech.root: debugger
ms.assetid: 5790b133-dbdc-4f77-a70e-616b0902794e
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces::ReadBusData"]
ms.keywords: IDebugDataSpaces interface [Windows Debugging],ReadBusData method, IDebugDataSpaces.ReadBusData, IDebugDataSpaces2 interface [Windows Debugging],ReadBusData method, IDebugDataSpaces2::ReadBusData, IDebugDataSpaces3 interface [Windows Debugging],ReadBusData method, IDebugDataSpaces3::ReadBusData, IDebugDataSpaces4 interface [Windows Debugging],ReadBusData method, IDebugDataSpaces4::ReadBusData, IDebugDataSpaces::ReadBusData, IDebugDataSpaces_59d5bf3f-7eb5-452c-ace2-4aed701d34a6.xml, ReadBusData, ReadBusData method [Windows Debugging], ReadBusData method [Windows Debugging],IDebugDataSpaces interface, ReadBusData method [Windows Debugging],IDebugDataSpaces2 interface, ReadBusData method [Windows Debugging],IDebugDataSpaces3 interface, ReadBusData method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::ReadBusData, dbgeng/IDebugDataSpaces3::ReadBusData, dbgeng/IDebugDataSpaces4::ReadBusData, dbgeng/IDebugDataSpaces::ReadBusData, debugger.readbusdata
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
 - IDebugDataSpaces::ReadBusData
 - dbgeng/IDebugDataSpaces::ReadBusData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces.ReadBusData
 - IDebugDataSpaces2.ReadBusData
 - IDebugDataSpaces3.ReadBusData
 - IDebugDataSpaces4.ReadBusData
---

# IDebugDataSpaces::ReadBusData


## -description

The <b>ReadBusData</b> method reads data from a system bus.

## -parameters

### -param BusDataType 

[in]
Specifies the bus data type to read from.  For details of allowed values see the documentation for the BUS_DATA_TYPE enumeration in the Microsoft Windows SDK.

### -param BusNumber 

[in]
Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same bus data type.

### -param SlotNumber 

[in]
Specifies the logical slot number on the bus.

### -param Offset 

[in]
Specifies the offset in the bus data to start reading from.

### -param Buffer 

[out]
Receives the data from the bus.

### -param BufferSize 

[in]
Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be returned.

### -param BytesRead 

[out, optional]
Receives the number of bytes read from the bus.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.

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
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method is only available in kernel-mode debugging.

The nature of the data read from the bus is system, bus, and slot dependent.