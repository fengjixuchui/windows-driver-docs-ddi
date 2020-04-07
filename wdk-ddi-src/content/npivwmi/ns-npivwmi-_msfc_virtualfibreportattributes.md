---
UID: NS:npivwmi._MSFC_VirtualFibrePortAttributes
title: _MSFC_VirtualFibrePortAttributes (npivwmi.h)
description: The MSFC_VirtualFibrePortAttributes structure contains attribute information for a virtual port.
old-location: storage\msfc_virtualfibreportattributes.htm
tech.root: storage
ms.assetid: FD8D6063-E6DD-4EA6-9675-774C58C08B40
ms.date: 03/29/2018
keywords: ["_MSFC_VirtualFibrePortAttributes structure"]
ms.keywords: "*PMSFC_VirtualFibrePortAttributes, MSFC_VirtualFibrePortAttributes, MSFC_VirtualFibrePortAttributes structure [Storage Devices], PMSFC_VirtualFibrePortAttributes, PMSFC_VirtualFibrePortAttributes structure pointer [Storage Devices], _MSFC_VirtualFibrePortAttributes, npivwmi/MSFC_VirtualFibrePortAttributes, npivwmi/PMSFC_VirtualFibrePortAttributes, storage.msfc_virtualfibreportattributes"
f1_keywords:
 - "npivwmi/MSFC_VirtualFibrePortAttributes"
req.header: npivwmi.h
req.include-header: Npivwmi.h
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
- npivwmi.h
api_name:
- MSFC_VirtualFibrePortAttributes
product:
- Windows
targetos: Windows
req.typenames: MSFC_VirtualFibrePortAttributes, *PMSFC_VirtualFibrePortAttributes
---

# _MSFC_VirtualFibrePortAttributes structure


## -description


The MSFC_VirtualFibrePortAttributes structure contains attribute information for a virtual port.


## -struct-fields




### -field Status

The virtual port status.


### -field FCId

The fabric ID of the virtual port.


### -field VirtualName

The symbolic name of the virtual port.


### -field Tag

A value for identifying the virtual port. This member provides a 128-bit width to accommodate a unique identifier.


### -field WWPN

The world wide port name of the physical port.


### -field WWNN

The world wide node name of the physical port.


### -field FabricWWN

The world wide port name of the fabric.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-virtualfibreportattributes-wmi-class">MSFC_VirtualFibrePortAttributes WMI Class</a>
 

 

