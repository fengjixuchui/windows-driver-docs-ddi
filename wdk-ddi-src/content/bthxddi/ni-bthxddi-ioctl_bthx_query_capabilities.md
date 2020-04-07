---
UID: NI:bthxddi.IOCTL_BTHX_QUERY_CAPABILITIES
title: IOCTL_BTHX_QUERY_CAPABILITIES (bthxddi.h)
description: IOCTL_BTHX_QUERY_CAPABILITIES is used to query the capabilities of the transport driver.
old-location: bltooth\ioctl_bthx_query_capabilities.htm
tech.root: bltooth
ms.assetid: 199C93EC-AB91-47F1-914A-F44BFF1796A6
ms.date: 04/27/2018
keywords: ["IOCTL_BTHX_QUERY_CAPABILITIES IOCTL"]
ms.keywords: IOCTL_BTHX_QUERY_CAPABILITIES, IOCTL_BTHX_QUERY_CAPABILITIES control, IOCTL_BTHX_QUERY_CAPABILITIES control code [Bluetooth Devices], bltooth.ioctl_bthx_query_capabilities, bthxddi/IOCTL_BTHX_QUERY_CAPABILITIES
f1_keywords:
 - "bthxddi/IOCTL_BTHX_QUERY_CAPABILITIES"
req.header: bthxddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- BthXDDI.h
api_name:
- IOCTL_BTHX_QUERY_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHX_QUERY_CAPABILITIES IOCTL


## -description



IOCTL_BTHX_QUERY_CAPABILITIES is used to query the capabilities of the transport driver.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthxddi/ns-bthxddi-_bthx_capabilities">BTHX_CAPABILITIES</a> structure. 


### -output-buffer-length

The length of the buffer is the size of the <b>BTHX_CAPABILITIES</b> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size of the structure.

The 
      <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
</table>
 


## -remarks



During startup, the Bluetooth stack sends IOCTL_BTHX_QUERY_CAPABILITIES to query the capabilities of the transport driver.

This is a synchrononous call and failure of this IOCTL prevents Windows from loading the Bluetooth stack.

The output buffer of this IOCTL is defined by the BTHX_CAPABILITIES structure.

The <b>MaxScoChannels</b> member must be set to 1. The <b>ScoSupport</b> member must be set to <b>ScoSupportHCIBypass</b>. Failure to do so prevents the stack from being loaded.



