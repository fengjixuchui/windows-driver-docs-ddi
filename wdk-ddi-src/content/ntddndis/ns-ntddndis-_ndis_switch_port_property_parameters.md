---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_PARAMETERS
title: _NDIS_SWITCH_PORT_PROPERTY_PARAMETERS (ntddndis.h)
description: The NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure specifies the parameters for a policy property of a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_property_parameters.htm
tech.root: netvista
ms.assetid: 656acfd4-6f34-41aa-862e-134a2b95dcab
ms.date: 05/02/2018
keywords: ["_NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure"]
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_PARAMETERS, NDIS_SWITCH_PORT_PROPERTY_PARAMETERS, NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_PARAMETERS, PNDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_PARAMETERS, netvista.ndis_switch_port_property_parameters, ntddndis/NDIS_SWITCH_PORT_PROPERTY_PARAMETERS, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_PARAMETERS"
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_PROPERTY_PARAMETERS"
 - "NDIS_SWITCH_PORT_PROPERTY_PARAMETERS"
req.header: ntddndis.h
req.include-header: Ndis.h, Fwpsk.h
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
- NDIS_SWITCH_PORT_PROPERTY_PARAMETERS
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PROPERTY_PARAMETERS, *PNDIS_SWITCH_PORT_PROPERTY_PARAMETERS
---

# _NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure


## -description


The <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure specifies the parameters for a policy property of a Hyper-V extensible switch port. 


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:





#### NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field PortId

 An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port to which the property is assigned.


### -field PropertyType

 An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_property_type">NDIS_SWITCH_PORT_PROPERTY_TYPE</a> enumeration value that specifies the type of port property that is contained within the property buffer.


### -field PropertyId

A GUID value that identifies the property for the extensible switch port.

For more information, see the Remarks section.

<div class="alert"><b>Note</b>  The extensible switch extension must ignore this member unless the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeCustom</b>.</div>
<div> </div>

### -field PropertyVersion

An NDIS_SWITCH_OBJECT_VERSION value that identifies the version of the property for the extensible switch port.




### -field SerializationVersion

An NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION value that identifies the format version of the serialized port property data. This data is serialized for access by the extension from the Managed Object Format (MOF) file that defined the property.

<div class="alert"><b>Note</b>  For Windows Server 2012, the <b>SerializationVersion</b> member must be set to NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION_1.</div>
<div> </div>

### -field PropertyInstanceId

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that identifies the instance of the  property for the extensible switch port.




### -field PropertyBufferLength

A ULONG value that specifies the size, in bytes, of the property buffer.


### -field PropertyBufferOffset

A ULONG value that specifies the offset, in bytes, to the property buffer that follows the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure up to the beginning of the property buffer. 


### -field Reserved

Reserved for future use.


## -remarks



The <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure is used in the following OID set requests:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-add">OID_SWITCH_PORT_PROPERTY_ADD</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-update">OID_SWITCH_PORT_PROPERTY_UPDATE</a>


</li>
</ul>
The property buffer contains a structure that is associated with the <b>PropertyType</b> member. The property buffer follows the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure in the information buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

The extensible switch extension must follow these guidelines when it processes an <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure:

<ul>
<li>
If the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeSecurity</b>, the property buffer is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_security">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a> structure.

</li>
<li>
If the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeVlan</b>, the property buffer is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_vlan">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure.

</li>
<li>
If the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeProfile</b>, the property buffer is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_profile">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a> structure.

</li>
<li>
If the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeCustom</b>, the <b>PropertyId</b> member must be set to the GUID value the independent software vendor (ISV) created for the custom port property. The property buffer is formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_custom">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a> structure that contains the parameters for the custom port property as defined by the ISV.

</li>
</ul>
Extensible switch extensions can access the custom port property inside an <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-property-parameters-get-property">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY</a> macro.

For more information about extensible switch policies, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-policies">Hyper-V Extensible Switch Policies</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_custom">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-property-parameters-get-property">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_profile">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_security">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_property_type">NDIS_SWITCH_PORT_PROPERTY_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_vlan">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-add">OID_SWITCH_PORT_PROPERTY_ADD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-update">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
 

 

