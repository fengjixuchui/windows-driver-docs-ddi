---
UID: NE:ndis._NDIS_PARAMETER_TYPE
title: _NDIS_PARAMETER_TYPE (ndis.h)
description: The NDIS_PARAMETER_TYPE enumeration type identifies the type of a registry entry.
old-location: netvista\ndis_parameter_type.htm
tech.root: netvista
ms.assetid: f17e390a-fa13-4435-ad1e-3fecc035ec41
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PARAMETER_TYPE, NDIS_PARAMETER_TYPE, NDIS_PARAMETER_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisParameterBinary, NdisParameterHexInteger, NdisParameterInteger, NdisParameterMultiString, NdisParameterString, PNDIS_PARAMETER_TYPE, PNDIS_PARAMETER_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_PARAMETER_TYPE, ndis/NDIS_PARAMETER_TYPE, ndis/NdisParameterBinary, ndis/NdisParameterHexInteger, ndis/NdisParameterInteger, ndis/NdisParameterMultiString, ndis/NdisParameterString, ndis/PNDIS_PARAMETER_TYPE, ndis_configuration_ref_05a453df-2660-470b-8eaf-7a59dcb20e04.xml, netvista.ndis_parameter_type"
ms.topic: enum
f1_keywords:
 - "ndis/NDIS_PARAMETER_TYPE"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP.
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
- ndis.h
api_name:
- NDIS_PARAMETER_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_PARAMETER_TYPE, *PNDIS_PARAMETER_TYPE
---

# _NDIS_PARAMETER_TYPE enumeration


## -description


The NDIS_PARAMETER_TYPE enumeration type identifies the type of a registry entry.


## -enum-fields




### -field NdisParameterInteger

An integer in decimal notation.


### -field NdisParameterHexInteger

An integer in hexadecimal notation.


### -field NdisParameterString

A string of type NDIS_STRING.


### -field NdisParameterMultiString

A multistring parameter of the REG_MULTI_SZ type.


### -field NdisParameterBinary

A binary value of type REG_BINARY.


## -remarks



The NDIS_PARAMETER_TYPE enumeration type is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_parameter">
    NDIS_CONFIGURATION_PARAMETER</a> structure and in the 
    <i>ParameterType</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_parameter">NDIS_CONFIGURATION_PARAMETER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>
 

 

