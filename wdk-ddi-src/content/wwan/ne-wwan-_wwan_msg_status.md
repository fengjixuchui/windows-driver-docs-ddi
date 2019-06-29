---
UID: NE:wwan._WWAN_MSG_STATUS
title: _WWAN_MSG_STATUS (wwan.h)
description: The WWAN_MSG_STATUS enumeration lists different SMS message statuses.
old-location: netvista\wwan_msg_status.htm
tech.root: netvista
ms.assetid: 60eb0494-fcc6-4546-a13a-b6d1dcf165e6
ms.date: 05/02/2018
ms.keywords: "*PWWAN_MSG_STATUS, PWWAN_MSG_STATUS, PWWAN_MSG_STATUS enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_MSG_STATUS, WWAN_MSG_STATUS enumeration [Network Drivers Starting with Windows Vista], WwanMsgStatusDraft, WwanMsgStatusMax, WwanMsgStatusNew, WwanMsgStatusOld, WwanMsgStatusSent, WwanRef_2cd2fe07-ee6c-4193-960e-434e31561f9e.xml, _WWAN_MSG_STATUS, netvista.wwan_msg_status, wwan/PWWAN_MSG_STATUS, wwan/WWAN_MSG_STATUS, wwan/WwanMsgStatusDraft, wwan/WwanMsgStatusMax, wwan/WwanMsgStatusNew, wwan/WwanMsgStatusOld, wwan/WwanMsgStatusSent"
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
- wwan.h
api_name:
- WWAN_MSG_STATUS
product:
- Windows
targetos: Windows
req.typenames: WWAN_MSG_STATUS, *PWWAN_MSG_STATUS
---

# _WWAN_MSG_STATUS enumeration


## -description


The WWAN_MSG_STATUS enumeration lists different SMS message statuses.


## -enum-fields




### -field WwanMsgStatusNew

The message is new or unread.


### -field WwanMsgStatusOld

The message is old and is read.


### -field WwanMsgStatusDraft

The message is unsent and stored in the device.


### -field WwanMsgStatusSent

The message has already been sent.


### -field WwanMsgStatusMax

The total number of supported SMS message statuses.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_sms_pdu_record">WWAN_SMS_PDU_RECORD</a>
 

 

