---
UID: NC:video.PVIDEO_HW_FIND_ADAPTER
title: PVIDEO_HW_FIND_ADAPTER (video.h)
description: HwVidFindAdapter performs initialization of data specific to the miniport driver and devices supported by the miniport driver.
old-location: display\hwvidfindadapter.htm
tech.root: display
ms.assetid: 8c880eff-4b4c-439e-9239-f2343c1fe084
ms.date: 05/10/2018
keywords: ["PVIDEO_HW_FIND_ADAPTER callback function"]
ms.keywords: HwVidFindAdapter, HwVidFindAdapter callback function [Display Devices], PVIDEO_HW_FIND_ADAPTER, PVIDEO_HW_FIND_ADAPTER callback, VideoMiniport_Functions_f035d610-08b2-4403-b9dc-c069520d61bb.xml, display.hwvidfindadapter, video/HwVidFindAdapter
f1_keywords:
 - "video/HwVidFindAdapter"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
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
- UserDefined
api_location:
- video.h
api_name:
- HwVidFindAdapter
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_HW_FIND_ADAPTER callback function


## -description


<i>HwVidFindAdapter</i> performs initialization of data specific to the miniport driver and devices supported by the miniport driver.


## -parameters




### -param HwDeviceExtension

Pointer to the driver's per-device storage area. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.


### -param HwContext

Is <b>NULL</b> and should be ignored by the miniport driver.


### -param ArgumentString

Pointer to a null-terminated ASCII string that originates with the user. This pointer can be <b>NULL</b>.


### -param ConfigInfo

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> structure. The video port driver allocates memory for and initializes this structure with any known configuration information, such as the system IO bus number and values that the miniport driver set in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure.


### -param Again

Should be ignored by the miniport driver.


## -returns



<i>HwVidFindAdapter</i> must return one of the following status codes:

|Return code|Description|
|--- |--- |
|ERROR_DEV_NOT_EXIST|Indicates, for a reenumerable bus, that the miniport driver could not find the device.|
|ERROR_INVALID_PARAMETER|Indicates the miniport driver could not configure or initialize the adapter successfully.|
|NO_ERROR|Indicates success.|

## -remarks

Every video miniport driver must have an <i>HwVidFindAdapter</i> function.

The video port driver does the following before it calls <i>HwVidFindAdapter</i>:

<ul>
<li>
Allocates storage for the miniport driver's per-adapter storage area according to the value of <b>HwDeviceExtensionSize</b> that the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure, and zero-initializes the allocated storage.

</li>
<li>
Allocates storage for a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> structure and fills in all available information based on miniport driver-supplied information in VIDEO_HW_INITIALIZATION_DATA.

</li>
</ul>
The video port driver then calls the miniport driver's <i>HwVidFindAdapter</i> function with pointers to the initialized per-adapter storage area and configuration information in the <i>HwDeviceExtension</i> and <i>ConfigInfo</i> parameters, respectively.

The <i>HwVidFindAdapter</i> function for devices on an enumerable bus must do the following:

<ul>
<li>
Check the size of the VIDEO_PORT_CONFIG_INFO structure to which <i>ConfigInfo</i> points to ensure proper versioning.

</li>
<li>
Call <b>VideoPortGetAccessRanges</b> to obtain the bus-relative physical addresses to which the device will respond. These addresses are assigned by the PnP manager. The miniport driver should pass <b>NULL</b> in the <i>VendorId</i>, <i>DeviceId</i>, and <i>Slot</i> parameters of <b>VideoPortGetAccessRanges</b>.

</li>
<li>
For miniport drivers that support several device types, determine the type of device that the PnP manager has detected. The miniport driver can call <b>VideoPortGetBusData</b> to obtain PCI configuration information.

</li>
<li>
Fill in any relevant but missing configuration information in the appropriate members of the VIDEO_PORT_CONFIG_INFO structure with adapter-specific data.

</li>
</ul>
<i>HwVidFindAdapter</i> should not attempt to initialize the device.

<i>HwVidFindAdapter</i> can allocate resources, such as memory and locks, for use by the miniport driver. Those resources can be device-specific or they can be shared by several devices that the miniport driver supports. If <i>HwVidFindAdapter</i> returns any value other than NO_ERROR, it must free all device-specific resources before returning. For resources that are shared among several devices, <i>HwVidFindAdapter</i> should keep a reference count. For example, the reference count could indicate the number of previous calls to <i>HwVidFindAdapter</i> that succeeded. That way, if <i>HwVidFindAdapter</i> must fail, and it determines that all previous calls to <i>HwVidFindAdapter</i> have failed, it could free the shared resources.

If <i>HwVidFindAdapter</i> fails every time it is called by the video port driver, the operating system might unload the miniport driver later. In such a case, any resources that <i>HwVidFindAdapter</i> allocated but did not free will leak.

For a device on a reenumerable bus such as ISA, PnP still attempts to start the device, although it is the responsibility of <i>HwVidFindAdapter</i> to determine whether the device is actually present. If the device is not found, <i>HwVidFindAdapter</i> should return ERROR_DEV_NOT_EXIST.

<i>HwVidFindAdapter</i> should also call <b>VideoPortSetRegistryParameters</b> to store adapter-specific information in the <b>HardwareInformation</b> key. This information is used by the Display program in Control Panel. See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/setting-hardware-information-in-the-registry">Setting Hardware Information in the Registry</a> for details.

Depending on the adapter and the <b>AdapterInterfaceType</b> value in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>, <i>HwVidFindAdapter</i> can call some of the following <b>VideoPort</b><i>Xxx</i> functions to get the necessary bus-relative configuration data and mapped access ranges to communicate with the adapter:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetbusdata">VideoPortGetBusData</a> to get bus-type-specific configuration information about an adapter on a particular I/O bus.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicedata">VideoPortGetDeviceData</a> to get VIDEO_DEVICE_DATA_TYPE-specific information from the registry and call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_query_device_routine">HwVidQueryDeviceCallback</a> to process this information.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetregistryparameters">VideoPortGetRegistryParameters</a> to get configuration information from the registry.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a> to get bus-relative access ranges addresses and possibly other hardware configuration values, and to claim them in the registry for use by the driver of an adapter.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a> to determine whether bus-relative video memory and/or I/O ports for the adapter can be claimed by the miniport driver; otherwise, a previously loaded driver has already claimed the resource in the registry and <i>HwVidFindAdapter</i> must try to claim other access ranges if possible or fail.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a> to map each successfully claimed bus-relative base address and range size, as described in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_access_range">VIDEO_ACCESS_RANGE</a> structure, to <a href="https://docs.microsoft.com/windows-hardware/drivers/">system space</a> logical addresses. <i>HwVidFindAdapter</i> must successfully call <b>VideoPortVerifyAccessRanges</b> or <b>VideoPortGetAccessRanges</b> before it can call <b>VideoPortGetDeviceBase</b>.

</li>
</ul>
If the driver does not handle interrupts, <i>HwVidFindAdapter</i> should set both <b>BusInterruptLevel</b> and <b>BusInterruptVector</b> in the VIDEO_PORT_CONFIG_INFO structure to zero after its call to <b>VideoPortGetAccessRanges</b>. If both members are zero, the video port driver does not connect the interrupt for the miniport driver. Explicitly setting both <b>BusInterruptLevel</b> and <b>BusInterruptVector</b> to zero in <i>HwVidFindAdapter</i> disables the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> entry point, if any, that was set up by the miniport driver's <b>DriverEntry</b> routine.

<i>HwVidFindAdapter</i> must not leave an unsupported adapter with its state changed. For VGA/SVGA adapters, <i>HwVidFindAdapter</i> must leave the adapter in a VGA state and restore any extended registers it might have modified to their original condition.

<i>HwVidFindAdapter</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/display/driverentry-of-video-miniport-driver">DriverEntry of Video Miniport Driver</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvassertmode">DrvAssertMode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_query_device_routine">HwVidQueryDeviceCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_get_registry_routine">HwVidQueryNamedValueCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportfreedevicebase">VideoPortFreeDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetbusdata">VideoPortGetBusData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicedata">VideoPortGetDeviceData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetregistryparameters">VideoPortGetRegistryParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a>
 

 

