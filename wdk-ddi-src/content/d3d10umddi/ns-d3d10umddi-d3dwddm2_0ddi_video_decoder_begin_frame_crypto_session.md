---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
title: D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION (d3d10umddi.h)
description: D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION is used along with CreateCryptoSession to perform crypto operations into and out of protected memory.
old-location: display\d3d11_video_decoder_begin_frame_crypto_session.htm
ms.assetid: EC08022F-319E-4E49-A003-B98EEADAA0CC
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION structure"]
ms.keywords: D3D11_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION, D3D11_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION structure [Display Devices], D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION, D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION, display.d3d11_video_decoder_begin_frame_crypto_session
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
req.typenames: D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
f1_keywords:
 - D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
 - d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
---

# D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION structure


## -description

<b>D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION</b> is used along with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> to   perform crypto operations into and out of protected memory.

## -struct-fields

### -field hCryptoSession

A handle to a cryptographic session object created using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>.

### -field pBlob

A pointer to an IHV-defined blob allocated by an upstream DRM component.  The blob identifies the sealed decryption key to be used for the current frame.

### -field BlobSize

Size of the IHV-defined blob referenced in the <b>pBlob</b> member.

### -field pKeyInfoId

A pointer to a <b>GUID</b> identifying the hardware key.

### -field pPrivateData

The definition of this buffer is dependent on the implementation of the secure environment. It may contain data specific to the current frame.

### -field PrivateDataSize

Contains the size of the memory buffer referenced by the <b>pPrivateData</b> member.

## -remarks

A pointer to this structure is passed in the <b>pContentKey</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_videodecoderbeginframe">D3D11_1DDIARG_VIDEODECODERBEGINFRAME</a> structure when <b>D3DWDDM2_0DDI_DECODER_ENCRYPTION_HW_CENC</b> is specified in the <b>guidConfigBitstreamEncryption</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_config">D3D11_1DDI_VIDEO_DECODER_CONFIG</a> structure when creating the video decoder object.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_videodecoderbeginframe">D3D11_1DDIARG_VIDEODECODERBEGINFRAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_config">D3D11_1DDI_VIDEO_DECODER_CONFIG</a>

