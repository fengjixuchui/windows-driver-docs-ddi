---
UID: NS:bthddi._BRB_SCO_UNREGISTER_SERVER
title: _BRB_SCO_UNREGISTER_SERVER (bthddi.h)
description: A profile driver uses the _BRB_SCO_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving SCO connections from remote Bluetooth devices.
old-location: bltooth\_brb_sco_unregister_server.htm
tech.root: bltooth
ms.assetid: a0624d6e-d3e9-45b1-b704-4a05532926f9
ms.date: 04/27/2018
keywords: ["_BRB_SCO_UNREGISTER_SERVER structure"]
ms.keywords: "_BRB_SCO_UNREGISTER_SERVER, _BRB_SCO_UNREGISTER_SERVER structure [Bluetooth Devices], bltooth._brb_sco_unregister_server, bth_structs_36fae461-b66e-42e0-8e66-a890e45abbbb.xml, bthddi/_BRB_SCO_UNREGISTER_SERVER"
f1_keywords:
 - "bthddi/_BRB_SCO_UNREGISTER_SERVER"
 - "_BRB_SCO_UNREGISTER_SERVER"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
- bthddi.h
api_name:
- _BRB_SCO_UNREGISTER_SERVER
targetos: Windows
req.typenames: 
---

# _BRB_SCO_UNREGISTER_SERVER structure


## -description


A profile driver uses the _BRB_SCO_UNREGISTER_SERVER structure to unregister itself as a server
  capable of receiving SCO connections from remote Bluetooth devices.


## -struct-fields




### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field ServerHandle

The handle of the SCO server to unregister, that was obtained earlier from
     BRB_SCO_REGISTER_SERVER.


## -remarks



To unregister itself as a SCO server, a profile driver should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536630(v=vs.85)">
    BRB_SCO_UNREGISTER_SERVER</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536630(v=vs.85)">BRB_SCO_UNREGISTER_SERVER</a>
 

 

