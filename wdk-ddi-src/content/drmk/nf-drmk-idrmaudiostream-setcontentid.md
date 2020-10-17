---
UID: NF:drmk.IDrmAudioStream.SetContentId
title: IDrmAudioStream::SetContentId (drmk.h)
description: The SetContentId method sets the DRM content ID and its assigned DRM content rights on a KS audio stream.
old-location: audio\idrmaudiostream_setcontentid.htm
tech.root: audio
ms.assetid: 0e9d13e8-c351-4730-8f00-6c149f824af0
ms.date: 05/08/2018
keywords: ["IDrmAudioStream::SetContentId"]
ms.keywords: IDrmAudioStream interface [Audio Devices],SetContentId method, IDrmAudioStream.SetContentId, IDrmAudioStream::SetContentId, SetContentId, SetContentId method [Audio Devices], SetContentId method [Audio Devices],IDrmAudioStream interface, audio.idrmaudiostream_setcontentid, audmp-routines_66106418-566d-4203-a6d6-faae74a6db13.xml, drmk/IDrmAudioStream::SetContentId
req.header: drmk.h
req.include-header: Drmk.h
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
 - IDrmAudioStream::SetContentId
 - drmk/IDrmAudioStream::SetContentId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - drmk.h
api_name:
 - IDrmAudioStream.SetContentId
---

# IDrmAudioStream::SetContentId


## -description

The <code>SetContentId</code> method sets the DRM content ID and its assigned DRM content rights on a KS audio stream.

## -parameters

### -param ContentId 

[in]
Specifies the DRM content ID. This parameter is an identifier that the DRM system generates at run time to identify DRM-protected content in this stream.

### -param DrmRights 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/drmk/ns-drmk-tagdrmrights">DRMRIGHTS</a> structure specifying the rights granted by the content provider to the user for playing and copying DRM-protected content in this stream.

## -returns

<code>SetContentId</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. If the filter cannot enforce the specified content rights, the method returns STATUS_NOT_IMPLEMENTED.

## -remarks

The DRM system can call the <code>SetContentId</code> method at any time during the lifetime of a KS audio stream.

A KS audio filter completes the execution of a call to the <code>SetContentId</code> method synchronously. If the function returns STATUS_SUCCESS, this indicates that all the downstream KS audio nodes (see <a href="/windows-hardware/drivers/audio/audio-topology-nodes">Audio Topology Nodes</a>) of a KS audio stream have also been successfully configured with the specified DRM content ID and DRM content rights. (The term <i>downstream node</i> refers to either a direct or an indirect sink for an audio stream.)

If the KS audio filter cannot enforce the specified DRM content rights, the <code>SetContentId</code> method returns the error code STATUS_NOT_IMPLEMENTED. In this case, the KS audio stream's previously set DRM content ID and DRM content rights remain set on the stream.

For more information about using this method, see <a href="/windows-hardware/drivers/audio/digital-rights-management">Digital Rights Management</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/drmk/ns-drmk-tagdrmrights">DRMRIGHTS</a>



<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmcreatecontentmixed">DrmCreateContentMixed</a>



<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmdestroycontent">DrmDestroyContent</a>



<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttofileobject">DrmForwardContentToFileObject</a>



<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>



<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmgetcontentrights">DrmGetContentRights</a>



<a href="/windows-hardware/drivers/ddi/drmk/nn-drmk-idrmaudiostream">IDrmAudioStream</a>