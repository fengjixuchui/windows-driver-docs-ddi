---
UID: NF:ks.KsInitializeDeviceProfile
title: KsInitializeDeviceProfile function (ks.h)
description: The KsInitializeDeviceProfile API must be called by all miniport drivers to initialize the profile store and publish the device profiles.
old-location: stream\ksinitializedeviceprofile.htm
tech.root: stream
ms.assetid: E6AD21CE-C218-439F-A8F7-8E1AAF307A57
ms.date: 04/23/2018
keywords: ["KsInitializeDeviceProfile function"]
ms.keywords: KsInitializeDeviceProfile, KsInitializeDeviceProfile function [Streaming Media Devices], ks/KsInitializeDeviceProfile, stream.ksinitializedeviceprofile
req.header: ks.h
req.include-header: Ksmedia.h
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsInitializeDeviceProfile
 - ks/KsInitializeDeviceProfile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ks.lib
 - ks.dll
api_name:
 - KsInitializeDeviceProfile
---

# KsInitializeDeviceProfile function


## -description

The <b>KsInitializeDeviceProfile</b> API must be called by all miniport drivers to initialize the profile store and publish the device profiles.

## -parameters

### -param FilterFactory 

[in]
This is the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> that was created by the camera driver to uniquely identify the camera’s filter factory.

## -returns

If the provided <b>KSFILTERFACTORY</b> does not contain a device interface associated with the <b>KSCATEGORY_VIDEO_CAMERA</b>, this API call will fail with <b>STATUS_INVALID_PARAMETER</b>.

## -remarks

It is required that the <b>ReferenceGuid</b> field of the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> structure contained with the <b>KSFILTERFACTORY</b> be set with a unique GUID for this filter type.  And the <b>Flags</b> field of the <b>KSFILTER_DESCRIPTOR</b> has the <b>KSFILTER_FLAG_PRIORITIZE_REFERENCEGUID</b> flag set.

To delete all profiles from the profile store associated with the device interface for this <b>KSFILTERFACTORY</b>, the driver may call <b>KsInitializeDeviceProfile</b> followed immediately by <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspersistdeviceprofile">KsPersistDeviceProfile</a>.  This would result in an empty profile information, which would remove the profile information from the profile store.