---
UID: NE:ntddndis._NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
title: _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION (ntddndis.h)
description: The NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration specifies the interrupt moderation setting of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch.
old-location: netvista\ndis_nic_switch_vport_interrupt_moderation.htm
tech.root: netvista
ms.assetid: 86ec2e8f-1a89-4c0a-b761-d9bf0d3dc35a
ms.date: 05/02/2018
keywords: ["_NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration"]
ms.keywords: "*PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration [Network Drivers Starting with Windows Vista], NdisNicSwitchVPortIntModAdaptive, NdisNicSwitchVPortIntModHigh, NdisNicSwitchVPortIntModLow, NdisNicSwitchVPortIntModMedium, NdisNicSwitchVPortIntModOff, NdisNicSwitchVPortIntModUndefined, PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, netvista.ndis_nic_switch_vport_interrupt_moderation, ntddndis/NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, ntddndis/NdisNicSwitchVPortIntModAdaptive, ntddndis/NdisNicSwitchVPortIntModHigh, ntddndis/NdisNicSwitchVPortIntModLow, ntddndis/NdisNicSwitchVPortIntModMedium, ntddndis/NdisNicSwitchVPortIntModOff, ntddndis/NdisNicSwitchVPortIntModUndefined, ntddndis/PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION"
f1_keywords:
 - "ntddndis/NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION"
 - "NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- Ntddndis.h
api_name:
- NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, *PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
---

# _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration


## -description


The <b>NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION</b> enumeration specifies the interrupt moderation setting of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch.


## -enum-fields




### -field NdisNicSwitchVPortInterruptModerationUndefined


### -field NdisNicSwitchVPortInterruptModerationAdaptive


### -field NdisNicSwitchVPortInterruptModerationOff


### -field NdisNicSwitchVPortInterruptModerationLow


### -field NdisNicSwitchVPortInterruptModerationMedium


### -field NdisNicSwitchVPortInterruptModerationHigh




#### - NdisNicSwitchVPortIntModAdaptive

Interrupt moderation for the VPort is adaptive. This state enables the network adapter to adjust the interrupt moderation rate for the VPort based on the pattern of network traffic.


#### - NdisNicSwitchVPortIntModHigh

Interrupt moderation for the VPort is high.


#### - NdisNicSwitchVPortIntModLow

Interrupt moderation for the VPort is low.


#### - NdisNicSwitchVPortIntModMedium

Interrupt moderation for the VPort is medium.


#### - NdisNicSwitchVPortIntModOff

Interrupt moderation for the VPort is disabled.


#### - NdisNicSwitchVPortIntModUndefined

Interrupt moderation for the VPort is not defined.


## -remarks



The determination of low, medium, and high interrupt moderation levels is determined by the miniport driver based on a hardware algorithm that is based on the network adapter.

The <b>InterruptModeration</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_vport_parameters">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_vport_info">NDIS_NIC_SWITCH_VPORT_INFO</a> structures is an NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration data type. 




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_vport_info">NDIS_NIC_SWITCH_VPORT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_vport_parameters">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a>
 

 

