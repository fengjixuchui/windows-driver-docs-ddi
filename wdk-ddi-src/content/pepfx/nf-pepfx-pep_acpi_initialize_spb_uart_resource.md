---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function (pepfx.h)
description: The PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_UART_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_uart_resource.htm
tech.root: kernel
ms.assetid: C1018E89-D3EC-49A0-B02E-254378000378
ms.date: 04/30/2018
keywords: ["PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function"]
ms.keywords: 0, 1, 2, 3, 4, 5, 6, 7, PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE, PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_spb_uart_resource, pepfx/PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
f1_keywords:
 - "pepfx/PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
- pepfx.h
api_name:
- PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE
product:
- Windows
targetos: Windows
req.typenames: 
---

# PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_uart_resource">PEP_ACPI_SPB_UART_RESOURCE</a> structure.


## -parameters




### -param BaudRate [in]

Specifies the baud rate of the connection.


### -param BitsPerByte [in]

Specifies the number of bits per byte of data.


### -param StopBits [in]

Specifies the stop bits used in the connection.


### -param LinesInUse [in]

Flag indicating the serial lines that are enabled. A value of 1 in the bit positions indicates that the line is enabled.

<table>
<tr>
<th>Bit</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="0"></a><dl>
<dt><b>0</b></dt>
</dl>
</td>
<td width="60%">
This bit is reserved and must be set to zero.

</td>
</tr>
<tr>
<td width="40%"><a id="1"></a><dl>
<dt><b>1</b></dt>
</dl>
</td>
<td width="60%">
This bit is reserved and must be set to zero.

</td>
</tr>
<tr>
<td width="40%"><a id="2"></a><dl>
<dt><b>2</b></dt>
</dl>
</td>
<td width="60%">
Data Carrier Detect (DTD)

</td>
</tr>
<tr>
<td width="40%"><a id="3"></a><dl>
<dt><b>3</b></dt>
</dl>
</td>
<td width="60%">
Ring Indicator (RI)

</td>
</tr>
<tr>
<td width="40%"><a id="4"></a><dl>
<dt><b>4</b></dt>
</dl>
</td>
<td width="60%">
Data Set Ready (DSR)

</td>
</tr>
<tr>
<td width="40%"><a id="5"></a><dl>
<dt><b>5</b></dt>
</dl>
</td>
<td width="60%">
Data Terminal Ready (DTR)

</td>
</tr>
<tr>
<td width="40%"><a id="6"></a><dl>
<dt><b>6</b></dt>
</dl>
</td>
<td width="60%">
Clear to Send (CTS)

</td>
</tr>
<tr>
<td width="40%"><a id="7"></a><dl>
<dt><b>7</b></dt>
</dl>
</td>
<td width="60%">
Request to Send (RTS)

</td>
</tr>
</table>
 


### -param IsBigEndian [in]

Indicates if the most significant bits of data are in the lowest address. 


### -param Parity [in]

Specifies the parity of the connection.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
None

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
Even

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
Odd

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x03</dt>
</dl>
</td>
<td width="60%">
Mark

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
Space

</td>
</tr>
</table>
 


### -param FlowControl [in]

Specifies the type of flow control used by the connection.


### -param RxSize [in]

Specifies the maximum receive buffer size, in bytes, that is supported by this connection.


### -param TxSize [in]

Specifies the maximum transmit buffer size, in bytes, that is supported by this connection.


### -param ResourceSource [in]

The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.


### -param ResourceSourceIndex [in]

This parameter should always be zero.


### -param ResourceUsage [in]

Indicates if this resource is in use.


### -param SharedMode [in]

Indicates if this resource is shared.


### -param VendorData [in]

A pointer to optional data that is specific to the serial bus connection type.


### -param VendorDataLength [in]

The length of the buffer pointed to by the <i>VendorData</i> parameter.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_uart_resource">PEP_ACPI_SPB_UART_RESOURCE</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_uart_resource">PEP_ACPI_SPB_UART_RESOURCE</a>
 

 

