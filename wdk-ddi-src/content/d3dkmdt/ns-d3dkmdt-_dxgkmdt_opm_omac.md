---
UID: NS:d3dkmdt._DXGKMDT_OPM_OMAC
title: _DXGKMDT_OPM_OMAC (d3dkmdt.h)
description: The DXGKMDT_OPM_OMAC structure contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity.
old-location: display\dxgkmdt_opm_omac.htm
tech.root: display
ms.assetid: caa64a32-3772-45b5-898a-78dc51b7f24b
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_OMAC structure"]
ms.keywords: "*PDXGKMDT_OPM_OMAC, DXGKMDT_OPM_OMAC, DXGKMDT_OPM_OMAC structure [Display Devices], DmStructs_8c3b7364-5055-4152-b7ed-4e2d1d910dd4.xml, PDXGKMDT_OPM_OMAC, PDXGKMDT_OPM_OMAC structure pointer [Display Devices], _DXGKMDT_OPM_OMAC, d3dkmdt/DXGKMDT_OPM_OMAC, d3dkmdt/PDXGKMDT_OPM_OMAC, display.dxgkmdt_opm_omac"
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
targetos: Windows
req.typenames: DXGKMDT_OPM_OMAC, *PDXGKMDT_OPM_OMAC
f1_keywords:
 - _DXGKMDT_OPM_OMAC
 - d3dkmdt/_DXGKMDT_OPM_OMAC
 - PDXGKMDT_OPM_OMAC
 - d3dkmdt/PDXGKMDT_OPM_OMAC
 - DXGKMDT_OPM_OMAC
 - d3dkmdt/DXGKMDT_OPM_OMAC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - DXGKMDT_OPM_OMAC
---

# _DXGKMDT_OPM_OMAC structure


## -description

The DXGKMDT_OPM_OMAC structure contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity.

## -struct-fields

### -field abOMAC

A 16-byte array that comprises the OMAC.

## -remarks

For more information about OMAC, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=70417">OMAC-1 algorithm</a>. 

The OMAC-1 parameters that OPM and COPP use are:

<ul>
<li>
<i>E</i> = AES (Advanced Encryption Standard)

</li>
<li>
<i>t</i> = 128 bits

</li>
<li>
<i>K</i> = The 128-bit key that the display miniport driver receives when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> is called.

</li>
<li>
<i>n</i> = 128 bits 

</li>
</ul>
For information about AES, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_configure_parameters">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_requested_information">DXGKMDT_OPM_REQUESTED_INFORMATION</a>

