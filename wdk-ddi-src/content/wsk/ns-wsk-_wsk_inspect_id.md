---
UID: NS:wsk._WSK_INSPECT_ID
title: _WSK_INSPECT_ID (wsk.h)
description: The WSK_INSPECT_ID structure specifies an identifier for an incoming connection request on a listening socket.
old-location: netvista\wsk_inspect_id.htm
tech.root: netvista
ms.assetid: 54578dc5-a88f-4649-adbd-6a5e1e31e7b3
ms.date: 05/02/2018
keywords: ["WSK_INSPECT_ID structure"]
ms.keywords: "*PWSK_INSPECT_ID, PWSK_INSPECT_ID, PWSK_INSPECT_ID structure pointer [Network Drivers Starting with Windows Vista], WSK_INSPECT_ID, WSK_INSPECT_ID structure [Network Drivers Starting with Windows Vista], _WSK_INSPECT_ID, netvista.wsk_inspect_id, wsk/PWSK_INSPECT_ID, wsk/WSK_INSPECT_ID, wskref_7e500c2a-23ce-4193-b8a5-fbf416a9659d.xml"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.typenames: WSK_INSPECT_ID, *PWSK_INSPECT_ID
f1_keywords:
 - _WSK_INSPECT_ID
 - wsk/_WSK_INSPECT_ID
 - PWSK_INSPECT_ID
 - wsk/PWSK_INSPECT_ID
 - WSK_INSPECT_ID
 - wsk/WSK_INSPECT_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wsk.h
api_name:
 - WSK_INSPECT_ID
---

# _WSK_INSPECT_ID structure


## -description

The WSK_INSPECT_ID structure specifies an identifier for an incoming connection request on a
  listening socket.

## -struct-fields

### -field Key

A key that is assigned to the incoming connection request.

### -field SerialNumber

A serial number that is assigned to the incoming connection request.

## -remarks

The WSK subsystem passes a pointer to a WSK_INSPECT_ID structure to a WSK application's 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_inspect_event">WskInspectEvent</a> event callback function
    whenever an incoming connection request arrives on a listening socket that has conditional accept mode
    enabled. The contents of the WSK_INSPECT_ID structure uniquely identify the incoming connection
    request.

If the WSK application returns 
    <b>WskInspectPend</b> from a call to its 
    <i>WskInspectEvent</i> event callback function, the application must first copy the 
    <u>contents</u> of the WSK_INSPECT_ID structure that is provided by the WSK subsystem into its own
    WSK_INSPECT_ID structure. The WSK application then passes a pointer to its WSK_INSPECT_ID structure to
    the 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_inspect_complete">WskInspectComplete</a> function when it
    completes the inspection.

If the incoming connection request is dropped by the remote system while an inspect operation is
    pending, the WSK subsystem calls the WSK application's 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_abort_event">WskAbortEvent</a> event callback function with a
    pointer to a WSK_INSPECT_ID structure that identifies the dropped request. The WSK application uses the
    contents of this WSK_INSPECT_ID structure to determine which inspection of an incoming connection request
    should be terminated. The WSK application should compare the contents of the WSK_INSPECT_ID structures to
    check for a match. The actual values of the structure members are irrelevant.

A WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="/windows-hardware/drivers/network/so-conditional-accept">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="/windows-hardware/drivers/network/listening-for-and-accepting-incoming-connections">Listening for and
    Accepting Incoming Connections</a>.

## -see-also

<a href="/windows-hardware/drivers/network/so-conditional-accept">SO_CONDITIONAL_ACCEPT</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_abort_event">WskAbortEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_inspect_complete">WskInspectComplete</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_inspect_event">WskInspectEvent</a>