---
UID: NI:nfcsedev.IOCTL_NFCSE_GET_ROUTING_TABLE
title: IOCTL_NFCSE_GET_ROUTING_TABLE (nfcsedev.h)
description: Returns information regarding the current configuration of listen mode routing table.
old-location: nfpdrivers\ioctl_nfcse_get_routing_table.htm
tech.root: nfpdrivers
ms.assetid: 838D31E8-1835-47C7-8201-93910610F5EC
ms.date: 02/15/2018
keywords: ["IOCTL_NFCSE_GET_ROUTING_TABLE IOCTL"]
ms.keywords: IOCTL_NFCSE_GET_ROUTING_TABLE, IOCTL_NFCSE_GET_ROUTING_TABLE control, IOCTL_NFCSE_GET_ROUTING_TABLE control code [Near-Field Proximity Drivers], nfcsedev/IOCTL_NFCSE_GET_ROUTING_TABLE, nfpdrivers.ioctl_nfcse_get_routing_table
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
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
 - IOCTL_NFCSE_GET_ROUTING_TABLE
 - nfcsedev/IOCTL_NFCSE_GET_ROUTING_TABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfcsedev.h
api_name:
 - IOCTL_NFCSE_GET_ROUTING_TABLE
---

# IOCTL_NFCSE_GET_ROUTING_TABLE IOCTL


## -description

Returns information regarding the current configuration of listen mode routing table. Note that the caller must allocate an output buffer large enough to hold information regarding all the entries that are present in the current listen mode routing table, i.e. Total number of routing entries x Size of routing table entry, otherwise the driver should return a STATUS_BUFFER_OVERFLOW error code to the client with NumberOfEntries field containing the number of routing table entries configured. The routing table entry is of type SECURE_ELEMENT_ROUTING_TABLE_ENTRY. Note: The driver shouldn’t return entry routing NFC-DEP to DH as part of the routing table returned in the output buffer even though the entry is present in the NFCC routing table.

## -ioctlparameters

### -input-buffer

None

### -input-buffer-length

None

### -output-buffer

<a href="/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_routing_table"> SECURE_ELEMENT_ROUTING_TABLE</a> containing all currently configured routing entries.

### -output-buffer-length

sizeof(SECURE_ELEMENT_ROUTING_TABLE)

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td><b>STATUS_BUFFER_OVERFLOW</b></td>
<td>The buffer supplied was too small to receive the routing table configuration.</td>
</tr>
<tr>
<td><b>STATUS_FEATURE_NOT_SUPPORTED</b></td>
<td>The NFCC does not support listen mode routing configuration.
</td>
</tr>
<tr>
<td><b>STATUS_INVALID_PARAMETER</b></td>
<td>This code is returned if the input buffer is non-zero.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_DEVICE_STATE</b></td>
<td>This code is returned if the IOCTL is sent on a handle other than with relative name ‘SEManage’.
</td>
</tr>
</table>