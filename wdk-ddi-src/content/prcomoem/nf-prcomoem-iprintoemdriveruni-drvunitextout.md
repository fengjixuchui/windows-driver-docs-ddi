---
UID: NF:prcomoem.IPrintOemDriverUni.DrvUniTextOut
title: IPrintOemDriverUni::DrvUniTextOut (prcomoem.h)
description: The IPrintOemDriverUni::DrvUniTextOut method is provided by the Unidrv driver so that a rendering plug-in using a device-managed drawing surface can easily output text strings.
old-location: print\iprintoemdriveruni_drvunitextout.htm
tech.root: print
ms.assetid: f8c21813-9bfd-46a5-abb2-78ac2f2301af
ms.date: 04/20/2018
keywords: ["IPrintOemDriverUni::DrvUniTextOut"]
ms.keywords: DrvUniTextOut, DrvUniTextOut method [Print Devices], DrvUniTextOut method [Print Devices],IPrintOemDriverUni interface, IPrintOemDriverUni interface [Print Devices],DrvUniTextOut method, IPrintOemDriverUni.DrvUniTextOut, IPrintOemDriverUni::DrvUniTextOut, prcomoem/IPrintOemDriverUni::DrvUniTextOut, print.iprintoemdriveruni_drvunitextout, print_unidrv-pscript_rendering_a67dafd9-26b4-43ad-82f9-e53caca33053.xml
f1_keywords:
 - "prcomoem/IPrintOemDriverUni.DrvUniTextOut"
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemDriverUni.DrvUniTextOut
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUni::DrvUniTextOut


## -description


The <code>IPrintOemDriverUni::DrvUniTextOut</code> method is provided by the Unidrv driver so that a rendering plug-in using a device-managed drawing surface can easily output text strings.


## -parameters




### -param pso

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_surfobj">SURFOBJ</a> structure that describes the surface on which to write. 


### -param pstro

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_strobj">STROBJ</a> structure that defines the glyphs to be rendered and the positions in which to place them. 


### -param pfo

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_fontobj">FONTOBJ</a> structure from which to retrieve information about the font and its glyphs. 


### -param pco

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_clipobj">CLIPOBJ</a> structure that defines the clip region through which all rendering must be done. The driver cannot affect any pixels outside the clip region. 


### -param prclExtra

Pointer to a RECTL structure. GDI always sets this parameter to <b>NULL</b> in calls to this function. It should be ignored by the driver. 


### -param prclOpaque

Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-rectl">RECTL</a> structure that represents a single opaque rectangle. This rectangle is bottom-right exclusive. Pixels within this rectangle (those that are not foreground and not clipped) are to be rendered with the opaque brush. This rectangle always bounds the text to be drawn. If this parameter is <b>NULL</b>, no opaque pixels are to be rendered. 


### -param pboFore

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_brushobj">BRUSHOBJ</a> structure that represents the brush object to be used for the foreground pixels. This brush will always be a solid color brush.


### -param pboOpaque

Pointer to a BRUSHOBJ structure that represents the opaque pixels. Both the foreground and background mix modes for this brush are assumed to be R2_COPYPEN. Unless the driver sets the GCAPS_ARBRUSHOPAQUE capabilities bit in the <b>flGraphicsCaps</b> member of the DEVINFO structure, it will always be called with a solid color brush. 


### -param pptlBrushOrg

Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-pointl">POINTL</a> structure that defines the brush origin for both brushes.


### -param mix

The foreground and background raster operations (mix modes) for <i>pboFore</i>. 


## -returns



The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



The <code>IPrintOemDriverUni::DrvUniTextOut</code> method is provided by Unidrv for use by rendering plug-ins that support a device-managed drawing surface. Such rendering plug-ins must hook out Unidrv's <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvtextout">DrvTextOut</a> function, and the <code>IPrintOemDriverUni::DrvUniTextOut</code> method is meant to be called from that hooking function. The hooking function must perform text region clipping and text rotation operations. It can then call <code>IPrintOemDriverUni::DrvUniTextOut</code> to request Unidrv to create the text string using downloadable fonts (and to perform glyph-based clipping).

If <code>IPrintOemDriverUni::DrvUniTextOut</code> cannot create the text string, either because the font is not available or is rotated, it calls the rendering plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-textoutasbitmap">IPrintOemUni::TextOutAsBitmap</a> method, which draws the text string as a bitmap.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/handling-device-managed-surfaces">Handling Device-Managed Surfaces</a>.



