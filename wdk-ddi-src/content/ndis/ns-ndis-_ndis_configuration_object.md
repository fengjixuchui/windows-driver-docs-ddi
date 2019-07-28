---
UID: NS:ndis._NDIS_CONFIGURATION_OBJECT
title: _NDIS_CONFIGURATION_OBJECT (ndis.h)
description: The NDIS_CONFIGURATION_OBJECT structure defines the attributes of a configuration object that an NDIS driver can pass to the NdisOpenConfigurationEx function.
old-location: netvista\ndis_configuration_object.htm
tech.root: netvista
ms.assetid: 8fa80414-c87a-4f05-b99c-5153f08a0862
ms.date: 05/02/2018
ms.keywords: "*PNDIS_CONFIGURATION_OBJECT, NDIS_CONFIGURATION_OBJECT, NDIS_CONFIGURATION_OBJECT structure [Network Drivers Starting with Windows Vista], PNDIS_CONFIGURATION_OBJECT, PNDIS_CONFIGURATION_OBJECT structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CONFIGURATION_OBJECT, ndis/NDIS_CONFIGURATION_OBJECT, ndis/PNDIS_CONFIGURATION_OBJECT, ndis_configuration_ref_aa617bdd-fe13-11d9-8a38-0030ab150798.xml, netvista.ndis_configuration_object"
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_CONFIGURATION_OBJECT"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- NDIS_CONFIGURATION_OBJECT
product:
- Windows
targetos: Windows
req.typenames: NDIS_CONFIGURATION_OBJECT, *PNDIS_CONFIGURATION_OBJECT
---

# _NDIS_CONFIGURATION_OBJECT structure


## -description


The NDIS_CONFIGURATION_OBJECT structure defines the attributes of a configuration object that an NDIS
  driver can pass to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisopenconfigurationex">
  NdisOpenConfigurationEx</a> function.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_CONFIGURATION_OBJECT structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CONFIGURATION_OBJECT, the 
     <b>Revision</b> member to NDIS_CONFIGURATION_OBJECT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_CONFIGURATION_OBJECT_REVISION_1.


### -field NdisHandle

An NDIS handle that the caller obtained during initialization.


### -field Flags

A bitwise OR of the following flags:
     





#### NDIS_CONFIG_FLAG_FILTER_INSTANCE_CONFIGURATION

Set this flag if a monitoring filter driver must access the filter module configuration for a
       specific filter module when there are multiple filter modules configured over the same miniport
       adapter. Modifying filter drivers must not use this flag.


## -remarks



To configuration parameters in the registry, an NDIS driver can use the NDIS_CONFIGURATION_OBJECT
    structure to define a configuration object and then call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a> function
    to get a configuration handle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>
 

 

