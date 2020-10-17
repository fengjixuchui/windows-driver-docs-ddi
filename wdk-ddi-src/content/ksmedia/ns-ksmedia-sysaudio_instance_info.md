---
UID: NS:ksmedia.__unnamed_struct_59
title: SYSAUDIO_INSTANCE_INFO (ksmedia.h)
description: The SYSAUDIO_INSTANCE_INFO structure specifies which virtual audio device to open and includes flags for configuring that device.
old-location: audio\sysaudio_instance_info.htm
tech.root: audio
ms.assetid: 3468b29d-e62c-46b4-b95e-06df846ebd81
ms.date: 04/30/2019
keywords: ["SYSAUDIO_INSTANCE_INFO structure"]
ms.keywords: "*PSYSAUDIO_INSTANCE_INFO, PSYSAUDIO_INSTANCE_INFO, PSYSAUDIO_INSTANCE_INFO structure pointer [Audio Devices], SYSAUDIO_INSTANCE_INFO, SYSAUDIO_INSTANCE_INFO structure [Audio Devices], aud-prop_dd4269d6-0f6e-476a-a4d3-ea71f3b9a96a.xml, audio.sysaudio_instance_info, ksmedia/PSYSAUDIO_INSTANCE_INFO, ksmedia/SYSAUDIO_INSTANCE_INFO"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
req.typenames: SYSAUDIO_INSTANCE_INFO, *PSYSAUDIO_INSTANCE_INFO
f1_keywords:
 - PSYSAUDIO_INSTANCE_INFO
 - ksmedia/PSYSAUDIO_INSTANCE_INFO
 - SYSAUDIO_INSTANCE_INFO
 - ksmedia/SYSAUDIO_INSTANCE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - SYSAUDIO_INSTANCE_INFO
---

# SYSAUDIO_INSTANCE_INFO structure


## -description

The SYSAUDIO_INSTANCE_INFO structure specifies which virtual audio device to open and includes flags for configuring that device.

## -struct-fields

### -field Property

Specifies the property. This parameter is a structure of type <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.

### -field Flags

Flags specifying how to configure the virtual audio device. Currently, the only flag bit defined for this parameter is SYSAUDIO_FLAGS_DONT_COMBINE_PINS. If set, this flag bit instructs SysAudio not to combine rendering pins. For more information, see the following Remarks section.

### -field DeviceNumber

Specifies the device ID. This member identifies the virtual audio device that is to be opened by the property request. If SysAudio enumerates <i>N</i> virtual audio devices (see <a href="/windows-hardware/drivers/audio/ksproperty-sysaudio-device-count">KSPROPERTY_SYSAUDIO_DEVICE_COUNT</a>), the valid device IDs range from 0 to <i>N</i>-1.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/audio/ksproperty-sysaudio-instance-info">KSPROPERTY_SYSAUDIO_INSTANCE_INFO</a> property.

By default, a virtual audio device combines its wave-rendering pins. The SYSAUDIO_FLAGS_DONT_COMBINE_PINS flag overrides this default.

When pins are combined, the virtual audio device exposes a single pin factory that combines hardware-accelerated rendering pins on the audio device with software-emulated mixer pins on the <a href="/windows-hardware/drivers/audio/kernel-mode-wdm-audio-components">KMixer system driver</a>. If the pins are not combined, then hardware-accelerated pins and software-emulated pins are exposed through separate pin factories. In order to correctly report the number of hardware-accelerated pins to application programs, DirectSound requires that the pins not be combined.

This property is similar to <a href="/windows-hardware/drivers/audio/ksproperty-sysaudio-device-instance">KSPROPERTY_SYSAUDIO_DEVICE_INSTANCE</a>, with the exception that it includes flags specifying how to configure the virtual audio device.

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/audio/ksproperty-sysaudio-device-count">KSPROPERTY_SYSAUDIO_DEVICE_COUNT</a>



<a href="/windows-hardware/drivers/audio/ksproperty-sysaudio-device-instance">KSPROPERTY_SYSAUDIO_DEVICE_INSTANCE</a>



<a href="/windows-hardware/drivers/audio/ksproperty-sysaudio-instance-info">KSPROPERTY_SYSAUDIO_INSTANCE_INFO</a>