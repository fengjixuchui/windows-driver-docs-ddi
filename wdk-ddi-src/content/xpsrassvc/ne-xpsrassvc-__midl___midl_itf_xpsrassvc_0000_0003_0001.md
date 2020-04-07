---
UID: NE:xpsrassvc.__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001
title: __MIDL___MIDL_itf_xpsrassvc_0000_0003_0001 (xpsrassvc.h)
description: XPSRAS_PIXEL_FORMAT allows a caller to select the pixel format used by the IWICBitmap interface that is returned by the IXpsRasterizer::RasterizeRect method. XPSRAS_PIXEL_FORMAT is provided with Windows 8 and later versions of Windows.
old-location: print\xpsras_pixel_format.htm
tech.root: print
ms.assetid: 54EA7ED6-BBE1-4110-8405-DEC0C5EA1C27
ms.date: 04/20/2018
keywords: ["__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001 enumeration"]
ms.keywords: XPSRAS_PIXEL_FORMAT, XPSRAS_PIXEL_FORMAT enumeration [Print Devices], XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB, XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB, XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB, __MIDL___MIDL_itf_xpsrassvc_0000_0003_0001, print.xpsras_pixel_format, xpsrassvc/XPSRAS_PIXEL_FORMAT, xpsrassvc/XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB, xpsrassvc/XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB, xpsrassvc/XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB
f1_keywords:
 - "xpsrassvc/XPSRAS_PIXEL_FORMAT"
req.header: xpsrassvc.h
req.include-header: Xpsrassvc.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Xpsrassvc.h
api_name:
- XPSRAS_PIXEL_FORMAT
product:
- Windows
targetos: Windows
req.typenames: XPSRAS_PIXEL_FORMAT
---

# __MIDL___MIDL_itf_xpsrassvc_0000_0003_0001 enumeration


## -description


<b>XPSRAS_PIXEL_FORMAT</b> allows a caller to select the pixel format used by the <a href="https://go.microsoft.com/fwlink/p/?linkid=133875">IWICBitmap</a> interface that is returned by the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-rasterizerect">IXpsRasterizer::RasterizeRect</a> method. <b>XPSRAS_PIXEL_FORMAT</b> is provided with  Windows 8 and later versions of Windows.  


## -enum-fields




### -field XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB

32-bit color pixel format. It is the default pixel format.


### -field XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB

64-bit color pixel format.


### -field XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB

128-bit color pixel format.


## -remarks



For more information about rasterizing XPS documents, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-the-xps-rasterization-service">Using the XPS Rasterization Service</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/wincodec/nn-wincodec-iwicbitmap">IWICBitmap</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh802468(v=vs.85)">IXpsRasterizationFactory1::CreateRasterizer1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-the-xps-rasterization-service">Using the XPS Rasterization Service</a>
 

 

