---
UID: NF:wdm.IoWMIDeviceObjectToProviderId
title: IoWMIDeviceObjectToProviderId function (wdm.h)
description: The IoWMIDeviceObjectToProviderId routine translates the specified device object into the corresponding WMI Provider ID.
old-location: kernel\iowmideviceobjecttoproviderid.htm
tech.root: kernel
ms.assetid: 211d41ae-18d3-4ca5-b9f5-868d97fab6fb
ms.date: 04/30/2018
keywords: ["IoWMIDeviceObjectToProviderId function"]
ms.keywords: IoWMIDeviceObjectToProviderId, IoWMIDeviceObjectToProviderId routine [Kernel-Mode Driver Architecture], k104_e24ce1c2-9f90-49b5-88be-1bbf40074aee.xml, kernel.iowmideviceobjecttoproviderid, wdm/IoWMIDeviceObjectToProviderId
f1_keywords:
 - "wdm/IoWMIDeviceObjectToProviderId"
 - "IoWMIDeviceObjectToProviderId"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoWMIDeviceObjectToProviderId
targetos: Windows
req.typenames: 
---

# IoWMIDeviceObjectToProviderId function


## -description


The <b>IoWMIDeviceObjectToProviderId</b> routine translates the specified device object into the corresponding WMI Provider ID.


## -parameters




### -param DeviceObject [in]

Pointer to a device object. 


## -returns



<b>IoWMIDeviceObjectToProviderId </b>returns the WMI Provider ID associated with the specified device object.




## -remarks



<b>IoWMIDeviceObjectToProviderId</b> should be used when filling in the <b>ProviderId</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a> structure in those cases when the <b>WNODEHEADER</b> structure is being initialized as part of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_reference">WNODE_EVENT_REFERENCE</a> structure. (If the <b>WNODE_HEADER</b> is being used for other purposes, <i>ProviderId</i> is reserved.)

When running on a 32-bit operating system, the provider ID and the device object are identical. When running on a 64-bit operating system, <b>IoWMIDeviceObjectToProviderId</b> will convert the 64-bit device object to a 32-bit provider ID.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_reference">WNODE_EVENT_REFERENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a>
 

 

