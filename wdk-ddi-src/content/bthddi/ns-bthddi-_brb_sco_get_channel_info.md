---
UID: NS:bthddi._BRB_SCO_GET_CHANNEL_INFO
title: _BRB_SCO_GET_CHANNEL_INFO (bthddi.h)
description: The _BRB_SCO_GET_CHANNEL_INFO structure describes the settings and statistics of a SCO channel.
old-location: bltooth\_brb_sco_get_channel_info.htm
tech.root: bltooth
ms.assetid: 1a7eb79c-5a3e-4977-ba1f-682bbebb0494
ms.date: 04/27/2018
keywords: ["BRB_SCO_GET_CHANNEL_INFO structure"]
ms.keywords: "_BRB_SCO_GET_CHANNEL_INFO, _BRB_SCO_GET_CHANNEL_INFO structure [Bluetooth Devices], bltooth._brb_sco_get_channel_info, bth_structs_cf7da00a-9c32-432d-a8a2-7bac58fe17e0.xml, bthddi/_BRB_SCO_GET_CHANNEL_INFO"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.typenames: 
f1_keywords:
 - _BRB_SCO_GET_CHANNEL_INFO
 - bthddi/_BRB_SCO_GET_CHANNEL_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - _BRB_SCO_GET_CHANNEL_INFO
---

# _BRB_SCO_GET_CHANNEL_INFO structure


## -description

The _BRB_SCO_GET_CHANNEL_INFO structure describes the settings and statistics of a SCO
  channel.

## -struct-fields

### -field Hdr

A 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.

### -field BtAddress

The Bluetooth address of the remote device.

### -field ChannelHandle

The handle to the SCO channel to query.

### -field InfoFlags

A flag that determines if baseband information is available for the SCO channel. The following
     flag is defined:
     

<table>
<tr>
<th>
       Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SCO_INFO_BASEBAND_AVAILABLE

</td>
<td>
If set, baseband settings are available for the SCO channel.

</td>
</tr>
</table>

### -field TransmitBandwidth

The transmission bandwidth of the channel, in bytes per second.

### -field ReceiveBandwidth

The reception bandwidth of the channel, in bytes per second.

### -field MaxLatency

A value that represents the upper limit of the sum of the synchronous interval and the size of the
     SCO window, in milliseconds. Possible values are listed in the following table.
     

<table>
<tr>
<th>
       Values</th>
<th>Description</th>
</tr>
<tr>
<td>
0x0000 to 0x0003

</td>
<td>
Reserved for future use.

</td>
</tr>
<tr>
<td>
0x0004 to 0xFFFE

</td>
<td>
The range of latency values for the channel.

</td>
</tr>
<tr>
<td>
0xFFFF

</td>
<td>
The channel doesn't have a preferred 
        <b>MaxLatency</b> setting.

</td>
</tr>
</table>

### -field PacketType

A flag or combination of flags that indicates the type of data packets that the SCO channel
     supports. These SCO packet types are defined by the Bluetooth SIG. See the Bluetooth specification for
     more information about these flags. Possible values include:
     


<dl>
<dt>SCO_HV1
     </dt>
<dt>SCO_HV2
     </dt>
<dt>SCO_HV3
     </dt>
<dt>SCO_EV3
     </dt>
<dt>SCO_EV4
     </dt>
<dt>SCO_EV5</dt>
</dl>

### -field ContentFormat

The audio voice setting for the channel. Use the following definitions to decode this member:
     


<dl>
<dt>SCO_VS_AIR_CODING_DATA
     </dt>
<dt>SCO_VS_AIR_CODING_FORMAT_ALAW
     </dt>
<dt>SCO_VS_AIR_CODING_FORMAT_CVSD
     </dt>
<dt>SCO_VS_AIR_CODING_FORMAT_MASK
     </dt>
<dt>SCO_VS_AIR_CODING_FORMAT_MULAW
     </dt>
<dt>SCO_VS_IN_CODING_ALAW
     </dt>
<dt>SCO_VS_IN_CODING_LINEAR
     </dt>
<dt>SCO_VS_IN_CODING_MASK
     </dt>
<dt>SCO_VS_IN_CODING_MULAW
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_1C
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_2C
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_MASK
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_SM
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_US
     </dt>
<dt>SCO_VS_IN_SAMPLE_SIZE_8BIT
     </dt>
<dt>SCO_VS_IN_SAMPLE_SIZE_16BIT
     </dt>
<dt>SCO_VS_IN_SAMPLE_SIZE_MASK
     </dt>
<dt>SCO_VS_PCM_BIT_POS_MASK
     </dt>
<dt>SCO_VS_SETTING_DEFAULT</dt>
</dl>

### -field Reserved

Reserved for future use. Do not use.

### -field RetransmissionEffort

A 
     <a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_sco_retransmission_effort">SCO_RETRANSMISSION_EFFORT</a> value that
     determines the channel's retransmission policies.

### -field ChannelFlags

Flags that specify how the channel was opened. Valid flag values are listed in the following
     table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SCO_CF_LINK_AUTHENTICATED

</td>
<td>
The link must be authenticated.

</td>
</tr>
<tr>
<td>
SCO_CF_LINK_ENCRYPTED

</td>
<td>
The link must be encrypted. Setting this flag also sets the SCO_CF_LINK_AUTHENTICATED flag.

</td>
</tr>
<tr>
<td>
SCO_CF_LINK_SUPPRESS_PIN

</td>
<td>
The profile driver indicates its preference that users not be prompted for a PIN.

</td>
</tr>
</table>

### -field HciConnectionHandle

The host controller interface's connection handle for the SCO connection.

### -field LinkType

The 
     <a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_sco_link_type">SCO_LINK_TYPE</a> that is associated with the host
     controller interface.

### -field BasebandInfo

A 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_baseband_channel_info">BASEBAND_CHANNEL_INFO</a> structure that
     contains information for the SCO connection. This information is only available for links established
     using the 1.2 Bluetooth Synchronous Commands.

## -remarks

To get the settings and statistics of a SCO channel, profile drivers should 
    <a href="/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_get_channel_info">
    BRB_SCO_GET_CHANNEL_INFO</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_baseband_channel_info">BASEBAND_CHANNEL_INFO</a>



<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_get_channel_info">BRB_SCO_GET_CHANNEL_INFO</a>



<a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_sco_link_type">SCO_LINK_TYPE</a>



<a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_sco_retransmission_effort">SCO_RETRANSMISSION_EFFORT</a>