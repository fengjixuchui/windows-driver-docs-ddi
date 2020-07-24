---
UID: NI:bthioctl.IOCTL_BTH_DISCONNECT_DEVICE
title: IOCTL_BTH_DISCONNECT_DEVICE (bthioctl.h)
description: Profile drivers use IOCTL_BTH_DISCONNECT_DEVICE to request the operating system to disconnect the specified remote device.
old-location: bltooth\ioctl_bth_disconnect_device.htm
tech.root: bltooth
ms.assetid: 03c7f389-60a4-4c98-881d-a58926644275
ms.date: 04/27/2018
keywords: ["IOCTL_BTH_DISCONNECT_DEVICE IOCTL"]
ms.keywords: IOCTL_BTH_DISCONNECT_DEVICE, IOCTL_BTH_DISCONNECT_DEVICE control, IOCTL_BTH_DISCONNECT_DEVICE control code [Bluetooth Devices], bltooth.ioctl_bth_disconnect_device, bth_ioctls_03f58c9a-06b9-45b9-b817-3ef86058af5e.xml, bthioctl/IOCTL_BTH_DISCONNECT_DEVICE
f1_keywords:
 - "bthioctl/IOCTL_BTH_DISCONNECT_DEVICE"
 - "IOCTL_BTH_DISCONNECT_DEVICE"
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthioctl.h
api_name:
- IOCTL_BTH_DISCONNECT_DEVICE
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_DISCONNECT_DEVICE IOCTL


## -description



Profile drivers use IOCTL_BTH_DISCONNECT_DEVICE to request the operating system to disconnect the
     specified remote device.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains the address of the remote device to disconnect
      from.


### -input-buffer-length

The length of the address in the buffer.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to zero because the Bluetooth driver
      stack returns no data with this IOCTL.

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
<tr>
<td>
STATUS_DEVICE_NOT_CONNECTED

</td>
<td>
The specified remote device is not connected.

</td>
</tr>
</table>
 


## -remarks



Calling IOCTL_BTH_DISCONNECT_DEVICE forces a disconnect from the remote device without regard to the
    state of any L2CAP and SCO connections. All active SCO connections will be disconnected before the ACL
    connection is disconnected. Pending data transfers might fail.



