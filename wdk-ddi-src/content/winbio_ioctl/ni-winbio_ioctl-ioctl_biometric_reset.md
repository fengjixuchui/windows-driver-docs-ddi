---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_RESET
title: IOCTL_BIOMETRIC_RESET (winbio_ioctl.h)
description: The IOCTL_BIOMETRIC_RESET IOCTL resets the device to a known or idle state, according to the current power state. Vendor-supplied WBDI drivers must support this IOCTL.
old-location: biometric\ioctl_biometric_reset.htm
tech.root: biometric
ms.assetid: 4385911b-ae38-4748-ad11-cc161922776a
ms.date: 02/20/2018
keywords: ["IOCTL_BIOMETRIC_RESET IOCTL"]
ms.keywords: IOCTL_BIOMETRIC_RESET, IOCTL_BIOMETRIC_RESET control, IOCTL_BIOMETRIC_RESET control code [Biometric Devices], biometric.ioctl_biometric_reset, biometric_ref_4043b840-5b38-40b2-bd80-282a28badd14.xml, winbio_ioctl/IOCTL_BIOMETRIC_RESET
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
 - IOCTL_BIOMETRIC_RESET
 - winbio_ioctl/IOCTL_BIOMETRIC_RESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winbio_ioctl.h
api_name:
 - IOCTL_BIOMETRIC_RESET
---

# IOCTL_BIOMETRIC_RESET IOCTL


## -description

The IOCTL_BIOMETRIC_RESET IOCTL resets the device to a known or idle state, according to the current power state.  Vendor-supplied WBDI drivers must support this IOCTL.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_blank_payload">WINBIO_BLANK_PAYLOAD</a> structure.

### -output-buffer-length

The length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_blank_payload">WINBIO_BLANK_PAYLOAD</a> structure.

The vendor-supplied driver can optionally return a DWORD-sized buffer that specifies the buffer size necessary for the requested operation.

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

IOCTL_BIOMETRIC_RESET cancels a data collection IOCTL, if one is pending.  If there is a vendor-specific operation in progress, the driver should cancel the operation and reset the device whenever possible. 

If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of WINBIO_BLANK_PAYLOAD with the status of the Biometric operation.

