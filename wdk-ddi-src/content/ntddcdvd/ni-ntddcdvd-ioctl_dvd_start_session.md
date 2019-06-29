---
UID: NI:ntddcdvd.IOCTL_DVD_START_SESSION
title: IOCTL_DVD_START_SESSION (ntddcdvd.h)
description: Returns an authentication grant ID (AGID) as a DVD session ID, which a caller must pass to the device in all subsequent operations in a DVD session.
old-location: storage\ioctl_dvd_start_session.htm
tech.root: storage
ms.assetid: a4010756-b230-4e49-85a4-498f5ebcf785
ms.date: 03/29/2018
ms.keywords: IOCTL_DVD_START_SESSION, IOCTL_DVD_START_SESSION control, IOCTL_DVD_START_SESSION control code [Storage Devices], k307_e26336f9-b482-4340-8315-cd8771c5bb81.xml, ntddcdvd/IOCTL_DVD_START_SESSION, storage.ioctl_dvd_start_session
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
- Ntddcdvd.h
api_name:
- IOCTL_DVD_START_SESSION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DVD_START_SESSION IOCTL


## -description



Returns an authentication grant ID (AGID) as a DVD session ID, which a caller must pass to the device in all subsequent operations in a DVD session.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns an integer authentication grant ID of type DVD_SESSION_ID in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

Length of a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(DVD_SESSION_ID). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.

