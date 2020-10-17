---
UID: NC:ndis.PROTOCOL_RECEIVE_NET_BUFFER_LISTS
title: PROTOCOL_RECEIVE_NET_BUFFER_LISTS (ndis.h)
description: The ProtocolReceiveNetBufferLists function processes receive indications from underlying drivers.Note  You must declare the function by using the PROTOCOL_RECEIVE_NET_BUFFER_LISTS type.
old-location: netvista\protocolreceivenetbufferlists.htm
tech.root: netvista
ms.assetid: c964b4b8-ab07-4a07-9965-5cc06c028c20
ms.date: 05/02/2018
keywords: ["PROTOCOL_RECEIVE_NET_BUFFER_LISTS callback function"]
ms.keywords: PROTOCOL_RECEIVE_NET_BUFFER_LISTS, PROTOCOL_RECEIVE_NET_BUFFER_LISTS callback, ProtocolReceiveNetBufferLists, ProtocolReceiveNetBufferLists callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolReceiveNetBufferLists, ndis_sendrcv_ref_80c46411-a010-442f-a978-5f9227abb70a.xml, netvista.protocolreceivenetbufferlists
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PROTOCOL_RECEIVE_NET_BUFFER_LISTS
 - ndis/PROTOCOL_RECEIVE_NET_BUFFER_LISTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - ProtocolReceiveNetBufferLists
---

# PROTOCOL_RECEIVE_NET_BUFFER_LISTS callback function


## -description

The 
  <i>ProtocolReceiveNetBufferLists</i> function processes receive indications from underlying drivers.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param ProtocolBindingContext 

[in]
A handle to a context area that the protocol driver allocated to maintain state information for a
     binding. This handle was passed to NDIS in a previous call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.

### -param NetBufferLists 

[in]
A linked list of 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that the
     underlying driver allocated. Each <b>NET_BUFFER_LIST</b> structure is usually associated with one 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

### -param PortNumber 

[in]
A port number that identifies a miniport adapter port. The default port number of a miniport
     adapter is zero. Protocol drivers that do not use miniport adapter ports should ignore this
     parameter.

### -param NumberOfNetBufferLists 

[in]
The number of <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that are in the linked list of structures at 
     <i>NetBufferLists</i> .

### -param ReceiveFlags 

[in]
Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     





#### NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.



#### NDIS_RECEIVE_FLAGS_RESOURCES

Specifies that NDIS reclaims ownership of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures and any attached
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures immediately after the call to 
       <i>ProtocolReceiveNetBufferLists</i> returns.



#### NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE

Specifies that all of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> have the same protocol type (EtherType).



#### NDIS_RECEIVE_FLAGS_SINGLE_VLAN

Specifies that all of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VLAN.



#### NDIS_RECEIVE_FLAGS_PERFECT_FILTERED

Specifies that all of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> include only data that matches the packet filter and multicast list that are
       assigned to the miniport adapter.



#### NDIS_RECEIVE_FLAGS_SINGLE_QUEUE

Specifies that all the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VM queue. A miniport driver must set this flag for all receive
       indications on a queue if the <b>NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION</b> flag was set
       in the 
       <b>Flags</b> member of the 
       <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_parameters">
       NDIS_RECEIVE_QUEUE_PARAMETERS</a> structure when that queue was allocated.



#### NDIS_RECEIVE_FLAGS_SHARED_MEMORY_INFO_VALID

Specifies that all the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> contain shared memory information that is valid. When this flag is set on a
       received <b>NET_BUFFER_LIST</b>, NDIS treats the shared memory information as valid. When this flag is not
       set, NDIS and drivers ignore the shared memory information. For example, intermediate drivers that
       modify packet data can use this flag to determine if data should be copied. Miniport drivers can use
       the flag to determine how to free the memory that is associated with a VM queue when a queue is
       deleted.



#### NDIS_RECEIVE_FLAGS_MORE_NBLS

Reserved.

## -remarks

<i>ProtocolReceiveNetBufferLists</i> is a required function for protocol drivers. NDIS calls 
    <i>ProtocolReceiveNetBufferLists</i> after a bound miniport driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
    NdisMIndicateReceiveNetBufferLists</a> function. A call to 
    <i>ProtocolReceiveNetBufferLists</i> can also occur as a result of a loopback.

If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter is not set, the protocol driver retains ownership of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures until it calls
    the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreturnnetbufferlists">
    NdisReturnNetBufferLists</a> function.

If NDIS sets the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag the protocol driver cannot retain the
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure and associated resources. The set <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag indicates
    that an underlying driver is running low on receive resources. In this case, the 
    <i>ProtocolReceiveNetBufferLists</i> function should copy the received data into protocol-allocated
    storage and return as quickly as possible.

<div class="alert"><b>Note</b>  If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag is set, the protocol driver must retain
    the original set of <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the linked list. For example, when this flag is set the
    driver might process the structures and indicate them up the stack one at a time but before the function
    returns it must restore the original linked list.</div>
<div> </div>
On a multiprocessor system, this function can execute concurrently on more than one processor. Apply
    protection (for example, use spin locks) to critical data structures that are accessed by 
    <i>ProtocolReceiveNetBufferLists</i>.

NDIS calls 
    <i>ProtocolReceiveNetBufferLists</i> at IRQL<= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolReceiveNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolReceiveNetBufferLists</i> function that is named "MyReceiveNetBufferLists", use the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> type as shown in this code example:


```
PROTOCOL_RECEIVE_NET_BUFFER_LISTS MyReceiveNetBufferLists;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyReceiveNetBufferLists(
    NDIS_HANDLE  ProtocolBindingContext,
    PNET_BUFFER_LIST  NetBufferLists,
    NDIS_PORT_NUMBER  PortNumber,
    ULONG  NumberOfNetBufferLists,
    ULONG ReceiveFlags
    )
  {...}
```

The <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
   MiniportReturnNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_parameters">NDIS_RECEIVE_QUEUE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreturnnetbufferlists">NdisReturnNetBufferLists</a>