---
UID: NF:wdfdevice.WdfDeviceRemoveRemovalRelationsPhysicalDevice
title: WdfDeviceRemoveRemovalRelationsPhysicalDevice function (wdfdevice.h)
description: The WdfDeviceRemoveRemovalRelationsPhysicalDevice method removes a specified device from the list of devices that must be removed when another specified device is removed.
old-location: wdf\wdfdeviceremoveremovalrelationsphysicaldevice.htm
tech.root: wdf
ms.assetid: f9b50dc2-1af7-47c3-87c6-d33858569eed
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_aad4d605-26bb-468f-a608-426a1e570037.xml, WdfDeviceRemoveRemovalRelationsPhysicalDevice, WdfDeviceRemoveRemovalRelationsPhysicalDevice method, kmdf.wdfdeviceremoveremovalrelationsphysicaldevice, wdf.wdfdeviceremoveremovalrelationsphysicaldevice, wdfdevice/WdfDeviceRemoveRemovalRelationsPhysicalDevice
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceRemoveRemovalRelationsPhysicalDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceRemoveRemovalRelationsPhysicalDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceRemoveRemovalRelationsPhysicalDevice</b> method removes a specified device from the list of devices that must be removed when another specified device is removed. 


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PhysicalDevice [in]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents a physical device object (PDO).


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceaddremovalrelationsphysicaldevice">WdfDeviceAddRemovalRelationsPhysicalDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceclearremovalrelationsdevices">WdfDeviceClearRemovalRelationsDevices</a>
 

 

