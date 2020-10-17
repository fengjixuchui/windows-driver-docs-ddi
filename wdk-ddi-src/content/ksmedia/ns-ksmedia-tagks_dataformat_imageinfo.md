---
UID: NS:ksmedia.tagKS_DATAFORMAT_IMAGEINFO
title: tagKS_DATAFORMAT_IMAGEINFO (ksmedia.h)
description: Specifies an image data format that is used for an independent image pin (or stream).
old-location: stream\ks_dataformat_imageinfo.htm
tech.root: stream
ms.assetid: d63289bc-9603-4e79-8a77-d2eb0f2c784c
ms.date: 04/23/2018
keywords: ["tagKS_DATAFORMAT_IMAGEINFO structure"]
ms.keywords: "*PKS_DATAFORMAT_IMAGEINFO, KS_DATAFORMAT_IMAGEINFO, KS_DATAFORMAT_IMAGEINFO structure [Streaming Media Devices], PKS_DATAFORMAT_IMAGEINFO, PKS_DATAFORMAT_IMAGEINFO structure pointer [Streaming Media Devices], ksmedia/KS_DATAFORMAT_IMAGEINFO, ksmedia/PKS_DATAFORMAT_IMAGEINFO, stream.ks_dataformat_imageinfo, tagKS_DATAFORMAT_IMAGEINFO"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
targetos: Windows
req.typenames: KS_DATAFORMAT_IMAGEINFO, *PKS_DATAFORMAT_IMAGEINFO
f1_keywords:
 - tagKS_DATAFORMAT_IMAGEINFO
 - ksmedia/tagKS_DATAFORMAT_IMAGEINFO
 - PKS_DATAFORMAT_IMAGEINFO
 - ksmedia/PKS_DATAFORMAT_IMAGEINFO
 - KS_DATAFORMAT_IMAGEINFO
 - ksmedia/KS_DATAFORMAT_IMAGEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - KS_DATAFORMAT_IMAGEINFO
---

# tagKS_DATAFORMAT_IMAGEINFO structure


## -description

Specifies an image data format that is used for an independent image pin (or stream).

## -struct-fields

### -field DataFormat

A <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a> structure that specifies the data format of the image stream.

### -field ImageInfoHeader

A <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader">KS_BITMAPINFOHEADER</a> structure that specifies image color and dimension information that the still image capture stream would provide.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader">KS_BITMAPINFOHEADER</a>