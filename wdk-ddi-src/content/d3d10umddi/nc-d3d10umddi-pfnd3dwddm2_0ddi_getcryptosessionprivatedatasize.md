---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_GETCRYPTOSESSIONPRIVATEDATASIZE
title: PFND3DWDDM2_0DDI_GETCRYPTOSESSIONPRIVATEDATASIZE (d3d10umddi.h)
description: GetCryptoSessionPrivateDataSize retrieves sizes for optional private driver data.
old-location: display\getcryptosessionprivatedatasize.htm
ms.assetid: 1D135203-AA20-4D5D-A0F2-A53BDF5104C0
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_0DDI_GETCRYPTOSESSIONPRIVATEDATASIZE callback function"]
ms.keywords: PFND3DWDDM2_0DDI_GETCRYPTOSESSIONPRIVATEDATASIZE, PFND3DWDDM2_0DDI_GETCRYPTOSESSIONPRIVATEDATASIZE callback, d3d10umddi/pfnGetCryptoSessionPrivateDataSize, display.getcryptosessionprivatedatasize, pfnGetCryptoSessionPrivateDataSize, pfnGetCryptoSessionPrivateDataSize callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/pfnGetCryptoSessionPrivateDataSize"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnGetCryptoSessionPrivateDataSize
product:
 - Windows
---

# PFND3DWDDM2_0DDI_GETCRYPTOSESSIONPRIVATEDATASIZE callback function

## -description

<b>GetCryptoSessionPrivateDataSize</b> retrieves sizes for optional private driver data.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param pCryptoType

Indicates the crypto type for which the private input and output size is queried.

### -param pDecoderProfile

Indicates the decoder profile for which the private input and output size is queried.

### -param pKeyExchangeType

Indicates the key exchange type for which the private input and output size is queried.

### -param pPrivateInputSize

Returns the size of private data that the driver needs for input commands.

### -param pPrivateOutputSize

Returns the size of private data that the driver needs for output commands.

## -remarks

When <b>pKeyExchangeType</b> is <b>D3D11_KEY_EXCHANGE_HW_PROTECTION</b>, the following behavior is expected in the <b>NegotiateCryptessionKeyExchange</b>device driver interface (DDI):

<ul>
<li><b>DataSize</b> is set to the size of the <b>D3D11_KEY_EXCHANGE_HW_PROTECTION_DATA</b> structure.

</li>
<li><b>pData</b> points to a <b>D3D11_KEY_EXCHANGE_CONTENT_PROTECTION_DATA</b> structure.</li>
<li>
<b>pInputData</b> points to a <b>D3D11_KEY_EXCHANGE_CONTENT_PROTECTION_OUTPUT_DATA</b> structure where:

<ul>
<li><b>pbInput</b>[0] – <b>pbInput</b>[N-1] contains memory reserved for use by the driver. The number of bytes (N) reserved for the driver is determined by the <b>pPrivateInputSize</b> value returned by the <b>GetCryptoSessionPrivateDataSize</b>DDI.</li>
<li><b>pbInput</b>[N] contains the first byte of the Digital Rights Management (DRM) command packet.</li>
</ul>
</li>
<li>
<b>pOutputData</b> points to a <b>D3D11_KEY_EXCHANGE_CONTENT_PROTECTION_OUTPUT_DATA</b> structure where:

<ul>
<li><b>pbOutput</b>[0] – <b>pbOutput</b>[M-1] contains memory reserved for use by the driver. The number of bytes (M) reserved for the driver is determined by the <b>pPrivateOutputSize</b> value returned by the <b>GetCryptoSessionPrivateDataSize</b>DDI.</li>
<li><b>pbOutput</b>[M] contains the first byte of the DRM command packet.</li>
</ul>
</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>

