---
UID: NI:ntddcdvd.IOCTL_AACS_GENERATE_BINDING_NONCE
title: IOCTL_AACS_GENERATE_BINDING_NONCE (ntddcdvd.h)
description: Reads the Advanced Access Content System (AACS) binding nonce starting at the specified byte offset on the disc, as part of the protocol for writing to a protected data area.
old-location: storage\ioctl_aacs_generate_binding_nonce.htm
tech.root: storage
ms.assetid: bb0fec4e-e6be-46e1-b6be-253dd0579ca6
ms.date: 03/29/2018
keywords: ["IOCTL_AACS_GENERATE_BINDING_NONCE IOCTL"]
ms.keywords: IOCTL_AACS_GENERATE_BINDING_NONCE, IOCTL_AACS_GENERATE_BINDING_NONCE control, IOCTL_AACS_GENERATE_BINDING_NONCE control code [Storage Devices], k307_ff2a829d-24b6-4d74-92e4-18c342689db7.xml, ntddcdvd/IOCTL_AACS_GENERATE_BINDING_NONCE, storage.ioctl_aacs_generate_binding_nonce
f1_keywords:
 - "ntddcdvd/IOCTL_AACS_GENERATE_BINDING_NONCE"
 - "IOCTL_AACS_GENERATE_BINDING_NONCE"
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
- IOCTL_AACS_GENERATE_BINDING_NONCE
targetos: Windows
req.typenames: 
---

# IOCTL_AACS_GENERATE_BINDING_NONCE IOCTL


## -description


Reads the Advanced Access Content System (AACS) binding nonce starting at the specified byte offset on the disc, as part of the protocol for writing to a protected data area.


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_read_binding_nonce">AACS_READ_BINDING_NONCE</a> that specifies the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a>, the starting logical block address and the number of sectors for which the logical unit should generate a binding nonce.


### -input-buffer-length

Length of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_read_binding_nonce">AACS_READ_BINDING_NONCE</a>.


### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_binding_nonce">AACS_BINDING_NONCE</a> that specifies the binding nonce.


### -output-buffer-length

Length of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_binding_nonce">AACS_BINDING_NONCE</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks



The IOCTL_AACS_GENERATE_BINDING_NONCE request corresponds to the part of the AACS authentication protocol that is responsible for writing to a protected data area. For a complete description of this protocol, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

The IOCTL_AACS_GENERATE_BINDING_NONCE request requires a single available AGID during its processing, and the AGID is <b><i>not</i></b> automatically released after the request completes. The AGID remains valid until it is explicitly invalidated or until the drive generates a power-on reset, hard reset, or media ejection event. However, the AGID cannot be reused with other requests.

It is recommended that you wait for the completion of all other requests that use secure sessions with AGIDs before making an IOCTL_AACS_GENERATE_BINDING_NONCE request.

Clients that do not use file system support must set the <b>Handle</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_read_binding_nonce">AACS_READ_BINDING_NONCE</a> to INVALID_HANDLE_VALUE and specify explicit values for the <b>StartLBA</b> and <b>NumberOfSectors</b> members.



