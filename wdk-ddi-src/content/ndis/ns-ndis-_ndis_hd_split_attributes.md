---
UID: NS:ndis._NDIS_HD_SPLIT_ATTRIBUTES
title: _NDIS_HD_SPLIT_ATTRIBUTES (ndis.h)
description: The NDIS_HD_SPLIT_ATTRIBUTES structure defines header-data split attributes, if any, that are associated with a miniport adapter.
old-location: netvista\ndis_hd_split_attributes.htm
tech.root: netvista
ms.assetid: c3e28d66-1fe8-4cb0-ada0-4292387da19a
ms.date: 05/02/2018
keywords: ["_NDIS_HD_SPLIT_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_HD_SPLIT_ATTRIBUTES, NDIS_HD_SPLIT_ATTRIBUTES, NDIS_HD_SPLIT_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_HD_SPLIT_ATTRIBUTES, PNDIS_HD_SPLIT_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_HD_SPLIT_ATTRIBUTES, header_data_split_ref_32bcb512-6620-48a5-8073-7b9ef0ef1f18.xml, ndis/NDIS_HD_SPLIT_ATTRIBUTES, ndis/PNDIS_HD_SPLIT_ATTRIBUTES, netvista.ndis_hd_split_attributes"
f1_keywords:
 - "ndis/NDIS_HD_SPLIT_ATTRIBUTES"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
- NDIS_HD_SPLIT_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: NDIS_HD_SPLIT_ATTRIBUTES, *PNDIS_HD_SPLIT_ATTRIBUTES
---

# _NDIS_HD_SPLIT_ATTRIBUTES structure


## -description


The NDIS_HD_SPLIT_ATTRIBUTES structure defines header-data split attributes, if any, that are
  associated with a miniport adapter.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     provider characteristics structure (NDIS_HD_SPLIT_ATTRIBUTES). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_HD_SPLIT_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_OBJECT_HD_SPLIT_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_HD_SPLIT_ATTRIBUTES_REVISION_1.


### -field HardwareCapabilities

The header-data split hardware capabilities that the miniport adapter supports. These capabilities
     should include capabilities that are currently disabled by INF file settings or through the 
     <b>Advanced</b> properties page. The value of 
     <b>HardwareCapabilities</b> is a bitwise OR of the following flags:
     





#### NDIS_HD_SPLIT_CAPS_SUPPORTS_HEADER_DATA_SPLIT

The miniport adapter can split the header and data into separate MDLs that meet the requirements
       for header-data split support.



#### NDIS_HD_SPLIT_CAPS_SUPPORTS_IPV4_OPTIONS

The miniport adapter can split IPv4 Ethernet frames that include IPv4 options. The miniport
       adapter can support splitting some IPv4 options while not splitting others. 
       

<div class="alert"><b>Note</b>  The NIC must not split IPv4 frames that contain unsupported IPv4 options. If an
       IPv4 frame is split, the header portion of the split frame must contain the entire IPv4 header and all
       of the IPv4 options that are present.</div>
<div> </div>


#### NDIS_HD_SPLIT_CAPS_SUPPORTS_IPV6_EXTENSION_HEADERS

The miniport adapter can split IPv6 Ethernet frames that include IPv6 extension headers. The
       miniport adapter can support some IPv6 extension headers while not supporting others. 
       

<div class="alert"><b>Note</b>  The NIC must not split IPv6 frames that contain unsupported IPv6 extension
       headers. If an IPv6 frame is split, the header portion of the split frame must contain the entire IPv6
       header and all of the IPv6 extension headers that are present.</div>
<div> </div>


#### NDIS_HD_SPLIT_CAPS_SUPPORTS_TCP_OPTIONS

The miniport adapter can split TCP frames with other TCP options in addition to the timestamp
       option. The miniport adapter can support some TCP options and not support others.
       

<div class="alert"><b>Note</b>  If the only TCP option in a frame is the timestamp option, the data-split
       provider must be able to split the frame.</div>
<div> </div>
<div class="alert"><b>Note</b>  If a TCP header contains an unsupported TCP option, the NIC must split the frame
       at the beginning of the TCP header or must not split the frame.</div>
<div> </div>

### -field CurrentCapabilities

The current header-data split capabilities that the miniport adapter supports. The miniport driver
     uses the same flags that are defined for the 
     <b>HardwareCapabilities</b> member. In this case, the flags are set to indicate the current capabilities
     that depend on the current configuration settings.


### -field HDSplitFlags

A set of flags that control the status of header-data split for a miniport adapter. The miniport
     driver should set this member to zero before calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> function. After 
     <b>NdisMSetMiniportAttributes</b> successfully returns, the driver must check the flags and configure the
     hardware accordingly. NDIS sets this member with a bitwise OR of the following flags:
     





#### NDIS_HD_SPLIT_ENABLE_HEADER_DATA_SPLIT

If this flag is set, the miniport driver should enable header-data split in the hardware.
       Otherwise, header-data split is disabled. If the computer uses header-data split and the miniport
       driver also set the NDIS_HD_SPLIT_CAPS_SUPPORTS_HEADER_DATA_SPLIT flag in the 
       <b>CurrentCapabilities</b> member, NDIS sets NDIS_HD_SPLIT_ENABLE_HEADER_DATA_SPLIT.


### -field BackfillSize

The backfill size, in bytes, for the data portion of a split frame. The miniport driver should set     
     <b>BackfillSize</b> to zero before calling 
     <b>NdisMSetMiniportAttributes</b>. NDIS sets this member if the miniport driver must pre-allocate
     backfill storage in the data portion for split frames. After 
     <b>NdisMSetMiniportAttributes</b> successfully returns, the driver must use the 
     <b>BackfillSize</b> value that NDIS set to pre-allocate the data buffers.


### -field MaxHeaderSize

The maximum size, in bytes, for the header portion of a split frame. The miniport driver should
     set 
     <b>MaxHeaderSize</b> to zero before calling 
     <b>NdisMSetMiniportAttributes</b>. NDIS sets this member to the maximum size for the header buffer for
     split frames. After 
     <b>NdisMSetMiniportAttributes</b> successfully returns, the driver must use the value that NDIS provided.
     
     

<div class="alert"><b>Note</b>  If the length of a header exceeds 
     <b>MaxHeaderSize</b> because of the presence of IPv4 options, IPSec headers, or IPv6 extension headers,
     the frame must not be split. If a header that includes a TCP or UDP header exceeds 
     <b>MaxHeaderSize</b> because of the presence of TCP header, TCP options, or UDP header, the NIC must
     split the frame at the beginning of the upper layer protocol header or must not split the
     frame.</div>
<div> </div>

## -remarks



To support header-data split, a miniport driver passes a pointer to an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">
    NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure in the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function. The 
    <b>HDSplitAttributes</b> member of NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES contains a pointer to
    the NDIS_HD_SPLIT_ATTRIBUTES structure. A miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
    during initialization.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">
   NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

