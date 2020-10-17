---
UID: NE:d3dumddi._DDIAUTHENTICATEDCHANNELTYPE
title: _DDIAUTHENTICATEDCHANNELTYPE (d3dumddi.h)
description: The DDIAUTHENTICATEDCHANNELTYPE enumeration contains values that identify authenticated-channel types.
old-location: display\ddiauthenticatedchanneltype.htm
tech.root: display
ms.assetid: 431575b7-1173-448c-98a9-790bc2721da0
ms.date: 05/10/2018
keywords: ["DDIAUTHENTICATEDCHANNELTYPE enumeration"]
ms.keywords: D3D_other_Structs_ac5c5f50-3e64-483f-86d1-a0cd99f0578b.xml, DDIAUTHENTICATEDCHANNELTYPE, DDIAUTHENTICATEDCHANNELTYPE enumeration [Display Devices], DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE, DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE, _DDIAUTHENTICATEDCHANNELTYPE, d3dumddi/DDIAUTHENTICATEDCHANNELTYPE, d3dumddi/DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE, d3dumddi/DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE, display.ddiauthenticatedchanneltype
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DDIAUTHENTICATEDCHANNELTYPE is supported beginning with the Windows 7 operating system.
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
req.typenames: DDIAUTHENTICATEDCHANNELTYPE
f1_keywords:
 - _DDIAUTHENTICATEDCHANNELTYPE
 - d3dumddi/_DDIAUTHENTICATEDCHANNELTYPE
 - DDIAUTHENTICATEDCHANNELTYPE
 - d3dumddi/DDIAUTHENTICATEDCHANNELTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DDIAUTHENTICATEDCHANNELTYPE
---

# _DDIAUTHENTICATEDCHANNELTYPE enumeration


## -description

The DDIAUTHENTICATEDCHANNELTYPE enumeration contains values that identify authenticated-channel types.

## -enum-fields

### -field DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE

The value specifies that the authenticated-channel type is software.

### -field DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE

The value specifies that the authenticated-channel type is hardware.

## -remarks

The user-mode display driver receives a DDIAUTHENTICATEDCHANNELTYPE-typed value in the <b>ChannelType</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_ddicertificateinfo">DDICERTIFICATEINFO</a> structure. The <b>pInfo</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a> structure points to this DDICERTIFICATEINFO structure when the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function is called with the D3DDDICAPS_GETCERTIFICATE value set in the <b>Type</b> member of D3DDDIARG_GETCAPS. 

The Microsoft Direct3D runtime specifies a DDIAUTHENTICATEDCHANNELTYPE-typed value in the <b>ChannelType</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createauthenicatedchannel">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a> structure that the <i>pData</i> parameter points to in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createauthenticatedchannel">CreateAuthenticatedChannel</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createauthenticatedchannel">CreateAuthenticatedChannel</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createauthenicatedchannel">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_ddicertificateinfo">DDICERTIFICATEINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>