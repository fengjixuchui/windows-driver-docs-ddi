---
UID: NF:ursdevice.UrsSetHardwareEventSupport
title: UrsSetHardwareEventSupport function (ursdevice.h)
description: Indicates the client driver's support for reporting new hardware events.
old-location: buses\urssethardwareeventsupport.htm
tech.root: usbref
ms.assetid: 905BA306-29A5-4AAB-BA30-6B459E0062F6
ms.date: 05/07/2018
keywords: ["UrsSetHardwareEventSupport function"]
ms.keywords: UrsSetHardwareEventSupport, UrsSetHardwareEventSupport function [Buses], buses.urssethardwareeventsupport, ursdevice/UrsSetHardwareEventSupport
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UrsSetHardwareEventSupport
 - ursdevice/UrsSetHardwareEventSupport
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Urscxstub.lib
 - Urscxstub.dll
api_name:
 - UrsSetHardwareEventSupport
---

# UrsSetHardwareEventSupport function


## -description

Indicates the client driver's support for reporting new hardware events.

## -parameters

### -param Device 

[in]
A handle to the framework device object that the client driver retrieved in the previous call to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

### -param HardwareEventReportingSupported 

[in]
A boolean value that indicates support for  reporting hardware events. 

TRUE indicates the client driver will report hardware events by calling <a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursreporthardwareevent">UrsReportHardwareEvent</a>. 

FALSE indicates hardware event reporting is not handled by the client driver.

## -remarks

Before the client driver can report hardware events, the client driver for the dual-role controller must indicate to the class extension that the driver supports hardware events by calling this method. Typically, the driver calls <b>UrsSetHardwareEventSupport</b> in the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function. The driver must not call this method after <i>EvtDevicePrepareHardware</i> has returned. Otherwise, the method fails and a break is issued if <a href="/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> is enabled.

For certain controllers, the client driver might not support role detection before performing a role switch operation. In that case, the client driver must  set  <i>HardwareEventReportingSupported</i> to FALSE.  The operating system manages the role of the controller.

Otherwise, if the driver supports role detection, it must set  <i>HardwareEventReportingSupported</i> to TRUE.  This indicates to the class extension that the client driver will  handle hardware events, such as ID pin interrupts, and report to the class extension that the role needs to be changed. The driver can report events by calling <a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursreporthardwareevent">UrsReportHardwareEvent</a>.


#### Examples


```

EVT_WDF_DEVICE_PREPARE_HARDWARE EvtDevicePrepareHardware;


NTSTATUS
EvtDevicePrepareHardware (
    _In_ WDFDEVICE Device,
    _In_ WDFCMRESLIST ResourcesRaw,
    _In_ WDFCMRESLIST ResourcesTranslated
    )
{
    ULONG resourceCount;
    BOOLEAN hasHardwareEventSupport;

    UNREFERENCED_PARAMETER(ResourcesRaw);


    TRY {


        resourceCount = WdfCmResourceListGetCount(ResourcesTranslated);

        ...

        // DetermineHardwareEventSupport determines support by inspecting resources.
        // Implementation not shown.
        hasHardwareEventSupport = DetermineHardwareEventSupport(ResourcesRaw);


        UrsSetHardwareEventSupport(Device, hasHardwareEventSupport);

        if (hasHardwareEventSupport) {
            UrsReportHardwareEvent(Device, UrsHardwareEventIdGround);
        }

        ... 

    } FINALLY {
    }


    return STATUS_SUCCESS;
}
```


## -see-also

<a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursreporthardwareevent">UrsReportHardwareEvent</a>