---
UID: NF:portcls.IMiniportTopology.Init
title: IMiniportTopology::Init (portcls.h)
description: The Init method initializes the topology miniport object.
old-location: audio\iminiporttopology_init.htm
tech.root: audio
ms.assetid: c8c53792-8c1a-466a-9f0f-8c12f9e7b50e
ms.date: 05/08/2018
keywords: ["IMiniportTopology::Init"]
ms.keywords: IMiniportTopology interface [Audio Devices],Init method, IMiniportTopology.Init, IMiniportTopology::Init, Init, Init method [Audio Devices], Init method [Audio Devices],IMiniportTopology interface, audio.iminiporttopology_init, audmp-routines_c87a11c3-aed3-4516-b3bf-5d32423fa293.xml, portcls/IMiniportTopology::Init
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportTopology::Init
 - portcls/IMiniportTopology::Init
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportTopology.Init
---

# IMiniportTopology::Init


## -description

The <code>Init</code> method initializes the topology miniport object.

## -parameters

### -param UnknownAdapter 

[in]
Pointer to the <b>IUnknown</b> interface of the adapter object whose miniport object is being initialized. This parameter is optional and can be specified as <b>NULL</b>. For more information, see the following Remarks section.

### -param ResourceList 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a> interface of the resource list object that is to be supplied to the miniport driver during initialization. After passing this reference to the miniport driver, the port driver is free to examine the contents of the resource list but will not modify the contents of this list. For more information, see the following Remarks section.

### -param Port 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iporttopology">IPortTopology</a> object that is bound to this miniport object. The caller specifies a valid, non-<b>NULL</b> pointer value for this parameter.

## -returns

<code>Init</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The <i>UnknownAdapter</i> and <i>ResourceList</i> parameters are the same pointer values that the adapter driver earlier passed as parameters to the <b>IPortTopology</b> object's <b>Init</b> method (see <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a>).

The <i>UnknownAdapter</i>, <i>ResourceList</i>, and <i>Port</i> parameters follow the <a href="/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiporttopology">IMiniportTopology</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iporttopology">IPortTopology</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>