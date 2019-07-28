---
UID: NE:fwpsk.FWPS_FIELDS_RPC_EP_ADD_
title: FWPS_FIELDS_RPC_EP_ADD_ (fwpsk.h)
description: The FWPS_FIELDS_RPC_EP_ADD enumeration type specifies the data field identifiers for the FWPS_LAYER_RPC_EP_ADD run-time filtering layer.
old-location: netvista\fwps_fields_rpc_ep_add.htm
tech.root: netvista
ms.assetid: 9062fe5f-4384-4466-a15f-c62f2f429699
ms.date: 05/02/2018
ms.keywords: FWPS_FIELDS_RPC_EP_ADD, FWPS_FIELDS_RPC_EP_ADD enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_RPC_EP_ADD_, FWPS_FIELD_RPC_EP_ADD_EP_FLAGS, FWPS_FIELD_RPC_EP_ADD_EP_VALUE, FWPS_FIELD_RPC_EP_ADD_MAX, FWPS_FIELD_RPC_EP_ADD_PROCESS_WITH_RPC_IF_UUID, FWPS_FIELD_RPC_EP_ADD_PROTOCOL, fwpsk/FWPS_FIELDS_RPC_EP_ADD, fwpsk/FWPS_FIELD_RPC_EP_ADD_EP_FLAGS, fwpsk/FWPS_FIELD_RPC_EP_ADD_EP_VALUE, fwpsk/FWPS_FIELD_RPC_EP_ADD_MAX, fwpsk/FWPS_FIELD_RPC_EP_ADD_PROCESS_WITH_RPC_IF_UUID, fwpsk/FWPS_FIELD_RPC_EP_ADD_PROTOCOL, netvista.fwps_fields_rpc_ep_add, wfp_ref_5_const_3_data_fields_427e308c-dcc3-4e3b-a569-9838623abff6.xml
ms.topic: enum
f1_keywords:
 - "fwpsk/FWPS_FIELDS_RPC_EP_ADD"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Vista.
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
- fwpsk.h
api_name:
- FWPS_FIELDS_RPC_EP_ADD
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_RPC_EP_ADD
---

# FWPS_FIELDS_RPC_EP_ADD_ enumeration


## -description


The FWPS_FIELDS_RPC_EP_ADD enumeration type specifies the data field identifiers for the
  FWPS_LAYER_RPC_EP_ADD 
  <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layer</a>.


## -enum-fields




### -field FWPS_FIELD_RPC_EP_ADD_PROCESS_WITH_RPC_IF_UUID

The UUID of the process with the RPC interface.


### -field FWPS_FIELD_RPC_EP_ADD_PROTOCOL

The possible condition values are:

<ul><li>RPC_PROTSEQ_TCP</li><li>RPC_PROTSEQ_HTTP</li><li>RPC_PROTSEQ_NMP</li></ul>


### -field FWPS_FIELD_RPC_EP_ADD_EP_VALUE

Reserved for internal use.


### -field FWPS_FIELD_RPC_EP_ADD_EP_FLAGS

Reserved for internal use.


### -field FWPS_FIELD_RPC_EP_ADD_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

