---
UID: NS:1394._NODE_ADDRESS
title: _NODE_ADDRESS (1394.h)
description: The NODE_ADDRESS structure specifies the 10-bit bus number and 6-bit node number that serve as the node address for a 1394 node.
old-location: ieee\node_address.htm
tech.root: IEEE
ms.assetid: ecafa166-356e-48d6-84c4-0f0c339289ac
ms.date: 02/15/2018
keywords: ["NODE_ADDRESS structure"]
ms.keywords: "*PNODE_ADDRESS, 1394/NODE_ADDRESS, 1394/PNODE_ADDRESS, 1394stct_4b87009c-620b-4840-aea3-52e059d388cd.xml, IEEE.node_address, NODE_ADDRESS, NODE_ADDRESS structure [Buses], PNODE_ADDRESS, PNODE_ADDRESS structure pointer [Buses], _NODE_ADDRESS"
req.header: 1394.h
req.include-header: 1394.h
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
targetos: Windows
req.typenames: NODE_ADDRESS, *PNODE_ADDRESS
f1_keywords:
 - _NODE_ADDRESS
 - 1394/_NODE_ADDRESS
 - PNODE_ADDRESS
 - 1394/PNODE_ADDRESS
 - NODE_ADDRESS
 - 1394/NODE_ADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - NODE_ADDRESS
---

# _NODE_ADDRESS structure


## -description

The NODE_ADDRESS structure specifies the 10-bit bus number and 6-bit node number that serve as the node address for a 1394 node.

## -struct-fields

### -field NA_Node_Number

Specifies the 6-bit node number. This member contains bits 10-15 of the node address.

### -field NA_Bus_Number

Specifies the 10-bit bus number. This member specifies bits 0-10 of the node address.

## -see-also

<a href="/windows-hardware/drivers/ddi/61883/ns-61883-_bus_generation_node">BUS_GENERATION_NODE</a>



<a href="/windows-hardware/drivers/ddi/1394/ns-1394-_io_address">IO_ADDRESS</a>