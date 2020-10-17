---
UID: NS:bthddi._BRB_L2CA_UPDATE_CHANNEL
title: _BRB_L2CA_UPDATE_CHANNEL (bthddi.h)
description: The _BRB_L2CA_UPDATE_CHANNEL structure describes an update to the link characteristics of an open L2CAP channel to a remote device or to ascertain when certain channel attributes have changed.
old-location: bltooth\_brb_l2ca_update_channel.htm
tech.root: bltooth
ms.assetid: 0186dc75-6d37-4adb-8337-6daa634bd936
ms.date: 04/27/2018
keywords: ["BRB_L2CA_UPDATE_CHANNEL structure"]
ms.keywords: "_BRB_L2CA_UPDATE_CHANNEL, _BRB_L2CA_UPDATE_CHANNEL structure [Bluetooth Devices], bltooth._brb_l2ca_update_channel, bth_structs_7ee8d85e-5cf3-4820-a325-6abe0777b22a.xml, bthddi/_BRB_L2CA_UPDATE_CHANNEL"
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
 - _BRB_L2CA_UPDATE_CHANNEL
 - bthddi/_BRB_L2CA_UPDATE_CHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - _BRB_L2CA_UPDATE_CHANNEL
---

# _BRB_L2CA_UPDATE_CHANNEL structure


## -description

The _BRB_L2CA_UPDATE_CHANNEL structure describes an update to the link characteristics of an open
  L2CAP channel to a remote device or to ascertain when certain channel attributes have changed.

## -struct-fields

### -field Hdr

A 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.

### -field BtAddress

The Bluetooth address of the remote device.

### -field ChannelHandle

The L2CAP channel handle that was returned by Bluetooth driver stack in response to an earlier 
     <a href="/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a> or 
     <a href="/previous-versions/ff536616(v=vs.85)">
     BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request.

### -field NewChannelFlags

      A combination of flag values that specify the updated requirements for the channel. This member
      should be set to CF_ROLE_EITHER.

### -field FailedChannelFlags

The flag or flags in the 
     <b>NewChannelFlags</b> member that the Bluetooth driver stack was not able to honor. This member contains
     information only if the BRB call failed.

## -remarks

To retrieve the current settings of a L2CAP channel, profile drivers should 
    <a href="/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="/previous-versions/ff536620(v=vs.85)">BRB_L2CA_UPDATE_CHANNEL</a> request.

The profile driver can then determine when certain channel attributes have changed. Additionally, if
    the CF_LINK_PASSIVE_MODE flag is not set, the BRB will attempt to change the current channel settings to
    the remote device.

The primary use of <b>BRB_L2CA_UPDATE_CHANNEL</b> is to determine when authentication or encryption has been
    enabled for a connection.

In some cases, L2CAP connections can be established without the profile driver specifying that
    authentication is required, but authentication will happen automatically due to choices made by the user.
    In this case, a period of time passes between when the connection is established and when authentication
    and encryption begin working. Calls to <b>BRB_L2CA_UPDATE_CHANNEL</b> are blocked until authentication and
    encryption are complete.

By building and sending a <b>BRB_L2CA_UPDATE_CHANNEL</b> request, profile drivers can avoid using the
    connection prior to authentication.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a>



<a href="/previous-versions/ff536616(v=vs.85)">
   BRB_L2CA_OPEN_CHANNEL_RESPONSE</a>



<a href="/previous-versions/ff536620(v=vs.85)">BRB_L2CA_UPDATE_CHANNEL</a>