---
UID: NS:61883._BUS_GENERATION_NODE
title: _BUS_GENERATION_NODE (61883.h)
description: The BUS_GENERATION_NODE structure is used in conjunction with the Av61883_GetUnitInfo request to retrieve bus characteristics.
old-location: ieee\bus_generation_node.htm
tech.root: IEEE
ms.assetid: 8db151ca-6358-41b0-a96a-e69b9d6c2c95
ms.date: 02/15/2018
keywords: ["_BUS_GENERATION_NODE structure"]
ms.keywords: "*PBUS_GENERATION_NODE, 61883/BUS_GENERATION_NODE, 61883/PBUS_GENERATION_NODE, 61883_structures_41921b5c-98f0-4df8-9770-335cc579eb38.xml, BUS_GENERATION_NODE, BUS_GENERATION_NODE structure [Buses], IEEE.bus_generation_node, PBUS_GENERATION_NODE, PBUS_GENERATION_NODE structure pointer [Buses], _BUS_GENERATION_NODE"
f1_keywords:
 - "61883/BUS_GENERATION_NODE"
 - "BUS_GENERATION_NODE"
req.header: 61883.h
req.include-header: 61883.h
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
- 61883.h
api_name:
- BUS_GENERATION_NODE
targetos: Windows
req.typenames: BUS_GENERATION_NODE, *PBUS_GENERATION_NODE
---

# _BUS_GENERATION_NODE structure


## -description


The BUS_GENERATION_NODE structure is used in conjunction with the <a href="https://docs.microsoft.com/previous-versions/ff536983(v=vs.85)">Av61883_GetUnitInfo</a> request to retrieve bus characteristics. 


## -struct-fields




### -field GenerationCount

The current bus generation count.


### -field LocalNodeAddress

The current node address of the local node.


### -field DeviceNodeAddress

The current node address of the device.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff536983(v=vs.85)">Av61883_GetUnitInfo</a>
 

 

