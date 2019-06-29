---
UID: NS:d3dkmddi._DXGK_FLIPCAPS
title: _DXGK_FLIPCAPS (d3dkmddi.h)
description: The DXGK_FLIPCAPS structure identifies flipping capabilities of the display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_flipcaps.htm
ms.assetid: 33399b7c-ce67-4c49-be26-2b2d759ff5a0
ms.date: 05/10/2018
ms.keywords: DXGK_FLIPCAPS, DXGK_FLIPCAPS structure [Display Devices], DmStructs_11bba63e-8001-41d2-9c60-978024921994.xml, _DXGK_FLIPCAPS, d3dkmddi/DXGK_FLIPCAPS, display.dxgk_flipcaps
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dkmddi.h
api_name:
- DXGK_FLIPCAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_FLIPCAPS
---

# _DXGK_FLIPCAPS structure


## -description


The <b>DXGK_FLIPCAPS</b> structure identifies flipping capabilities of the display miniport driver that the driver provides through a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.


## -struct-fields




### -field FlipOnVSyncWithNoWait

A <b>UINT</b> value that specifies whether the driver supports the scheduling of a flip command that will take effect on the next vertical retrace period (vertical sync) without causing the graphics pipeline to stall until that vertical sync occurs. That is, the graphics pipeline must proceed immediately after the driver writes the physical address of the flipping surface into flip-pending registers at the hardware. Although most hardware uses a depth of one flip-pending register, if hardware uses more than one flip-pending register, the driver should specify the number in the <b>MaxQueuedFlipOnVSync</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure. 

If <b>FlipOnVSyncWithNoWait</b> is set to 1 (<b>TRUE</b>), the driver supports this mechanism. If <b>FlipOnVSyncWithNoWait</b> is set to 0 (<b>FALSE</b>), the driver does not support this mechanism. That is, the graphics pipeline must wait until the next vertical sync occurs after the scheduling of a flip command to take effect on the next vertical sync.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field FlipOnVSyncMmIo

A <b>UINT</b> value that specifies whether the driver supports a memory mapped I/O (MMIO)-based flip that takes effect on the next vertical sync. To support this type of flip, the display miniport driver must support the following operations:

<ul>
<li>
No generation of a DMA buffer to pass in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> function (that is, <b>NULL</b> is passed in the <b>pDmaBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a> structure).

</li>
<li>
A flip through a call to its <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560767(v=vs.85)">DxgkDdiSetVidPnSourceAddress</a> function at device interrupt request level (DIRQL). In the call to <i>DxgkDdiSetVidPnSourceAddress</i>, the driver should program the digital-to-analog converter (DAC) and use the value in the <b>PrimaryAddress</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress">DXGKARG_SETVIDPNSOURCEADDRESS</a> structure to start the scan out. After the vertical sync, the driver should notify the GPU scheduler to report the effective scan address by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_interrupt">DxgkCbNotifyInterrupt</a> function with the <b>DXGK_INTERRUPT_CRTC_VSYNC</b> value set in the <b>InterruptType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure. The driver should then call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_dpc">DxgkCbNotifyDpc</a> function to perform most of the scan-out processing.

</li>
</ul>

### -field FlipInterval

A <b>UINT</b> value that specifies whether the driver supports the scheduling of a flip command to take effect after two, three, or four vertical syncs occur. Regardless of whether the driver supports a flip interval of two or greater, the driver must support an immediate flip and a flip interval of one.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field FlipImmediateMmIo

A <b>UINT</b> value that specifies whether the driver supports a memory mapped I/O (MMIO)-based immediate flip. This type of flip takes effect immediately following a call to the driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560767(v=vs.85)">DxgkDdiSetVidPnSourceAddress</a> function without waiting for the next vertical sync to occur.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).

Supported starting with Windows 7.


### -field FlipIndependent

A <b>UINT</b> value that specifies whether the driver supports an independent flip. WDDM 1.3 and later drivers must set this member to 1.

In an <i>independent flip</i>, the operating system attempts to bypass a Desktop Window Manager (DWM) user-mode present call and flips to the application back buffer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>  and <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560767(v=vs.85)">DxgkDdiSetVidPnSourceAddress</a> in Direct Flip and multiplane overlay presentation models.

Note that there will be cases when a DWM user-mode present call is made even when <b>FlipIndependent</b> is set. Your driver must still handle such cases.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).

Supported starting with Windows 8.1.


### -field DdiPresentForIFlip

 


### -field FlipImmediateOnHSync

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that DXGK_FLIPCAPS contains that can hold a 32-bit value that identifies flipping capabilities.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress">DXGKARG_SETVIDPNSOURCEADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_dpc">DxgkCbNotifyDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_interrupt">DxgkCbNotifyInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560767(v=vs.85)">DxgkDdiSetVidPnSourceAddress</a>
 

 

