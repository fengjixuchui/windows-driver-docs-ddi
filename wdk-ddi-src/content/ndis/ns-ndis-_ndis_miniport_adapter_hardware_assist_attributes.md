---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
title: _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES (ndis.h)
description: The NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure specifies the hardware-assisted attributes of the network adapter.
old-location: netvista\ndis_miniport_adapter_hardware_assist_attributes.htm
tech.root: netvista
ms.assetid: b0662a2c-feb6-4d66-89c9-586c2859b78b
ms.date: 05/02/2018
keywords: ["NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, header_data_split_ref_cedb1474-09f1-4340-9d13-d6d7f5b96ed4.xml, ndis/NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, netvista.ndis_miniport_adapter_hardware_assist_attributes"
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
targetos: Windows
req.typenames: NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
f1_keywords:
 - _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
 - ndis/_NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
 - PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
 - ndis/PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
 - NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
 - ndis/NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure


## -description

The <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure specifies the hardware-assisted attributes of the network adapter.

## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES.
     

To indicate the version of the <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure, set the 
     <b>Revision</b> member to one of the following values:





#### NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_3

Added various members for NDIS 6.30.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_3.



#### NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_2

Added the 
        <b>HardwareReceiveFilterCapabilities</b>, 
        <b>CurrentReceiveFilterCapabilities</b>, 
        <b>HardwareNicSwitchCapabilities</b>, and 
        <b>CurrentNicSwitchCapabilities</b> members for NDIS 6.20.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_2.



#### NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_1

Original version for NDIS 6.1.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_1.

### -field HDSplitAttributes

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_hd_split_attributes">NDIS_HD_SPLIT_ATTRIBUTES</a> structure
     that represents the header-data split capabilities that the network adapter provides. If the network adapter does not support the header-data split feature, set 
     <b>HDSplitAttributes</b> to <b>NULL</b>.

### -field HardwareReceiveFilterCapabilities

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_capabilities">
     NDIS_RECEIVE_FILTER_CAPABILITIES</a> structure. This structure specifies the hardware receive
     filtering capabilities of the network adapter. This value can be <b>NULL</b> if the network adapter does not
     support receive filtering.

<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>CurrentReceiveFilterCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>

### -field CurrentReceiveFilterCapabilities

A pointer to an NDIS_RECEIVE_FILTER_CAPABILITIES structure. This structure specifies the receive
     filtering capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the
     network adapter does not support receive filtering.

<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>HardwareReceiveFilterCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>

### -field HardwareNicSwitchCapabilities

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_capabilities">
     NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the hardware NIC switch
     capabilities of the network adapter. This value can be <b>NULL</b> if the network adapter does not support
     NIC switch features or receive filtering.

<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>CurrentNicSwitchCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>

### -field CurrentNicSwitchCapabilities

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_capabilities">NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the NIC switch
     capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the network adapter does not support NIC switch features or receive filtering.

<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>HardwareNicSwitchCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>

### -field HardwareSriovCapabilities

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_sriov_capabilities">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter hardware. This value can be <b>NULL</b> if the network adapter does not support SR-IOV.

For more information on SR-IOV, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/single-root-i-o-virtualization--sr-iov-">Single Root I/O Virtualization (SR-IOV)</a>.

<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>CurrentSriovCapabilities</b>, <b>HardwareNicSwitchCapabilities</b>, and <b>CurrentNicSwitchCapabilities</b> members must not be set to <b>NULL</b>.</div>
<div> </div>

### -field CurrentSriovCapabilities

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_sriov_capabilities">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the SR-IOV capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the network adapter does not support SR-IOV. 

<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>HardwareSriovCapabilities</b>, <b>HardwareNicSwitchCapabilities</b>, and <b>CurrentNicSwitchCapabilities</b> members must not be set to <b>NULL</b>.</div>
<div> </div>

### -field HardwareQosCapabilities

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_qos_capabilities">NDIS_QOS_CAPABILITIES</a> structure. This structure specifies the hardware capabilities that the network adapter supports for NDIS quality of service (QoS) over the IEEE 802.1 Data Center Bridging (DCB) interface. This value can be <b>NULL</b> if the network adapter does not support NDIS QoS hardware capabilities for DCB. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-qos-for-data-center-bridging">NDIS QoS for Data Center Bridging</a>.

<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>CurrentQosCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>

### -field CurrentQosCapabilities

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_qos_capabilities">NDIS_QOS_CAPABILITIES</a> structure. This structure specifies the hardware capabilities that are currently enabled on the network adapter for NDIS QoS over the DCB interface. This value can be <b>NULL</b> if the network adapter does not support NDIS QoS hardware capabilities for DCB. 

If the adapter supports NDIS QoS capabilties but those capabilities are disabled, the miniport driver must set all members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_qos_capabilities">NDIS_QOS_CAPABILITIES</a> structure (with the exception of the <b>Header</b> member) to zero.

<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>HardwareQosCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>

### -field HardwareGftOffloadCapabilities

### -field CurrentGftOffloadCapabilities

## -remarks

To register the hardware-assisted capabilities of the underlying network adapter, the miniport driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function. The driver passes 
    an initialized <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b>
    structure to the <i>MiniportAttributes</i> parameter of this function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_hd_split_attributes">NDIS_HD_SPLIT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_capabilities">NDIS_NIC_SWITCH_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_qos_capabilities">NDIS_QOS_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_capabilities">
   NDIS_RECEIVE_FILTER_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_sriov_capabilities">NDIS_SRIOV_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>

