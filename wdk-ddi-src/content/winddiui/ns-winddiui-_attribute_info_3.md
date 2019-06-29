---
UID: NS:winddiui._ATTRIBUTE_INFO_3
title: _ATTRIBUTE_INFO_3 (winddiui.h)
description: The ATTRIBUTE_INFO_3 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied.
old-location: print\attribute_info_3.htm
tech.root: print
ms.assetid: a9299c25-4210-4161-bfd6-8a13113b93e1
ms.date: 04/20/2018
ms.keywords: "*PATTRIBUTE_INFO_3, ATTRIBUTE_INFO_3, ATTRIBUTE_INFO_3 structure [Print Devices], PATTRIBUTE_INFO_3, PATTRIBUTE_INFO_3 structure pointer [Print Devices], _ATTRIBUTE_INFO_3, print.attribute_info_3, print_interface-graphics_473dca69-31fc-410d-a9d6-cfa5241f2c5b.xml, winddiui/ATTRIBUTE_INFO_3, winddiui/PATTRIBUTE_INFO_3"
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h, Winsplp.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winddiui.h
api_name:
- ATTRIBUTE_INFO_3
product:
- Windows
targetos: Windows
req.typenames: ATTRIBUTE_INFO_3, *PATTRIBUTE_INFO_3
---

# _ATTRIBUTE_INFO_3 structure


## -description


The ATTRIBUTE_INFO_3 structure is used as a parameter for a printer interface DLL's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a> function. All member values are function-supplied.


## -struct-fields




### -field dwJobNumberOfPagesPerSide

Number of document pages to be placed on one side of a physical page, as requested by the user. Allowable values are 1, 2, 4, 6, 9, or 16.


### -field dwDrvNumberOfPagesPerSide

Number of document pages that the printer and driver can place on one side of a physical page. This value must be 1 or the value specified for <b>dwJobNumberOfPagesPerSide</b>.


### -field dwNupBorderFlags

One of the following bit flag values:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
BORDER_PRINT

</td>
<td>
The print processor should draw a border around the page.

</td>
</tr>
<tr>
<td>
NO_BORDER_PRINT

</td>
<td>
The print processor should not draw a border around the page.

</td>
</tr>
</table>
 


### -field dwJobPageOrderFlags

One of the following bit flag values:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
BOOKLET_PRINT

</td>
<td>
Pages should be printed in booklet form, with two document pages printed on one side of a physical page. In landscape mode, the two document pages are printed side-by-side on the paper. In portrait mode, the two document pages are printed top-and-bottom.

</td>
</tr>
<tr>
<td>
NORMAL_PRINT

</td>
<td>
Pages should be printed in normal order: page 1, page 2, and so on.

</td>
</tr>
<tr>
<td>
REVERSE_PRINT

</td>
<td>
Pages should be printed in reverse order: last page, next-to-last page, and so on.

</td>
</tr>
</table>
 


### -field dwDrvPageOrderFlags

Bit flags indicating which page ordering options are supported by the printer and driver. Uses the same flags as <b>dwJobPageOrderFlags</b>.


### -field dwJobNumberOfCopies

Number of copies of the print job, as requested by the user.


### -field dwDrvNumberOfCopies

Maximum number of copies the printer and driver can handle at once, taking into account such job attributes as collating and stapling.


### -field dwColorOptimization

One of the following bit flag values:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
COLOR_OPTIMIZATION

</td>
<td>
The print processor should use monochrome color optimization.

</td>
</tr>
<tr>
<td>
NO_COLOR_OPTIMIZATION

</td>
<td>
The print processor should not use monochrome color optimization.

</td>
</tr>
</table>
 


### -field dmPrintQuality

Value to be used instead of the <b>dmPrintQuality</b> member of the print job's <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure, if the COLOR_OPTIMIZATION flag is set in <b>dwColorOptimization</b>.


### -field dmYResolution

Value to be used instead of the <b>dmYResolution</b> member of the print job's DEVMODEW structure, if the COLOR_OPTIMIZATION flag is set in <b>dwColorOptimization</b>.


## -remarks



If the <b>dmPrintQuality</b> member of a print job's DEVMODEW structure is a negative value, such as DMRES_HIGH, and if monochrome color optimization is enabled, then switching between color and monochrome could result in different resolutions being used. This is because DMRES_HIGH might be assigned to different DPI values for color and monochrome rendering. (For Unidrv-supported devices, this assignment occurs in the printer's <a href="https://docs.microsoft.com/windows-hardware/drivers/">GPD</a> file.) To ensure a consistent resolution throughout the print job, the driver can specify positive <b>dmPrintQuality</b> and <b>dmYResolution</b> values (representing a specific DPI resolution) to override the equivalent <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> values. 

The EMF print processor uses the flag specified for <b>dwColorOptimization</b> to determine whether to request GDI to perform monochrome color optimization. If monochrome color optimization is enabled, the print job can be switched between monochrome and color rendering as appropriate.

If you are creating a Unidrv rendering plug-in to generate color watermarks, note that when the <b>dwColorOptimization</b> member is set to COLOR_OPTIMIZATION, color watermarks are printed in black and white when they are printed on black-and-white documents. To ensure that color watermarks print correctly with color and black-and-white documents, disable color optimization. Color optimization also can be controlled by the Unidrv *<b>ChangeColorModeOnDoc?</b> color attribute (see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/color-attributes">Color Attributes</a>), and by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winppi/nf-winppi-gdiendpageemf">GdiEndPageEMF</a> function. 

For information about other ATTRIBUTE_INFO_3 structure members, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_attribute_info_1">ATTRIBUTE_INFO_1</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_attribute_info_2">ATTRIBUTE_INFO_2</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_attribute_info_2">ATTRIBUTE_INFO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_attribute_info_4">ATTRIBUTE_INFO_4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winppi/nf-winppi-gdiendpageemf">GdiEndPageEMF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-getjobattributesex">GetJobAttributesEx</a>
 

 

