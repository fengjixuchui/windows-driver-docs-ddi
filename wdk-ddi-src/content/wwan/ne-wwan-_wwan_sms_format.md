---
UID: NE:wwan._WWAN_SMS_FORMAT
title: _WWAN_SMS_FORMAT (wwan.h)
description: The WWAN_SMS_FORMAT enumeration lists different Short Message Service (SMS) formats.
old-location: netvista\wwan_sms_format.htm
tech.root: netvista
ms.assetid: fb583ded-8292-4486-8e85-3d3039611d14
ms.date: 05/02/2018
keywords: ["_WWAN_SMS_FORMAT enumeration"]
ms.keywords: "*PWWAN_SMS_FORMAT, PWWAN_SMS_FORMAT, PWWAN_SMS_FORMAT enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_FORMAT, WWAN_SMS_FORMAT enumeration [Network Drivers Starting with Windows Vista], WwanRef_594a5286-7ead-4877-939c-ed4bf2eb99e0.xml, WwanSmsFormatCdma, WwanSmsFormatMax, WwanSmsFormatPdu, WwanSmsFormatReserved0, WwanSmsFormatReserved1, WwanSmsFormatReserved2, _WWAN_SMS_FORMAT, netvista.wwan_sms_format, wwan/PWWAN_SMS_FORMAT, wwan/WWAN_SMS_FORMAT, wwan/WwanSmsFormatCdma, wwan/WwanSmsFormatMax, wwan/WwanSmsFormatPdu, wwan/WwanSmsFormatReserved0, wwan/WwanSmsFormatReserved1, wwan/WwanSmsFormatReserved2"
f1_keywords:
 - "wwan/WWAN_SMS_FORMAT"
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
- WWAN_SMS_FORMAT
product:
- Windows
targetos: Windows
req.typenames: WWAN_SMS_FORMAT, *PWWAN_SMS_FORMAT
---

# _WWAN_SMS_FORMAT enumeration


## -description


The WWAN_SMS_FORMAT enumeration lists different Short Message Service (SMS) formats.


## -enum-fields




### -field WwanSmsFormatPdu

SMS messages are in PDU format. For GSM-based devices, messages are hexadecimal strings that
     represent messages in PDU format as defined in the 3GPP TS 27.005 and 3GPP TS 23.040 specifications. For
     CDMA-based devices messages are byte arrays that represent messages as defined in section 3.4.2.1 SMS
     Point-to-Point Message in 3GPP2 specification C.S0015-A "Short Message Service (SMS) for Wideband Spread
     Spectrum Systems".


### -field WwanSmsFormatReserved0

This value is reserved for future use. Do not use.


### -field WwanSmsFormatReserved1

This value is reserved for future use. Do not use.


### -field WwanSmsFormatReserved2

This value is reserved for future use. Do not use.


### -field WwanSmsFormatCdma

The message is in text format. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a> and 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send_cdma">WWAN_SMS_SEND_CDMA</a>. This value applies
     only to CDMA-based devices.


### -field WwanSmsFormatMax

This value is reserved. Do not use.


## -remarks



CDMA-based devices support only 
    <b>WwanSmsFormatCdma</b>. The 
    <b>WwanSmsFormatCdma</b> format is not applicable for GSM-based devices.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_sms_configuration">WWAN_SET_SMS_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_configuration">WWAN_SMS_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_read">WWAN_SMS_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send">WWAN_SMS_SEND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send_cdma">WWAN_SMS_SEND_CDMA</a>
 

 

