---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_UPDATE_FIRMWARE
title: IOCTL_BIOMETRIC_UPDATE_FIRMWARE (winbio_ioctl.h)
description: The IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTL tells the driver to update the firmware for the device with the given firmware image. This IOCTL is optional.
old-location: biometric\ioctl_biometric_update_firmware.htm
tech.root: biometric
ms.assetid: 0337956a-09d0-4c9c-8f2d-ac63210431ba
ms.date: 02/20/2018
keywords: ["IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTL"]
ms.keywords: IOCTL_BIOMETRIC_UPDATE_FIRMWARE, IOCTL_BIOMETRIC_UPDATE_FIRMWARE control, IOCTL_BIOMETRIC_UPDATE_FIRMWARE control code [Biometric Devices], biometric.ioctl_biometric_update_firmware, biometric_ref_b94fa4b7-e1db-4cac-8c06-ff490ca39fd5.xml, winbio_ioctl/IOCTL_BIOMETRIC_UPDATE_FIRMWARE
f1_keywords:
 - "winbio_ioctl/IOCTL_BIOMETRIC_UPDATE_FIRMWARE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Winbio_ioctl.h
api_name:
- IOCTL_BIOMETRIC_UPDATE_FIRMWARE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTL


## -description


The IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTL tells the driver to update the firmware for the device with the given firmware image.  This IOCTL is optional. 


## -ioctlparameters




### -input-buffer


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_update_firmware">WINBIO_UPDATE_FIRMWARE</a>



### -input-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_update_firmware">WINBIO_UPDATE_FIRMWARE</a> structure.


### -output-buffer

The AssociatedIrp.SystemBuffer member points to a buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_blank_payload">WINBIO_BLANK_PAYLOAD</a> structure.


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



The firmware image is specific to each vendor and may contain both firmware data and any extra data that the driver needs to validate the image.

If the device has a different firmware update mechanism, the driver can return E_NOTIMPL for this IOCTL.

If the vendor-supplied driver passes back the entire payload, it should fill in the WinBioHresult member of WINBIO_BLANK_PAYLOAD with the status of the Biometric operation.

Possible values include:





