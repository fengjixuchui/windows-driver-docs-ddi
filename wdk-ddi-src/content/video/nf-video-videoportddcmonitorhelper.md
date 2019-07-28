---
UID: NF:video.VideoPortDDCMonitorHelper
title: VideoPortDDCMonitorHelper function (video.h)
description: Queries a monitor for EDID information using the DDC protocol.
old-location: display\videoportddcmonitorhelper.htm
tech.root: display
ms.assetid: 2e4bd9c7-73be-47bc-b4e7-daea7781c46b
ms.date: 05/10/2018
ms.keywords: VideoPortDDCMonitorHelper, VideoPortDDCMonitorHelper function [Display Devices], VideoPort_Functions_dc0bda84-97c5-49ba-9084-04149f9be157.xml, display.videoportddcmonitorhelper, video/VideoPortDDCMonitorHelper
ms.topic: function
f1_keywords:
 - "video/VideoPortDDCMonitorHelper"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortDDCMonitorHelper
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortDDCMonitorHelper function


## -description


Queries a monitor for <a href="https://docs.microsoft.com/windows-hardware/drivers/">EDID</a> information using the DDC protocol.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the miniport driver's device extension.


### -param DDCControl [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_ddc_control">DDC_CONTROL</a> structure.


### -param EdidBuffer [in, out]

A pointer to a buffer in which the video port driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/">EDID</a> structure. For ACPI devices, the first four bytes are preset by the video port driver to indicate an attempt to read the <i>EDID</i>. 


### -param EdidBufferSize [in]

The size in bytes of the buffer to which <i>EdidBuffer</i> points.


## -returns



<b>VideoPortDDCMonitorHelper</b> returns <b>TRUE</b> if successful.




## -remarks



<div class="alert"><b>Note</b>  <p class="note">This function existed prior to the Windows XP release, but has been changed.

<p class="note">The video miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a> function can call <b>VideoPortDDCMonitorHelper</b> for assistance in reading the <a href="https://docs.microsoft.com/windows-hardware/drivers/">EDID</a> structure from a DDC2-compliant monitor. <b>VideoPortDDCMonitorHelper </b>implements the details of reading the EDID structure according to the I²C specification, but must call back into the video miniport driver to read and write individual data bits to the I²C serial clock and data lines.

<p class="note">The four functions, implemented by the video miniport driver, that read and write individual bits to the I²C clock and data lines are <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_read_clock_line">ReadClockLine</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_read_data_line">ReadDataLine</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_write_clock_line">WriteClockLine</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_write_data_line">WriteDataLine</a>. When the video miniport driver calls <b>VideoPortDDCMonitorHelper</b>, it supplies pointers to those four functions in <i>DDCControl</i><b>->I2CCallbacks</b>.

<p class="note">The <a href="https://docs.microsoft.com/windows-hardware/drivers/">EDID</a> can be obtained using the ACPI_METHOD_OUTPUT_DDC method whose alias is defined in Dispmprt.h. This method is required for integrated LCDs that do not have another standard mechanism for returning EDID data.

<p class="note">In a 256-byte buffer, a caller of this function can receive:

<ul>
<li>
One 128-byte EDID

</li>
<li>
Two 128-byte EDIDs

</li>
<li>
One 256-byte EDID (from P&D display)

</li>
<li>
No EDID

</li>
</ul>
<p class="note">The caller should always ask for the full 256 bytes, because it is impossible to read just the second 128-byte block of the segment.

</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">I2C Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_read_clock_line">ReadClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_read_data_line">ReadDataLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_write_clock_line">WriteClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_write_data_line">WriteDataLine</a>
 

 

