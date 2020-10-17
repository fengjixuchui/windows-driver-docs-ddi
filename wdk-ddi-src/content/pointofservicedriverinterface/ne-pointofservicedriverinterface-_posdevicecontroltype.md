---
UID: NE:pointofservicedriverinterface._PosDeviceControlType
title: _PosDeviceControlType (pointofservicedriverinterface.h)
description: This enumeration defines values for the IOCTLs of the scanner driver and magnetic stripe reader (MSR) driver.
old-location: pos\posdevicecontroltype.htm
tech.root: pos
ms.assetid: 9f5f3baa-49a0-4711-88c0-b9ff8d87ae1d
ms.date: 02/23/2018
keywords: ["PosDeviceControlType enumeration"]
ms.keywords: BarcodeScannerInjectEvent, CheckHealth, ClaimDevice, GetDeviceBasics, GetProperty, Invalid, MsrAuthenticateDevice, MsrDeAuthenticateDevice, MsrRetrieveDeviceAuthentication, MsrUpdateKey, PosDeviceControlType, PosDeviceControlType enumeration, ReleaseDevice, ResetStatistics, RetainDevice, RetrieveStatistics, SetProperty, UpdateStatistics, _MaxDeviceControlType, _PosDeviceControlType, pointofservicedriverinterface/BarcodeScannerInjectEvent, pointofservicedriverinterface/CheckHealth, pointofservicedriverinterface/ClaimDevice, pointofservicedriverinterface/GetDeviceBasics, pointofservicedriverinterface/GetProperty, pointofservicedriverinterface/Invalid, pointofservicedriverinterface/MsrAuthenticateDevice, pointofservicedriverinterface/MsrDeAuthenticateDevice, pointofservicedriverinterface/MsrRetrieveDeviceAuthentication, pointofservicedriverinterface/MsrUpdateKey, pointofservicedriverinterface/PosDeviceControlType, pointofservicedriverinterface/ReleaseDevice, pointofservicedriverinterface/ResetStatistics, pointofservicedriverinterface/RetainDevice, pointofservicedriverinterface/RetrieveStatistics, pointofservicedriverinterface/SetProperty, pointofservicedriverinterface/UpdateStatistics, pointofservicedriverinterface/_MaxDeviceControlType, pos.posdevicecontroltype
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
req.typenames: PosDeviceControlType
f1_keywords:
 - _PosDeviceControlType
 - pointofservicedriverinterface/_PosDeviceControlType
 - PosDeviceControlType
 - pointofservicedriverinterface/PosDeviceControlType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - PosDeviceControlType
---

# _PosDeviceControlType enumeration


## -description

This enumeration defines values for the IOCTLs of the scanner driver and magnetic stripe reader (MSR) driver.

## -enum-fields

### -field _MinDeviceControlType

### -field Invalid

The event code is not valid.

### -field GetProperty

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_get_property">IOCTL_POINT_OF_SERVICE_GET_PROPERTY</a>.

### -field SetProperty

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_set_property">IOCTL_POINT_OF_SERVICE_SET_PROPERTY</a>.

### -field ClaimDevice

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device">IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE</a>.

### -field ReleaseDevice

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_release_device">IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE</a>.

### -field RetainDevice

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_retain_device">IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE</a>.

### -field RetrieveStatistics

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics">IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS</a>.

### -field ResetStatistics

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_reset_statistics">IOCTL_POINT_OF_SERVICE_RESET_STATISTICS</a>.

### -field UpdateStatistics

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics">IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS</a>.

### -field CheckHealth

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_check_health">IOCTL_POINT_OF_SERVICE_CHECK_HEALTH</a>.

### -field GetDeviceBasics

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_get_device_basics">IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS</a>.

### -field BarcodeScannerInjectEvent

Unused.

### -field MsrRetrieveDeviceAuthentication

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_msr_retrieve_device_authentication">IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION</a>.

### -field MsrAuthenticateDevice

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_msr_authenticate_device">IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE</a>.

### -field MsrDeAuthenticateDevice

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_msr_deauthenticate_device">IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE</a>.

### -field MsrUpdateKey

Represents <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_msr_update_key">IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY</a>.

### -field StartBarcodeScannerSoftwareTrigger

### -field StopBarcodeScannerSoftwareTrigger

### -field PrinterClearOutput

### -field PrinterSlipWaitForPaperInserted

### -field PrinterSlipWaitForPaperRemoved

### -field PrinterChangePrintSide

### -field PrinterCutPaper

### -field PrinterDrawRuledLine

### -field PrinterSlipOpenJaws

### -field PrinterSlipCloseJaws

### -field PrinterMarkFeed

### -field PrinterPageModePrint

### -field PrinterPrintBarcode

### -field PrinterPrintMemoryBitmapStart

### -field PrinterPrintMemoryBitmapFill

### -field PrinterPrintNormal

### -field PrinterRotatePrint

### -field PrinterSetBitmapStart

### -field PrinterSetBitmapFill

### -field PrinterTransactionPrint

### -field PrinterValidateData

### -field PrinterPrintSavedBitmap

### -field CashDrawerOpenDrawer

### -field CashDrawerCreateDrawerCloseAlarm

### -field CashDrawerCancelWait

### -field ConnectRemotePosDevice

### -field PrinterWaitForJobComplete

### -field LineDisplayCreateWindow

### -field LineDisplayDestroyWindow

### -field LineDisplayRefreshWindow

### -field LineDisplayWindowDisplayText

### -field LineDisplayWindowDisplayTextAt

### -field LineDisplayWindowScrollText

### -field LineDisplayWindowClearText

### -field LineDisplayWindowDisplayBitmap

### -field LineDisplaySetBitmap

### -field LineDisplaySetDescriptor

### -field LineDisplayClearDescriptors

### -field LineDisplayDefineGlyph

### -field LineDisplayReadCharacterAtCursor

### -field BarcodeScannerGetSymbologyAttributes

### -field BarcodeScannerSetSymbologyAttributes

### -field _MaxDeviceControlType

## -remarks

This enumeration provides values for each IOCTL that you can send to the device driver. It is a convenient way to indicate which IOCTL to dispatch when calling functions like **SendDeviceCommand()**.