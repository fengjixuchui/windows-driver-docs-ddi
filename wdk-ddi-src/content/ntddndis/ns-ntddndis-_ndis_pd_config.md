---
UID: NS:ntddndis._NDIS_PD_CONFIG
title: _NDIS_PD_CONFIG (ntddndis.h)
description: This structure holds configuration data for the PD provider.
old-location: netvista\ndis_pd_config.htm
tech.root: netvista
ms.assetid: 2B010641-4CFA-40B6-AB77-BE9F85347134
ms.date: 05/02/2018
ms.keywords: NDIS_PD_CONFIG, NDIS_PD_CONFIG structure [Network Drivers Starting with Windows Vista], _NDIS_PD_CONFIG, netvista.ndis_pd_config, ntddndis/NDIS_PD_CONFIG
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_PD_CONFIG"
req.header: ntddndis.h
req.include-header: Ndis.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_PD_CONFIG
product:
- Windows
targetos: Windows
req.typenames: NDIS_PD_CONFIG
---

# _NDIS_PD_CONFIG structure


## -description


This structure holds configuration data for the PD provider.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_CONFIG</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_CONFIG_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_CONFIG_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field Enabled

A <b>BOOLEAN</b> value that is set to <b>TRUE</b> if the PDPI provider's  PacketDirect capability is enabled. Otherwise, this member is <b>FALSE</b>.


### -field CapabilitiesOffset

If the <b>CapabilitiesSize</b> member is greater than zero, this is a <b>ULONG</b>-aligned pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pd_capabilities">NDIS_PD_CAPABILITIES</a> structure.


### -field CapabilitiesSize

If this member is greater than zero, it contains the size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pd_capabilities">NDIS_PD_CAPABILITIES</a> structure that the <b>CapabilitiesOffset</b> member points to.


## -remarks



This structure must be aligned on an 8-byte boundary.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>
 

 

