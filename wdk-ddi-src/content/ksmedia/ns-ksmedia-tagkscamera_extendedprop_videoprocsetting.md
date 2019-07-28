---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
title: tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING (ksmedia.h)
description: The KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode.
old-location: stream\kscamera_extendedprop_videoprocsetting.htm
tech.root: stream
ms.assetid: D4239E72-C57A-45BC-881C-08FF6263874E
ms.date: 04/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure [Streaming Media Devices], KSCAMERA_EXTENDEDPROP_WBPRESET_CANDLELIGHT, KSCAMERA_EXTENDEDPROP_WBPRESET_CLOUDY, KSCAMERA_EXTENDEDPROP_WBPRESET_DAYLIGHT, KSCAMERA_EXTENDEDPROP_WBPRESET_FLASH, KSCAMERA_EXTENDEDPROP_WBPRESET_FLUORESCENT, KSCAMERA_EXTENDEDPROP_WBPRESET_TUNGSTEN, KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET, KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE, PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, ksmedia/PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, stream.kscamera_extendedprop_videoprocsetting, tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
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
- Ksmedia.h
api_name:
- KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, *PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
---

# tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure


## -description


The <b>KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING</b> is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode.


## -struct-fields




### -field Mode

The video processing mode type. Currently, this member is used to control white balance. The possible values for <b>Mode</b> are the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE"></a><a id="kscamera_extendedprop_whitebalance_temperature"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE</b></dt>
</dl>
</td>
<td width="60%">
A picture temperature value is used to set white balance in degrees Kelvin.

</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET"></a><a id="kscamera_extendedprop_whitebalance_preset"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET</b></dt>
</dl>
</td>
<td width="60%">
The white balance setting is a preset value specified in <b>VideoProc</b>.

</td>
</tr>
</table>
 

This member is not used for <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-exposuremode">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-focusmode">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a>. In these cases it must be set to 0.


### -field Min

The minum range value for the setting in <b>VideoProc</b>.


### -field Max

The maximum range value for the setting in <b>VideoProc</b>.


### -field Step

The maximum range value for the setting in <b>VideoProc</b>.

The increment in value, when applicable, for the setting in <b>VideoProc</b> when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE.

-or-

The increment in value, when applicable, for the setting in <b>VideoProc</b> when setting exposure is set manually with KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL.


### -field VideoProc

Using the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-whitebalancemode">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a> property, when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET, the <b>VideoProc.Value.ul</b> value is one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_CLOUDY"></a><a id="kscamera_extendedprop_wbpreset_cloudy"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_WBPRESET_CLOUDY</b></dt>
</dl>
</td>
<td width="60%">
White balance preset for cloudy conditions.

</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_DAYLIGHT"></a><a id="kscamera_extendedprop_wbpreset_daylight"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_WBPRESET_DAYLIGHT</b></dt>
</dl>
</td>
<td width="60%">
White balance preset for cloudy daylight.

</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_FLASH"></a><a id="kscamera_extendedprop_wbpreset_flash"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_WBPRESET_FLASH</b></dt>
</dl>
</td>
<td width="60%">
White balance preset to compensate for flash lighting.

</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_FLUORESCENT"></a><a id="kscamera_extendedprop_wbpreset_fluorescent"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_WBPRESET_FLUORESCENT</b></dt>
</dl>
</td>
<td width="60%">
White balance preset to compensate for fluorescent lighting.

</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_TUNGSTEN"></a><a id="kscamera_extendedprop_wbpreset_tungsten"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_WBPRESET_TUNGSTEN</b></dt>
</dl>
</td>
<td width="60%">
White balance preset to compensate for tungsten emitted lighting.

</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_CANDLELIGHT"></a><a id="kscamera_extendedprop_wbpreset_candlelight"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_WBPRESET_CANDLELIGHT</b></dt>
</dl>
</td>
<td width="60%">
White balance preset to compensate for candlelight lighting.

</td>
</tr>
</table>
 

Using the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-whitebalancemode">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a> property, when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE, the <b>VideoProc.Value.ul</b> value is a temperature value in degrees Kelvin.

Using the  <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-exposuremode">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a> property, when used for manually setting exposure, KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL, the <b>VideoProc.Value.ul</b> value is a the exposure time in 100 nanosecond units.

Using the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-focusmode">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a> property, this member contains the focal length value for manual focus mode,  KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL.


### -field Reserved

Reserved.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-exposuremode">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-focusmode">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-whitebalancemode">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a>
 

 

