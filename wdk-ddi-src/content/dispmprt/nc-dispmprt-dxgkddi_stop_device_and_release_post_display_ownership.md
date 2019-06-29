---
UID: NC:dispmprt.DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP
title: DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP (dispmprt.h)
description: Called by the operating system to request the display miniport driver to reset the display device and to release ownership of the current power-on self-test (POST) device.
old-location: display\dxgkddireleasepostdisplayownership.htm
tech.root: display
ms.assetid: 6AF170BF-C422-4340-8935-31A4D4F3EFA5
ms.date: 05/10/2018
ms.keywords: DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP, DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP callback, DxgkDdiStopDeviceAndReleasePostDisplayOwnership, DxgkDdiStopDeviceAndReleasePostDisplayOwnership callback function [Display Devices], display.dxgkddireleasepostdisplayownership, dispmprt/DxgkDdiStopDeviceAndReleasePostDisplayOwnership
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiStopDeviceAndReleasePostDisplayOwnership
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP callback function


## -description


Called by the operating system to request the display miniport driver to reset the  display device and to release ownership of the current  power-on self-test (POST)  device.

Starting with Windows 8, the operating system calls this function during a Plug and Play (PnP) stop operation.

To indicate to the operating system that this function is supported, the driver must set the <b>NonVGASupport</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function is called.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.




### -param TargetId [in]

A <b>D3DDDI_VIDEO_PRESENT_TARGET_ID</b> value that specifies the identifier of the video present target on the display adapter that the display device is connected to. This identifier could be for the target that was left in the current video present network (VidPN) state during the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a>.

For more details about the use of the <i>TargetId</i> parameter, see the following Remarks section.


### -param DisplayInfo [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_dxgk_display_information">DXGK_DISPLAY_INFORMATION</a> structure that is allocated by the operating system.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h. For more information, see the following Remarks section.




## -remarks



<h3><a id="Allowed_color_formats"></a><a id="allowed_color_formats"></a><a id="ALLOWED_COLOR_FORMATS"></a>Allowed color formats</h3>
The display miniport driver should report only a 32-bit color format. Therefore the <i>DisplayInfo</i>-><b>ColorFormat</b> member must include only one of the following two formats:

<ul>
<li><b>D3DDDIFMT_X8R8G8B8</b></li>
<li><b>D3DDDIFMT_A8R8G8B8</b></li>
</ul>
<h3><a id="Video_present_target_initialization_"></a><a id="video_present_target_initialization_"></a><a id="VIDEO_PRESENT_TARGET_INITIALIZATION_"></a>Video present target initialization
</h3>
The display miniport driver must set the <i>DisplayInfo</i>-><b>TargetId</b> member to the target identifier of the display that remains active. Typically, this identifier will be the value of the <i>TargetId</i> parameter that the operating system passed to the driver.

Similarly, the display miniport driver must set the <i>DisplayInfo</i>-><b>AcpiId</b> member to the ACPI identifier of the display that remains active.

<h3><a id="Required_steps_by_display_miniport_driver"></a><a id="required_steps_by_display_miniport_driver"></a><a id="REQUIRED_STEPS_BY_DISPLAY_MINIPORT_DRIVER"></a>Required steps by display miniport driver</h3>
The display miniport driver must follow these steps when its <i>DxgkDdiStopDeviceAndReleasePostDisplayOwnership</i> function is called:

<ol>
<li>
The driver must stop the display device associated with the video present target indicated by the <i>TargetId</i> parameter but must keep the display associated with this target powered on and visible.

</li>
<li>The driver must check the connectivity of the display associated with this target. If the target does not have a display connected, the driver must complete the call to this function and return the <b>STATUS_NOT_SUPPORTED</b> error code.</li>
<li>The driver must disable the signal to all other displays that are connected to the display adapter. If this is not possible, the driver should attempt to place a blank image on all other displays. If this is not possible, the driver must leave the last image on the screen unchanged.</li>
<li>The driver must keep the current display mode on the indicated target and provide this mode back to the operating system as part of this function call.</li>
<li>
If the driver cannot maintain the current display mode, or if the target is not part of the active topology, the driver should select an alternate active target and attempt to maintain the current resolution of that target. If that is not possible, the driver should attempt to set the display to its native resolution or to a high-resolution mode. In this case, the  display resolution must be set to at least 800 x 600 pixels in either <b>D3DDDIFMT_R8G8B8</b> (24 bits per pixel) or <b>D3DDDIFMT_X8R8G8B8</b> (32 bpp) color formats of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a> enumeration.

</li>
<li>If no target is active, the driver should attempt to enable a target, preferably the internal panel, if it is available.</li>
<li>
If possible, the driver must	clear the current frame buffer and disable the hardware cursor and all display overlays.

</li>
<li>
If possible, the driver must set the gamma ramp of the device to its default values.

</li>
<li>
The driver must 	set the current frame buffer to be in a linear mode. The driver does this either by using the default swizzle range or by disabling swizzle mode.

</li>
<li>
	The driver must make the current frame buffer accessible to the CPU by mapping the  current frame buffer linearly into the CPU address space.

</li>
<li>The driver must ensure that the visibility of the indicated target is set to "enabled."</li>
</ol>
After the display miniport driver performs these steps, it must return the current display settings for the device. The driver returns this information by setting the members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_dxgk_display_information">DXGK_DISPLAY_INFORMATION</a> structure that is referenced by the <i>DisplayInfo</i> parameter.

<div class="alert"><b>Note</b>  After the device has been stopped, this display information might be used by the Windows generic display driver to manage the display device.</div>
<div> </div>
<h3><a id="Other_requirements"></a><a id="other_requirements"></a><a id="OTHER_REQUIREMENTS"></a>Other requirements</h3>
On systems that support the Unified Extensible Firmware Interface (UEFI), a VGA basic input/output system (BIOS) does not exist. To support PnP stop operations on these systems, Windows Display Driver Model (WDDM) 1.2 and later provides support for the operating system to reset the POST device and to get its display information during a PnP stop operation.  The operating system does this by calling the display miniport driver's <i>DxgkDdiStopDeviceAndReleasePostDisplayOwnership</i> function.

A PnP stop operation can occur in response to requests by processes such as the Device Manager, or during a driver upgrade process.

Starting with Windows 8, the operating system calls the driver's <i>DxgkDdiStopDeviceAndReleasePostDisplayOwnership</i> function only on the POST device during a PnP stop operation.

<div class="alert"><b>Note</b>  	It is optional for the display miniport driver to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkcb_acquire_post_display_ownership">DxgkCbAcquirePostDisplayOwnership</a>. However, the operating system might still call the <i>DxgkDdiStopDeviceAndReleasePostDisplayOwnership</i> function of the device driver if the driver did not previously call <b>DxgkCbAcquirePostDisplayOwnership</b>.</div>
<div> </div>
If the driver successfully completes a call to this function, the operating system will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_stop_device">DxgkDdiStopDevice</a> function. If the driver fails to complete a call to this function, the operating system will call the <i>DxgkDdiStopDevice</i> function, and device behavior will be the same as in Windows 7.

On UEFI-only systems, if the display miniport driver fails a call to this function, a black screen is displayed and the IHV driver is not installed. The workaround to this scenario is for the user to reboot the computer.

For more information on how this function is used in PnP scenarios, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/plug-and-play--pnp--start-and-stop-cases">Plug and Play (PnP) in WDDM 1.2 and later</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_dxgk_display_information">DXGK_DISPLAY_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkcb_acquire_post_display_ownership">DxgkCbAcquirePostDisplayOwnership</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_stop_device">DxgkDdiStopDevice</a>
 

 

