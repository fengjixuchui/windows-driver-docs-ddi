---
UID: NS:1394._IRB_REQ_BUS_RESET
title: _IRB_REQ_BUS_RESET (1394.h)
description: This structure contains the fields necessary for the 1394 bus driver to create a bus reset request.
old-location: ieee\irb_req_bus_reset.htm
tech.root: IEEE
ms.assetid: 56B7D001-2EC3-4397-B520-193CCF52A9EE
ms.date: 02/15/2018
keywords: ["_IRB_REQ_BUS_RESET structure"]
ms.keywords: 1394/IRB_REQ_BUS_RESET, IEEE.irb_req_bus_reset, IRB_REQ_BUS_RESET, IRB_REQ_BUS_RESET structure [Buses], _IRB_REQ_BUS_RESET
f1_keywords:
 - "1394/IRB_REQ_BUS_RESET"
req.header: 1394.h
req.include-header: 
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
- 1394.h
api_name:
- IRB_REQ_BUS_RESET
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_BUS_RESET
---

# _IRB_REQ_BUS_RESET structure


## -description


This structure contains the fields necessary for the 1394 bus driver to create a bus reset request.


## -struct-fields




### -field fulFlags

Set this flag to BUS_RESET_FLAGS_FORCE_ROOT to make the local node the root node. All other values indicate that the node is not root.

