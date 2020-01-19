---
UID: NS:d3dumddi._D3DDDI_BLTFLAGS
title: _D3DDDI_BLTFLAGS (d3dumddi.h)
description: The D3DDDI_BLTFLAGS structure identifies the type of bit-block transfer (bitblt) to perform.
old-location: display\d3dddi_bltflags.htm
tech.root: display
ms.assetid: 844d6aed-2ca2-45ef-bd53-54344dbdadbf
ms.date: 05/10/2018
ms.keywords: D3DDDI_BLTFLAGS, D3DDDI_BLTFLAGS structure [Display Devices], D3D_other_Structs_8d70fa64-3813-4165-a64d-4e91287e05d5.xml, _D3DDDI_BLTFLAGS, d3dumddi/D3DDDI_BLTFLAGS, display.d3dddi_bltflags
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDI_BLTFLAGS"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
- d3dumddi.h
api_name:
- D3DDDI_BLTFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_BLTFLAGS
---

# _D3DDDI_BLTFLAGS structure


## -description


The D3DDDI_BLTFLAGS structure identifies the type of bit-block transfer (bitblt) to perform.


## -struct-fields




### -field Point

A UINT value that specifies whether to use point filtering in the bit-block transfer. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Linear

A UINT value that specifies whether to use linear filtering in the bit-block transfer. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field SrcColorKey

A UINT value that specifies whether to perform source color-keying by using the value in the <b>ColorKey</b> member. That is, any pixel in the source surface that matches the color key should not be copied to the destination surface, and all of the source pixels that do not match the color key should be copied. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field DstColorKey

A UINT value that specifies whether to perform destination color-keying by using the value in the <b>ColorKey</b> member. That is, any pixel in the destination surface that matches the color key should be replaced with the corresponding pixel from the source surface, and all of the destination pixels that do not match the color key should not be replaced.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field MirrorLeftRight

A UINT value that specifies whether the contents of the source surface are flipped horizontally along the center axis in the bitblt to the destination surface. That is, contents on the left side of the source surface are copied to the right side of the destination surface, and vice versa.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field MirrorUpDown

A UINT value that specifies whether the contents of the source surface are flipped vertically along the center axis in the bitblt to the destination surface. That is, the contents on the top of the source surface are copied to the bottom of the destination surface, and vice versa.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field LinearToSrgb

A UINT value that specifies whether to convert the linear-formatted source to sRGB format during the bitblt operation. sRGB format is gamma corrected. For more information about sRGB format, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a> website.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field Rotate

A UINT value that specifies whether to rotate the source during the bitblt operation. 

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).


### -field BeginPresentToDwm

A UINT value that specifies whether the Microsoft Direct3D runtime begins a DWM present operation during the bitblt operation. For more information about <b>BeginPresentToDwm</b>, see Remarks.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).


### -field ContinuePresentToDwm

A UINT value that specifies whether the Direct3D runtime continues a DWM present operation during the bitblt operation. For more information about <b>ContinuePresentToDwm</b>, see Remarks.

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).


### -field EndPresentToDwm

A UINT value that specifies whether the Direct3D runtime ends a DWM present operation during the bitblt operation. For more information about <b>EndPresentToDwm</b>, see Remarks.

Setting this member is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400).


### -field Discard

Indicates that the user-mode display driver can discard previous contents of the entire resource. The driver can take advantage of this capability to optimize performance and memory usage.

If this member is not <b>NULL</b>, <b>NoOverwrite</b> and  <b>Tileable</b> must be <b>NULL</b>.

Setting this member is equivalent to setting the twelfth bit (0xFFFFF800) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field NoOverwrite

Indicates that the caller guarantees that the portion of the surface that is being written to with new data is not currently being referenced or accessed by any previous render operation. The driver can take advantage of this capability to optimize performance and memory usage.

If this member is not <b>NULL</b>, <b>Discard</b> must be <b>NULL</b>.

Setting this member is equivalent to setting the thirteenth bit (0x00001000) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field Tileable

For tile-based deferred rendering, indicates that a copy operation can operate on only the currently processed tile in the source or destination resource, and the scene does not have to be flushed in all tiles.

If this member is not <b>NULL</b>, <b>Discard</b> must be <b>NULL</b>.

Setting this member is equivalent to setting the fourteenth bit (0x00002000) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 21 bits (0xFFFFF800) of the 32-bit <b>Value</b> member to zeros.

This member is reserved and should be set to zero. 

Setting this member to zero is equivalent to setting the remaining 18 bits (0xFFFFC000) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field Value

A member in the union that is contained in D3DDDI_BLTFLAGS that can hold one 32-bit value that identifies the type of bitblt to perform.


## -remarks



The <b>BeginPresentToDwm</b>, <b>ContinuePresentToDwm</b>, and <b>EndPresentToDwm</b> bit-field flags inform the user-mode display driver about the time when the Direct3D runtime performs parts of a DWM present operation.  Because DWM present operations can occur in multiple steps, the Direct3D runtime uses these flags to mark the steps in a sequence of bitblts. For example:  

<ul>
<li>If the present operation consists of one bitblt, the bitblt is marked as follows:<ul>
<li><b>BeginPresentToDwm</b> = <b>TRUE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>TRUE</b>;</li>
</ul>
</li>
<li>If the present operation consists of two bitblts, the bitblts are marked as shown in two sequential bitblt operations:<ol>
<li>First bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>TRUE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>FALSE</b>;</li>
</ul>
</li>
<li>Second bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>TRUE</b>;</li>
</ul>
</li>
</ol>
</li>
<li>If the present operation consists of three or more bitblts, the bitblts are marked as shown in the following sequential bitblt operations:<ol>
<li>First bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>TRUE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>FALSE</b>;</li>
</ul>
</li>
<li>Second and successive bitblts, not including the final bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>TRUE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>FALSE</b>;</li>
</ul>
</li>
<li>Final bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>TRUE</b>;</li>
</ul>
</li>
</ol>
</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_blt">D3DDDIARG_BLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a>
 

 

