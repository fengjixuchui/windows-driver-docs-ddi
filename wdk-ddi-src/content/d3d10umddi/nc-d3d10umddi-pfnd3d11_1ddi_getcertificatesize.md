---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCERTIFICATESIZE
title: PFND3D11_1DDI_GETCERTIFICATESIZE (d3d10umddi.h)
description: Queries the size in bytes of the certificate that the display miniport driver uses for either the cryptographic session certificate or authenticated channel.
old-location: display\getcertificatesize.htm
ms.assetid: 7f9a2a76-ee50-4f72-a588-d7b9145c14a6
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_GETCERTIFICATESIZE, PFND3D11_1DDI_GETCERTIFICATESIZE callback, d3d10umddi/pfnGetCertificateSize, display.getcertificatesize, pfnGetCertificateSize, pfnGetCertificateSize callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnGetCertificateSize"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnGetCertificateSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_GETCERTIFICATESIZE callback function


## -description


Queries the size in bytes of the certificate that the display miniport driver uses for either the cryptographic  session certificate or authenticated channel.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCertificateInfo [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_certificate_info">D3D11_1DDI_CERTIFICATE_INFO</a> structure that specifies the cryptographic  session certificate or authenticated channel to query.


### -param *pCertificateSize [out]

The size, in bytes, of the specified certificate.


## -returns



This callback function does not return a value.




## -remarks



Based on the data in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_certificate_info">D3D11_1DDI_CERTIFICATE_INFO</a> structure, the <b>GetCertificateSize</b> function returns the size in bytes of the certificate chain for either the cryptographic session or the authenticated channel. The driver uses this certificate to establish trust and perform key exchange for the session or channel.

<div class="alert"><b>Note</b>  The driver's certificate  can be queried by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificate">GetCertificate</a>.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_certificate_info">D3D11_1DDI_CERTIFICATE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificate">GetCertificate</a>
 

 

