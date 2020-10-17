---
UID: NS:portcls._PCPROPERTY_REQUEST
title: _PCPROPERTY_REQUEST (portcls.h)
description: The PCPROPERTY_REQUEST structure specifies a property request.
old-location: audio\pcproperty_request.htm
tech.root: audio
ms.assetid: 3683735d-ce00-4615-9782-dee9f4753cc7
ms.date: 05/08/2018
keywords: ["PCPROPERTY_REQUEST structure"]
ms.keywords: "*PPCPROPERTY_REQUEST, PCPROPERTY_REQUEST, PCPROPERTY_REQUEST structure [Audio Devices], PPCPROPERTY_REQUEST, PPCPROPERTY_REQUEST structure pointer [Audio Devices], _PCPROPERTY_REQUEST, audio.pcproperty_request, audpc-struct_f153c6fb-8b21-4a81-ab9b-d7b7fef9f9db.xml, portcls/PCPROPERTY_REQUEST, portcls/PPCPROPERTY_REQUEST"
req.header: portcls.h
req.include-header: Portcls.h
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
targetos: Windows
req.typenames: PCPROPERTY_REQUEST, *PPCPROPERTY_REQUEST
f1_keywords:
 - _PCPROPERTY_REQUEST
 - portcls/_PCPROPERTY_REQUEST
 - PPCPROPERTY_REQUEST
 - portcls/PPCPROPERTY_REQUEST
 - PCPROPERTY_REQUEST
 - portcls/PCPROPERTY_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - portcls.h
api_name:
 - PCPROPERTY_REQUEST
---

# _PCPROPERTY_REQUEST structure


## -description

The <b>PCPROPERTY_REQUEST</b> structure specifies a property request.

## -struct-fields

### -field MajorTarget

<a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> pointer to the main miniport object. This member contains the <i>UnknownMiniport</i> parameter value that the adapter driver previously passed to the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a> method.

### -field MinorTarget

<a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> pointer to a stream object that is associated with the <b>MajorTarget</b> miniport object. If the target for the property request is a pin instance, this member contains the stream-object pointer that the IMiniport <i>Xxx</i>::NewStream method previously output to the port driver (for example, the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a> method's <i>Stream</i> parameter). Otherwise (if the target for the property request is a filter instance), this member is <b>NULL</b>.

### -field Node

Specifies a node ID. This member identifies the target node for the request. If the target is not a node, this member is set to ULONG(-1).

### -field PropertyItem

Pointer to the property item, which is a structure of type <a href="/windows-hardware/drivers/ddi/portcls/ns-portcls-pcproperty_item">PCPROPERTY_ITEM</a>.

### -field Verb

Specifies the type of property request. <b>Verb</b> is set to the bitwise OR of one or more of the following flag bits from header file ks.h:

<ul>
<li>
KSPROPERTY_TYPE_GET

</li>
<li>
KSPROPERTY_TYPE_SET

</li>
<li>
KSPROPERTY_TYPE_SETSUPPORT

</li>
<li>
KSPROPERTY_TYPE_BASICSUPPORT

</li>
<li>
KSPROPERTY_TYPE_RELATIONS

</li>
<li>
KSPROPERTY_TYPE_SERIALIZESET

</li>
<li>
KSPROPERTY_TYPE_UNSERIALIZESET

</li>
<li>
KSPROPERTY_TYPE_SERIALIZERAW

</li>
<li>
KSPROPERTY_TYPE_UNSERIALIZERAW

</li>
<li>
KSPROPERTY_TYPE_SERIALIZESIZE

</li>
<li>
KSPROPERTY_TYPE_DEFAULTVALUES

</li>
<li>
KSPROPERTY_TYPE_TOPOLOGY

</li>
</ul>
These flags are described in <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.

### -field InstanceSize

Specifies the size in bytes of the property-instance buffer.

### -field Instance

Pointer to the property-instance buffer

### -field ValueSize

Specifies the size in bytes of the property-value buffer.

### -field Value

Pointer to the property-value buffer

### -field Irp

Pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> containing the client's original property request

## -remarks

This is the structure that the port driver passes to the miniport driver's property-handler routine. The <a href="/windows-hardware/drivers/ddi/portcls/ns-portcls-pcproperty_item">PCPROPERTY_ITEM</a> structure contains a function pointer to a property handler that takes a <b>PCPROPERTY_REQUEST</b> pointer as its only call parameter. The port driver allocates a <b>PCPROPERTY_REQUEST</b> structure, extracts the relevant information from the original property request (which the <b>Irp</b> member points to), and loads the information into this structure before calling the handler.

In WDM audio, the target of a property request can be either a filter instance or a pin instance. The target can also include a node ID.

In the client's original property request, the property-instance data always begins with a <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> or <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksnodeproperty">KSNODEPROPERTY</a> structure, but can include additional information. The port driver adjusts the <b>PCPROPERTY_REQUEST</b> structure's <b>Instance</b> member to point to this additional information, if it exists. For details, see <a href="/windows-hardware/drivers/audio/audio-property-handlers">Audio Property Handlers</a>.

The <b>MajorTarget</b> and <b>MinorTarget</b> members are <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> pointers to the main miniport object and an associated stream object, respectively. The property handler can query these objects for their miniport and stream interfaces. If the target for the property request is a filter instance, <b>MajorTarget</b> points to the miniport object for that filter instance, and <b>MinorTarget</b> is <b>NULL</b>. If the target is a pin instance, <b>MinorTarget</b> points to the stream object for that pin, and <b>MajorTarget</b> points to the miniport object for the filter that the pin is attached to.

For example, if the target for the property request is a pin instance on a WaveCyclic filter:

<ul>
<li>
The handler can call <a href="/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)">QueryInterface</a> on the <b>MajorTarget</b> object's <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface to obtain a reference to the object's <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavecyclic">IMiniportWaveCyclic</a> interface.

</li>
<li>
The handler can call <a href="/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)">QueryInterface</a> on the <b>MinorTarget</b> object's <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface to obtain a reference to the object's <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavecyclicstream">IMiniportWaveCyclicStream</a> interface.

</li>
</ul>
For background information about audio properties, see <a href="/windows-hardware/drivers/audio/audio-endpoints--properties-and-events">Audio Endpoints, Properties and Events</a>. For a list of the available audio-specific properties, see <a href="/windows-hardware/drivers/audio/audio-drivers-property-sets">Audio Drivers Property Sets</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksnodeproperty">KSNODEPROPERTY</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksnodeproperty_audio_channel">KSNODEPROPERTY_AUDIO_CHANNEL</a>



<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/ddi/portcls/ns-portcls-pcproperty_item">PCPROPERTY_ITEM</a>