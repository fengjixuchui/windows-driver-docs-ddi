---
UID: NF:storport.StorPortSetUnitAttributes
title: StorPortSetUnitAttributes function (storport.h)
description: The StorPortSetUnitAttributes routine registers the power attributes of a storage unit device with the Storport driver.
old-location: storage\storportsetunitattributes.htm
tech.root: storage
ms.assetid: 0E05233D-79B0-4FC7-B13C-91B6B1F57E89
ms.date: 03/29/2018
keywords: ["StorPortSetUnitAttributes function"]
ms.keywords: StorPortSetUnitAttributes, StorPortSetUnitAttributes routine [Storage Devices], storage.storportsetunitattributes, storport/StorPortSetUnitAttributes
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortSetUnitAttributes
 - storport/StorPortSetUnitAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - StorPortSetUnitAttributes
---

# StorPortSetUnitAttributes function


## -description

The <b>StorPortSetUnitAttributes</b> routine registers the power attributes of a storage unit device with the Storport driver.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Address 

[in]
The storage unit device address. This parameter must not be NULL.

### -param Attributes 

[in]
A set of bitfields indicating the attributes supported for the unit device.

## -returns

<b>StorPortSetUnitAttributes</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the routine set the unit attributes successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> pointer is <b>NULL</b>.

-or-

One or more reserved bits in <i>Attributes</i> are set.

-or-

The unit address in <i>Address</i> is formatted incorrectly.

-or-

A unit device is not found for the address given in <i>Address</i>.

</td>
</tr>
</table>

## -remarks

A miniport driver will call this routine to register the unit attributes with Storport during completion of an SRB containing a SCSIOP_INQUIRY command request.  The bitfields in <i>attributes</i> are set based on the data returned from the adapter for the inquiry command. Storport will issue an inquiry for the unit at <i>Address</i> during a bus enumeration.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_stor_address">STOR_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_unit_attributes">STOR_UNIT_ATTRIBUTES</a>

