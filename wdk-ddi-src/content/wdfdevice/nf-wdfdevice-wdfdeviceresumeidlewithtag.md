---
UID: NF:wdfdevice.WdfDeviceResumeIdleWithTag
title: WdfDeviceResumeIdleWithTag macro (wdfdevice.h)
description: The WdfDeviceResumeIdleWithTag macro decrements the power reference count for a specified framework device object and assigns the driver's current file name and line number to the reference. The macro also assigns a tag value to the reference.
tech.root: wdf
ms.assetid: 065393BE-CEDF-4B82-AE43-844DDB932DF0
ms.date: 02/26/2018
keywords: ["WdfDeviceResumeIdleWithTag macro"]
ms.keywords: DFDeviceObjectGeneralRef_6078e8e8-7d4e-4714-a1b4-74fc973a678c.xml, WdfDeviceResumeIdleWithTag, WdfDeviceResumeIdleWithTag method, kmdf.WdfDeviceResumeIdleWithTag, wdf.WdfDeviceResumeIdleWithTag, wdfdevice/WdfDeviceResumeIdleWithTag
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceResumeIdleWithTag
 - wdfdevice/WdfDeviceResumeIdleWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfDeviceResumeIdleWithTag
---

# WdfDeviceResumeIdleWithTag macro


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The **WdfDeviceResumeIdleWithTag** macro decrements the power reference count for a specified framework device object and assigns the driver's current file name and line number to the reference. The macro also assigns a tag value to the reference.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Tag 

[in]
A driver-defined value that the framework stores as an identification tag for the power reference.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.


If the object's reference count becomes zero, the object might be deleted before **WdfDeviceResumeIdleWithTag** returns.

Calling **WdfDeviceResumeIdleWithTag** instead of [**WdfDeviceResumeIdle**](./nf-wdfdevice-wdfdeviceresumeidle.md) provides additional information (tag value, line number, and file name) that you can view in Microsoft debuggers. **WdfDeviceResumeIdleWithTag** uses the driver's current line number and file name.

You can view the tag, line number, and file name values by using the [**!wdfkd.wdftagtracker**](/windows-hardware/drivers/debugger/-wdfkd-wdftagtracker) debugger extension.

Use [**!wdfkd.wdfdevice**](/windows-hardware/drivers/debugger/-wdfkd-wdfdevice) with verbose flags on and locate the link to [**!wdftagtracker**](/windows-hardware/drivers/debugger/-wdfkd-wdftagtracker) in the output:

```cpp
kd> !wdfdevice <handle> f 
```

## -see-also

[Debugging Power Reference Leaks in WDF](/windows-hardware/drivers/wdf/debugging-power-reference-leaks-in-wdf)

[**WdfDeviceResumeIdle**](./nf-wdfdevice-wdfdeviceresumeidle.md)

[**WdfDeviceStopIdle**](./nf-wdfdevice-wdfdevicestopidle.md)

[**WdfDeviceStopIdleWithTag**](./nf-wdfdevice-wdfdevicestopidlewithtag.md)