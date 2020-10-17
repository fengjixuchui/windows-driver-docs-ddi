---
UID: NI:ntddcdvd.IOCTL_AACS_START_SESSION
title: IOCTL_AACS_START_SESSION (ntddcdvd.h)
description: Retrieves an Authentication Grant Identifier (AGID) that identifies a secure session.
old-location: storage\ioctl_aacs_start_session.htm
tech.root: storage
ms.assetid: b5fb5dac-7f63-4457-bb25-61315395429b
ms.date: 03/29/2018
keywords: ["IOCTL_AACS_START_SESSION IOCTL"]
ms.keywords: IOCTL_AACS_START_SESSION, IOCTL_AACS_START_SESSION control, IOCTL_AACS_START_SESSION control code [Storage Devices], k307_a9378e49-2d39-4532-bac7-5fe9612ea5d0.xml, ntddcdvd/IOCTL_AACS_START_SESSION, storage.ioctl_aacs_start_session
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_AACS_START_SESSION
 - ntddcdvd/IOCTL_AACS_START_SESSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_AACS_START_SESSION
---

# IOCTL_AACS_START_SESSION IOCTL


## -description

Retrieves an Authentication Grant Identifier (AGID) that identifies a secure session.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a value of type <a href="/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session.

### -output-buffer-length

Length of a <a href="/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.

## -remarks

The IOCTL_AACS_START_SESSION request corresponds to one of the steps of the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth). For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

After obtaining the AGID, host software uses the AGID to associate subsequent AACS IOCTLs with the secure session. Unlike the AGID that is used with DVD Content-Scrambling System (CSS) encryption, the AACS AGID is valid for the transfer of only one piece of protected information.