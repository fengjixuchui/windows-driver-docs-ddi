---
UID: NE:ntddndis._NDIS_SWITCH_PORT_TYPE
title: _NDIS_SWITCH_PORT_TYPE (ntddndis.h)
description: The NDIS_SWITCH_PORT_TYPE enumeration specifies the type of a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_type.htm
tech.root: netvista
ms.assetid: 4FCE88BC-6FA1-44D0-9BC1-3065A5EEE1A0
ms.date: 05/02/2018
keywords: ["_NDIS_SWITCH_PORT_TYPE enumeration"]
ms.keywords: NDIS_SWITCH_PORT_TYPE, NDIS_SWITCH_PORT_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortTypeEmulated, NdisSwitchPortTypeExternal, NdisSwitchPortTypeGeneric, NdisSwitchPortTypeInternal, NdisSwitchPortTypeSynthetic, PNDIS_SWITCH_PORT_TYPE, PNDIS_SWITCH_PORT_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_TYPE, netvista.ndis_switch_port_type, ntddndis/NDIS_SWITCH_PORT_TYPE, ntddndis/NdisSwitchPortTypeEmulated, ntddndis/NdisSwitchPortTypeExternal, ntddndis/NdisSwitchPortTypeGeneric, ntddndis/NdisSwitchPortTypeInternal, ntddndis/NdisSwitchPortTypeSynthetic, ntddndis/PNDIS_SWITCH_PORT_TYPE
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_TYPE"
 - "NDIS_SWITCH_PORT_TYPE"
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
- NDIS_SWITCH_PORT_TYPE
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_TYPE
---

# _NDIS_SWITCH_PORT_TYPE enumeration


## -description



The <b>NDIS_SWITCH_PORT_TYPE</b> enumeration specifies the type of  a Hyper-V extensible switch port.  




## -enum-fields




### -field NdisSwitchPortTypeGeneric

This value specifies a generic port type that was created with an earlier version of the extensible switch WMI management platform.


### -field NdisSwitchPortTypeExternal

This value specifies a port that is connected to an external network adapter. This  adapter is exposed in the management operating system that runs in the Hyper-V parent partition. 

The external network adapter provides the connection to the  physical network interface that is available on the host. This allows processes that run in either the management or guest operating systems to send or receive packets over the extensible switch.

<div class="alert"><b>Note</b>  An extensible switch supports no more than one external network adapter. The external network adapter can be bound to one or more underlying physical network adapters. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/external-network-adapters">External Network Adapters</a>.</div>
<div> </div>

### -field NdisSwitchPortTypeSynthetic

This value specifies a port that is connected to a synthetic network adapter. This adapter is exposed in a guest operating system that runs in a Hyper-V child partition.

<div class="alert"><b>Note</b>  A synthetic network adapter is a type of virtual machine (VM) network adapter. This adapter is exposed in a guest operating system that is running Windows Vista or a later version of Windows.</div>
<div> </div>

### -field NdisSwitchPortTypeEmulated

This value specifies a port that is connected to an emulated network adapter. This adapter is exposed in a guest operating system.

<div class="alert"><b>Note</b>  An emulated network adapter is a type of VM network adapter. This adapter can be exposed in a guest operating system that is running Windows XP or a non-Windows operating system.</div>
<div> </div>

### -field NdisSwitchPortTypeInternal

This value specifies a port that is connected to an internal network adapter. This adapter is exposed in the management operating system that runs in the Hyper-V parent partition. 

The internal network adapter provides access to an extensible switch for processes that run in the management operating system. This allows these processes to send or receive packets over the extensible switch.

<div class="alert"><b>Note</b>  An extensible switch supports no more than one internal network adapter. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/internal-network-adapters">Internal Network Adapters</a>.</div>
<div> </div>

## -remarks



The <b>PortType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> structure is an <b>NDIS_SWITCH_PORT_TYPE</b> enumeration data type. 



For more information on the extensible switch ports, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-ports">Hyper-V Extensible Switch Ports</a>.






## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a>
 

 

