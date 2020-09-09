---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_SET_INDICATOR
title: IOCTL_BIOMETRIC_SET_INDICATOR (winbio_ioctl.h)
description: The IOCTL_BIOMETRIC_SET_INDICATOR IOCTL directs the driver to update the status of the indicator light.
old-location: biometric\ioctl_biometric_set_indicator.htm
tech.root: biometric
ms.assetid: 5aaaf178-a137-4a98-a77f-b426514a8cd9
ms.date: 02/20/2018
keywords: ["IOCTL_BIOMETRIC_SET_INDICATOR IOCTL"]
ms.keywords: IOCTL_BIOMETRIC_SET_INDICATOR, IOCTL_BIOMETRIC_SET_INDICATOR control, IOCTL_BIOMETRIC_SET_INDICATOR control code [Biometric Devices], biometric.ioctl_biometric_set_indicator, biometric_ref_46e6f908-83fd-4e5b-9cc4-183da4f178d2.xml, winbio_ioctl/IOCTL_BIOMETRIC_SET_INDICATOR
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
 - IOCTL_BIOMETRIC_SET_INDICATOR
 - winbio_ioctl/IOCTL_BIOMETRIC_SET_INDICATOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winbio_ioctl.h
api_name:
 - IOCTL_BIOMETRIC_SET_INDICATOR
---

# IOCTL_BIOMETRIC_SET_INDICATOR IOCTL


## -description

The IOCTL_BIOMETRIC_SET_INDICATOR IOCTL directs the driver to update the status of the indicator light.  The light can be turned on or off.  This IOCTL is optional.This IOCTL must be implemented if the driver supports the WINBIO_CAPABILITY_INDICATOR capability.

## -ioctlparameters

### -input-buffer

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_set_indicator">WINBIO_SET_INDICATOR</a>

### -input-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_set_indicator">WINBIO_SET_INDICATOR</a> structure.

### -output-buffer

The AssociatedIrp.SystemBuffer member points to a buffer that contains a WINBIO_BLANK_PAYLOAD structure.

### -output-buffer-length

The smallest valid output buffer size is the size of DWORD.  If the driver receives an DWORD-sized output buffer, the driver should return the buffer size necessary for the requested operation.

### -in-out-buffer

### -inout-buffer-length

### -status-block

Indicates whether the DeviceIoControl call to the driver completed and the OUT payload is valid.

The <b>Status</b> member is set to one of the values in the following table.

|Status value|Description|
|--- |--- |
|S_OK, STATUS_SUCCESS|The operation completed successfully.  If the size of data returned is DWORD, the payload contains the size of the buffer necessary for the call.  Otherwise, the payload contains the full output buffer.|
|E_INVALIDARG|The parameters were not specified correctly.|
|E_UNKNOWN|Any other failure that prevents the payload from being filled in.|
|E_UNEXPECTED|Any other failure that prevents the payload from being filled in.|
|E_FAIL|Any other failure that prevents the payload from being filled in.|

## -remarks

If the vendor-supplied driver passes back the entire payload, it should fill in the WinBioHresult member of WINBIO_BLANK_PAYLOAD with the status of the biometric operation.

Possible values include:

