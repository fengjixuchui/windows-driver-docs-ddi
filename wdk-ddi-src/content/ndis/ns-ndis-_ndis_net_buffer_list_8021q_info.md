---
UID: NS:ndis._NDIS_NET_BUFFER_LIST_8021Q_INFO
title: _NDIS_NET_BUFFER_LIST_8021Q_INFO (ndis.h)
description: The NDIS_NET_BUFFER_LIST_8021Q_INFO structure specifies 802.1Q information that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_net_buffer_list_8021q_info.htm
tech.root: netvista
ms.assetid: 4314d3f9-2457-41f6-844c-197e5d05b0fe
ms.date: 05/02/2018
ms.keywords: "*PNDIS_NET_BUFFER_LIST_8021Q_INFO, NDIS_NET_BUFFER_LIST_8021Q_INFO, NDIS_NET_BUFFER_LIST_8021Q_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NET_BUFFER_LIST_8021Q_INFO, PNDIS_NET_BUFFER_LIST_8021Q_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NET_BUFFER_LIST_8021Q_INFO, ndis/NDIS_NET_BUFFER_LIST_8021Q_INFO, ndis/PNDIS_NET_BUFFER_LIST_8021Q_INFO, ndis_netbuf_structures_ref_6581b8a1-543e-46fe-a513-f8b2b6780cdd.xml, netvista.ndis_net_buffer_list_8021q_info"
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_NET_BUFFER_LIST_8021Q_INFO"
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
- NDIS_NET_BUFFER_LIST_8021Q_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_NET_BUFFER_LIST_8021Q_INFO, *PNDIS_NET_BUFFER_LIST_8021Q_INFO
---

# _NDIS_NET_BUFFER_LIST_8021Q_INFO structure


## -description


The NDIS_NET_BUFFER_LIST_8021Q_INFO structure specifies 802.1Q information that is associated with a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.


## -struct-fields




### -field TagHeader

A member in the union that is contained in NDIS_NET_BUFFER_LIST_8021Q_INFO. 802.3 Ethernet
      miniport drivers use 
      <b>TagHeader</b> to access 802.1Q information. 
      <b>TagHeader</b> is a bit field with the following members:


### -field TagHeader.UserPriority

Specifies 802.1p priority information that is used to establish packet priority in shared-media
       802 networks. The bits in this member specify an 802.1p priority value.


### -field TagHeader.CanonicalFormatId

This member should be set to zero, which indicates that all MAC address information present in a
       packet is in canonical format (that is, simplest form).


### -field TagHeader.VlanId

Identifies the VLAN that a packet belongs to. Outgoing packets are marked with the VLAN
       identifier.


### -field TagHeader.Reserved

This member is reserved and should be set to zero.


### -field WLanTagHeader

A member in the union that is contained in NDIS_NET_BUFFER_LIST_8021Q_INFO. Native 802.11
      miniport drivers use 
      <b>WLanTagHeader</b> to access 802.1Q information. 
      <b>WLanTagHeader</b> is a bit field with the following members:


### -field WLanTagHeader.UserPriority

Specifies 802.1p priority information that is used to establish packet priority in shared-media
       802 networks. The bits in this member specify an 802.1p priority value.


### -field WLanTagHeader.CanonicalFormatId

This member should be set to zero, which indicates that all MAC address information present in a
       packet is in canonical format (that is, simplest form).


### -field WLanTagHeader.VlanId

Identifies the VLAN that a packet belongs to. Outgoing packets are marked with the VLAN
       identifier.


### -field WLanTagHeader.WMMInfo

A wireless multimedia (WMM) integer value that is the same as the traffic identifier (TID) fields
        that appear in certain frames that are used to deliver and to control the delivery of 802.1Q Quality
        of Service (QoS) data. The values 0 through 7 represent QoS user priorities (UPs) for the MAC service
        data units (MSDUs). The values 8 through 15 are reserved. Therefore, the higest bit in 
        <b>WMMInfo</b> must be zero.

<div class="alert"><b>Note</b>  Traffic specification (TSPEC) and traffic classification (TCLAS) are not
        supported.</div>
<div> </div>

### -field WLanTagHeader.Reserved

This member is reserved and should be set to zero.


### -field Value

A member in the union that is contained in NDIS_NET_BUFFER_LIST_8021Q_INFO. 
      <b>Value</b> contains a pointer value that is type-compatible with the 
      <b>NetBufferListInfo</b> member in the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.


## -remarks



To retrieve or insert 802.1Q information that is associated with a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure, an NDIS driver
    calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a> macro and specifies
    the 
    <b>Ieee8021QNetBufferListInfo</b> information type.

The NET_BUFFER_LIST_INFO macro returns the pointer that is specified in the 
    <b>Value</b> member of the NDIS_NET_BUFFER_LIST_8021Q_INFO structure. The NDIS driver can use the 
    <b>TagHeader</b> or 
    <b>WLanTagHeader</b> member of the union to access specific types of information, such as 802.1p priority
    and VLAN identifier information. The 
    <b>WLanTagHeader</b> member provides access to the wireless multimedia (WMM) information in addition to
    the information that is available through the 
    <b>TagHeader</b> member.

Miniport drivers that support the 802.1Q tag in hardware must use the NDIS_NET_BUFFER_LIST_8021Q_INFO
    structure for transmit and receive operations:

<ul>
<li>
For transmit operations, the miniport driver must check for NDIS_NET_BUFFER_LIST_8021Q_INFO OOB data
      in the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. The miniport
      driver must ensure that the hardware creates the 802.1Q tag from the NDIS_NET_BUFFER_LIST_8021Q_INFO
      specifications and insert it into the Ethernet frame.

</li>
<li>
For receive operations, the miniport driver must remove the 802.1Q tag from the Ethernet frame and
      map the 802.1Q tag information into the NDIS_NET_BUFFER_LIST_8021Q_INFO OOB data in the NET_BUFFER_LIST
      structure before indicating the data to NDIS with the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
      NdisMIndicateReceiveNetBufferLists</a> function.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>
 

 

