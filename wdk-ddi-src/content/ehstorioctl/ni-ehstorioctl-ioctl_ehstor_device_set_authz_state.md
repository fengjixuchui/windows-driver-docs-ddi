---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE
title: IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE (ehstorioctl.h)
description: This IOCTL is used to inform the owning driver for the IEEE 1667 device PDOs that the authorization state has changed.
old-location: storage\ioctl_ehstor_device_set_authz_state.htm
tech.root: storage
ms.assetid: 8C71F597-2141-4DA6-8A14-8B10CB69E5CC
ms.date: 03/29/2018
ms.keywords: IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE, IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE control, IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE, storage.ioctl_ehstor_device_set_authz_state
ms.topic: ioctl
f1_keywords:
 - "ehstorioctl/IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE"
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- EhStorIoctl.h
api_name:
- IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE IOCTL


## -description


This IOCTL is used to inform the owning driver for the IEEE 1667 device PDOs that the authorization state has changed. The owning driver may choose to change the state of the disk PDO in response to this IOCTL. In the case of<i> EhStorClass.sys</i>, the disk PDO is added or removed based on the authorization value in the input buffer of this IOCTL. Typically this IOCTL is issued by a UMDF authentication silo driver, such as the password or certificate driver, immediately following a successful silo operation which has changed the authentication state of the silo.


## -ioctlparameters




### -input-buffer

The input buffer at Irp->AssociatedIrp.SystemBuffer must contain a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ns-ehstorioctl-tagact_authz_state">ACT_AUTHZ_STATE</a>.


### -input-buffer-length

The length of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ns-ehstorioctl-tagact_authz_state">ACT_AUTHZ_STATE</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

One of the following values may be returned in the Status field:


<dl>
<dd>
STATUS_SUCCESS - The authorization state for the ACT was successfully set according to the data contained in the input buffer.

</dd>
</dl>



<dl>
<dd>
STATUS_INVALID_BUFFER_SIZE - The input buffer length supplied is of incorrect size.

</dd>
</dl>


