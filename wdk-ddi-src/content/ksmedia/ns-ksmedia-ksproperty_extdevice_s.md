---
UID: NS:ksmedia.__unnamed_struct_134
title: KSPROPERTY_EXTDEVICE_S (ksmedia.h)
description: The KSPROPERTY_EXTDEVICE_S structure describes an external device and its capabilities.
old-location: stream\ksproperty_extdevice_s.htm
tech.root: stream
ms.assetid: da866f7e-f2c6-4926-bbde-db0629571c57
ms.date: 04/30/2019
keywords: ["KSPROPERTY_EXTDEVICE_S structure"]
ms.keywords: "*PKSPROPERTY_EXTDEVICE_S, KSPROPERTY_EXTDEVICE_S, KSPROPERTY_EXTDEVICE_S structure [Streaming Media Devices], PKSPROPERTY_EXTDEVICE_S, PKSPROPERTY_EXTDEVICE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_EXTDEVICE_S, ksmedia/PKSPROPERTY_EXTDEVICE_S, stream.ksproperty_extdevice_s, vidcapstruct_7c8b60d9-303e-489a-8c93-39d91cda2819.xml"
f1_keywords:
 - "ksmedia/KSPROPERTY_EXTDEVICE_S"
 - "KSPROPERTY_EXTDEVICE_S"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
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
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSPROPERTY_EXTDEVICE_S
targetos: Windows
req.typenames: KSPROPERTY_EXTDEVICE_S, *PKSPROPERTY_EXTDEVICE_S
---

# KSPROPERTY_EXTDEVICE_S structure


## -description


The KSPROPERTY_EXTDEVICE_S structure describes an external device and its capabilities.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field u


### -field u.Capabilities

Describes the external device's capabilities.


### -field u.DevPort

Specifies the external device's port. For example:

DEV_PORT_1394

DEV_PORT_USB


### -field u.PowerState

Specifies the external device's power state:

ED_POWER_ON

ED_POWER_STANDBY

ED_POWER_OFF


### -field u.pawchString

Specifies the external device's ID and version.


### -field u.NodeUniqueID

Specifies the external device's unique node Id.


## -remarks



Any ED_Xxx or DEV_PORT_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagdevcaps">DEVCAPS</a>



<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>
 

 

