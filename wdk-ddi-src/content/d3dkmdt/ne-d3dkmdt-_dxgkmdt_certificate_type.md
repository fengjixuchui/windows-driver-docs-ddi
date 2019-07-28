---
UID: NE:d3dkmdt._DXGKMDT_CERTIFICATE_TYPE
title: _DXGKMDT_CERTIFICATE_TYPE (d3dkmdt.h)
description: The DXGKMDT_CERTIFICATE_TYPE enumeration identifies the type of certificate that callers of the DxgkDdiOPMGetCertificateSize and DxgkDdiOPMGetCertificate functions require.
old-location: display\dxgkmdt_certificate_type.htm
tech.root: display
ms.assetid: aad96bf7-46d3-4859-b324-f48cdb99a594
ms.date: 05/10/2018
ms.keywords: DXGKMDT_CERTIFICATE_TYPE, DXGKMDT_CERTIFICATE_TYPE enumeration [Display Devices], DXGKMDT_COPP_CERTIFICATE, DXGKMDT_FORCE_ULONG, DXGKMDT_OPM_CERTIFICATE, DXGKMDT_UAB_CERTIFICATE, DmEnums_837195ed-375e-43ef-a854-1d1f0aab0c84.xml, _DXGKMDT_CERTIFICATE_TYPE, d3dkmdt/DXGKMDT_CERTIFICATE_TYPE, d3dkmdt/DXGKMDT_COPP_CERTIFICATE, d3dkmdt/DXGKMDT_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_CERTIFICATE, d3dkmdt/DXGKMDT_UAB_CERTIFICATE, display.dxgkmdt_certificate_type
ms.topic: enum
f1_keywords:
 - "d3dkmdt/DXGKMDT_CERTIFICATE_TYPE"
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
- d3dkmdt.h
api_name:
- DXGKMDT_CERTIFICATE_TYPE
product:
- Windows
targetos: Windows
req.typenames: DXGKMDT_CERTIFICATE_TYPE
---

# _DXGKMDT_CERTIFICATE_TYPE enumeration


## -description


The DXGKMDT_CERTIFICATE_TYPE enumeration identifies the type of certificate that callers of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size">DxgkDdiOPMGetCertificateSize</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate">DxgkDdiOPMGetCertificate</a> functions require. 


## -enum-fields




### -field DXGKMDT_OPM_CERTIFICATE

Indicates an Output Protection Management (OPM) certificate. 


### -field DXGKMDT_COPP_CERTIFICATE

Indicates a Certified Output Protection Protocol (COPP) certificate. 


### -field DXGKMDT_UAB_CERTIFICATE

Indicates a User Accessible Bus (UAB) certificate. 


### -field DXGKMDT_INDIRECT_DISPLAY_CERTIFICATE


### -field DXGKMDT_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value. 


## -remarks



For more information about certificates that are used with OPM, download the Output Content Protection document at the <a href="https://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate">DxgkDdiOPMGetCertificate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size">DxgkDdiOPMGetCertificateSize</a>
 

 

