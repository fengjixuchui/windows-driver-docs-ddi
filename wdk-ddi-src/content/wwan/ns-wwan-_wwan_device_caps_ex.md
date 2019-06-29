---
UID: NS:wwan._WWAN_DEVICE_CAPS_EX
title: _WWAN_DEVICE_CAPS_EX (wwan.h)
description: The WWAN_DEVICE_CAPS_EX structure represents the capabilities of the mobile broadband device.
old-location: netvista\wwan_device_caps_ex.htm
tech.root: netvista
ms.assetid: 91F62BFF-C26A-422A-B138-1E8D9A5146B3
ms.date: 05/02/2018
ms.keywords: "*PWWAN_DEVICE_CAPS_EX, PWWAN_DEVICE_CAPS_EX, PWWAN_DEVICE_CAPS_EX structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_CAPS_EX, WWAN_DEVICE_CAPS_EX structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_CAPS_EX, netvista.wwan_device_caps_ex, wwan/PWWAN_DEVICE_CAPS_EX, wwan/WWAN_DEVICE_CAPS_EX"
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
- WWAN_DEVICE_CAPS_EX
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_CAPS_EX, *PWWAN_DEVICE_CAPS_EX
---

# _WWAN_DEVICE_CAPS_EX structure


## -description


The <b>WWAN_DEVICE_CAPS_EX</b> structure represents the capabilities of the mobile broadband device. <b>WWAN_DEVICE_CAPS_EX</b> extends the existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a> structure by adding an <b>Executor Index</b> member, for tracking specific executors, and a <b>WwanOptionalServiceCaps</b> member, for Microsoft service extensions.


## -struct-fields




### -field WwanDeviceType

The type of the device. Miniport drivers must set the device type to be a value other than 
     <b>WwanDeviceTypeUnknown</b>.


### -field WwanCellularClass

The cellular class of the device. Miniport drivers must set the cellular class to be a value other
     than 
     <b>WwanCellularClassUnknown</b>. The values in this member control features that are specific to
     cellular technology, such as network provider registration modes.

Miniport drivers that support multi-mode should set this to <b>WwanCellularClassGsm.</b>


### -field WwanVoiceClass

The voice class of the device. This member informs the MB Service about the presence of circuit
     voice service, and how such service interacts with data service. Be aware that the MB Service does not
     support circuit-switched voice natively, nor does it preclude it. It is up to the miniport driver to
     determine how to support circuit voice. This 
     <b>WwanVoiceClass</b> member allows the MB Service to support this feature in the future.


### -field WwanSimClass

The class of the Subscriber Identity Module (SIM card). Miniport drivers must set the SIM class to
     be a value other than 
     <b>WwanSimClassUnknown</b>.


### -field WwanDataClass

A bitmap that represents the data-class(es) that the device supports. The following table shows
     the possible values for this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_NONE

</td>
<td>
The device does not support data service.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_GPRS

</td>
<td>
General Packet Radio Service (GPRS) data service is supported. This value applies only to
        GSM-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_EDGE

</td>
<td>
Enhanced Data for Global Evolution (EDGE) data service is supported. This value applies only to
        GSM-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_UMTS

</td>
<td>
Universal Mobile Telecommunications System (UMTS) data service is supported. This value applies
        only to GSM-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_HSDPA

</td>
<td>
High-Speed Downlink Packet Access (HSDPA) data service is supported. This value applies only to
        GSM-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_HSUPA

</td>
<td>
High-Speed Uplink Packet Access (HSUPA) data service is supported. This value applies only to
        GSM-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_LTE

</td>
<td>
LTE data service is supported. This value applies only to GSM-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_5G_NSA

</td>
<td>
Non-standalone 5G data service is supported. For more info about 5G data class support, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-5g-data-class-support">MB 5G data class support</a>.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_SA

</td>
<td>
Standalone 5G data service is supported. For more info about 5G data class support, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-5g-data-class-support">MB 5G data class support</a>.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_1XRTT

</td>
<td>
CDMA 1x Radio Transmission Technology (1xRTT, also known as cdma2000, CDMA2000 1x, and so on) data
        service is supported. This value applies only to CDMA-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_1XEVDO

</td>
<td>
CDMA Evolution-Data Optimized (originally Data Only, 1xEDVO, also known as CDMA2000 1x EV-DO, or
        1x EVDO) data service is supported. This value applies only to CDMA-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_1XEVDO_REVA

</td>
<td>
1xEVDO RevA data service is supported. This value applies only to CDMA-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_1XEVDV

</td>
<td>
CDMA Evolution-Data/Voice (also known as CDMA 2000 1x EV-DV, or 1x EVDV) data service is
        supported. This value applies only to CDMA-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_3XRTT

</td>
<td>
CDMA 3x Radio Transmission Technology (3xRTT) data service is supported. This value applies only
        to CDMA-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_1XEVDO_REVB

</td>
<td>
1xEVDO RevB data service is supported. This value applies only to CDMA-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_UMB

</td>
<td>
UMB data service is supported. This value applies only to CDMA-based devices.

</td>
</tr>
<tr>
<td>
WWAN_DATA_CLASS_CUSTOM

</td>
<td>
The device supports a data service not listed in this table.

</td>
</tr>
</table>
 


### -field CustomDataClass

A NULL-terminated string that represents the name of the custom data-class. This member is valid
     only when the miniport driver sets the WWAN_DATA_CLASS_CUSTOM bit in the 
     <b>WwanDataClass</b> member.


### -field WwanGsmBandClass

A bitmap that represents the frequency bands GSM-based devices support. The following table shows
     the possible values for this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_UNKNOWN

</td>
<td>
The frequency band that is supported by the device is not given.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_I

</td>
<td>
The device supports the UMTS2100 spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_II

</td>
<td>
The device supports the UMTS1900 spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_III

</td>
<td>
The device supports the UMTS1800 spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_IV

</td>
<td>
The device supports the AWS spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_V

</td>
<td>
The device supports the UMTS850 spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_VI

</td>
<td>
The device supports the UMTS800 spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_VII

</td>
<td>
The device supports the UMTS2600 spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_VIII

</td>
<td>
The device supports the UMTS900 spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_IX

</td>
<td>
The device supports the UMTS1700 spectrum.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_X

</td>
<td></td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_CUSTOM

</td>
<td>
The device supports a spectrum other than those listed in this table.

</td>
</tr>
</table>
 

If the miniport driver specifies WWAN_BAND_CLASS_CUSTOM, it should also provide the name of the
     data-class in 
     <b>CustomBandClass</b> .

For more information about these values, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-caps">OID_WWAN_DEVICE_CAPS</a>.


### -field WwanCdmaBandClass

A bitmap that represents the frequency bands CDMA-based devices support. The following table shows
     the possible values for this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_UNKNOWN

</td>
<td>
The frequency band that is supported by the device is not given.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_0

</td>
<td>
The device supports the 800MHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_I

</td>
<td>
The device supports the 1900MHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_II

</td>
<td>
The device supports the TACS band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_III

</td>
<td>
The device supports the JTACS band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_IV

</td>
<td>
The device supports the Korean PCS band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_V

</td>
<td>
The device supports the 450 MHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_VI

</td>
<td>
The device supports the 2 GHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_VII

</td>
<td>
The device supports the 700 MHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_VIII

</td>
<td>
The device supports the 1800 MHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_IX

</td>
<td>
The device supports the 900 MHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_X

</td>
<td>
The device supports the secondary 800 MHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_XI

</td>
<td>
The device supports the 400 MHz European PAMR band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_XII

</td>
<td>
The device supports the 800 MHz PAMR band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_XIII

</td>
<td>
The device supports the 2.5GHz IMT2000 Extension band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_XIV

</td>
<td>
The device supports the US PCS 1.9GHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_XV

</td>
<td>
The device supports the AWS band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_XVI

</td>
<td>
The device supports the US 2.5GHz band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_XVII

</td>
<td>
The device supports the US 2.5 GHz Forward Link Only band.

</td>
</tr>
<tr>
<td>
WWAN_BAND_CLASS_CUSTOM

</td>
<td>
The device supports a band other than the bands listed in this table.

</td>
</tr>
</table>
 

If the miniport driver specifies WWAN_BAND_CLASS_CUSTOM, it should also provide the name of the
     data-class in 
     <b>CustomBandClass</b> .

For more information about these values, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-caps">OID_WWAN_DEVICE_CAPS</a>.


### -field CustomBandClass

A NULL-terminated string that represents the name of the custom band class. This member is valid
     only when the miniport driver sets the WWAN_BAND_CLASS_CUSTOM bit in either the 
     <b>WwanGsmBandClass</b> or 
     <b>WwanCdmaBandClass</b> members, as appropriate.


### -field WwanSmsCaps

A bitmap that represents the type of SMS messages and directional flow that the device supports.
     The following table shows the valid SMS capabilities settings.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_SMS_CAPS_NONE

</td>
<td>
The device does not support SMS messages.

</td>
</tr>
<tr>
<td>
WWAN_SMS_CAPS_PDU_SEND

</td>
<td>
For GSM-based devices, this value means that the device supports sending PDU-style SMS
        messages.

For CDMA-based devices, this value means that the device is capable of sending SMS messages in
        binary format as defined in section "3.4.2.1 SMS Point-to-Point Message" in 3GPP2 specification
        C.S0015-A "Short Message Service (SMS) for Wideband Spread Spectrum Systems".

</td>
</tr>
<tr>
<td>
WWAN_SMS_CAPS_PDU_RECEIVE

</td>
<td>
For GSM-based devices, this value means that the device supports receiving PDU-style SMS
        messages.

For CDMA-based devices, this value means that the device is capable of reading the SMS messages in
        binary format as defined in section "3.4.2.1 SMS Point-to-Point Message" in the 3GPP2 specification
        C.S0015-A "Short Message Service (SMS) for Wideband Spread Spectrum Systems".

</td>
</tr>
<tr>
<td>
WWAN_SMS_CAPS_TEXT_SEND

</td>
<td>
The device supports sending Text-style SMS messages. This flag applies for CDMA-based devices.

</td>
</tr>
<tr>
<td>
WWAN_SMS_CAPS_TEXT_RECEIVE

</td>
<td>
The device supports receiving Text-style SMS messages. This flag applies for CDMA-based
        devices.

</td>
</tr>
</table>
 

Miniport drivers should set this member to reflect support for only GSM PDU format for receiving and sending SMS when the current home provider is multi-mode capable. Therefure, if the miniport driver receives a SMS in the cellular class native format, for example CDMA TEXT or CDMA PDU, then the miniport driver is required to do the translation to GSM PDU and indicate it to the MB Service. Similarly if the miniport driver receives a send request in GSM PDU format then it is required to do the translation to its native cellular class format.


### -field WwanControlCaps

A bitmap that represents the control capabilities that the device supports. The following table
     shows the valid WwanControlCaps settings for GSM-based and CDMA-based devices. 
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_REG_MANUAL

</td>
<td>
Indicates whether the provider network allows manual network selection. Miniport drivers for
        GSM-based devices should specify this flag. Miniport drivers for CDMA-based devices should not
        specify this flag.

</td>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_HW_RADIO_SWITCH

</td>
<td>
Indicates the presence of a hardware radio power switch. This corresponds to the 
        <b>WwanDeviceTypeEmbedded</b> value of the WWAN_DEVICE_TYPE enumeration.

</td>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_CDMA_MOBILE_IP

</td>
<td>
Indicates that the CDMA-based device is configured to support mobile IP. This flag applies only to
        CDMA-based devices.

Miniport drivers should not set this flag when the current home provider is multi-mode capable.

</td>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_CDMA_SIMPLE_IP

</td>
<td>
Indicates that the CDMA-based device is configured for simple IP support. This flag applies only
        to CDMA-based devices.

Miniport drivers should not set this flag when the current home provider is multi-mode capable.

</td>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_CDMA_MOBILE_IP ored with WWAN_CTRL_CAPS_CDMA_SIMPLE_IP

</td>
<td>
Indicates that the CDMA-based device is configured to support mobile IP, with simple IP as a
        fallback option.

</td>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_PROTECT_UNIQUEID

</td>
<td>
Indicates that Windows should not display the International Mobile Subscriber Identity (IMSI).

</td>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_USSD

</td>
<td>
Indicates that the GSM-based MB device is configured to support the USSD protocol. This flag applies only to GSM-based devices.

Miniport drivers that support sending and receiving USSD messages set this flag.

Miniport drivers can set this flag  when the current multi-mode capable home providers GSM side of the network supports USSD even if the CDMA side of the network does not support USSD.

</td>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_MODEL_MULTI_CARRIER

</td>
<td>
Indicates that the MB device supports registering and connecting to multiple network operators.

</td>
</tr>
<tr>
<td>
WWAN_CTRL_CAPS_MULTI_MODE

</td>
<td>
This flag indicates that the current home provider supports multiple cellular classes/RATs (Radio Access Technologies).

</td>
</tr>
</table>
 

Miniport drivers of CDMA-based devices must specify WWAN_CTRL_CAPS_CDMA_MOBILE_IP, or
     WWAN_CTRL_CAPS_CDMA_SIMPLE_IP, or both flags to inform the MB Service about the type of IP that the
     device supports.


### -field DeviceId

A NULL-terminated string that represents the device ID.

For GSM-based devices, the string must
     conform to the International Mobile Equipment Identity (IMEI) format (up to 15 digits).

For CDMA-based
     devices, the string must conform to both the Electronic Serial Number (ESN, 11 digits) and Mobile
     Equipment Identifier (MEID, 17 digits) formats.

For multi-mode capable miniport drivers, for example those that set the <b>WWAN_CTRL_CAPS_MULTI_MODE</b> flag in <b>WwanControlCaps</b>, only the GSM-based <b>DeviceId</b> must be reported.

This value should be stored in the device's memory and
     must be available even when the MB device/SIM requires a PIN to unlock.


### -field Manufacturer

A NULL-terminated string that represents the manufacturer of the device. This member is
     optional.


### -field Model

A NULL-terminated string that represents the model of the device. This member is optional.


### -field FirmwareInfo

A NULL-terminated string that represents the firmware specific information about the device. This
     member is optional.


### -field MaxActivatedContexts

The maximum number of activated contexts that are supported by the device. Miniport drivers should
     enforce this limit by failing any activation attempts that exceed 
     <b>MaxActivatedContexts</b>.


### -field WwanAuthAlgoCaps

A bitmap that represents the types of authentication methods the MB device supports.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_AUTH_ALGO_CAPS_NONE

</td>
<td>
The MB device does not support any authentication methods.

</td>
</tr>
<tr>
<td>
WWAN_AUTH_ALGO_CAPS_SIM

</td>
<td>
The MB device supports the SIM authentication method.

</td>
</tr>
<tr>
<td>
WWAN_AUTH_ALGO_CAPS_AKA

</td>
<td>
The MB device supports the AKA authentication method.

</td>
</tr>
<tr>
<td>
WWAN_AUTH_ALGO_CAPS_AKAP

</td>
<td>
The MB device supports the AKA' (AKA Prime) authentication method.

</td>
</tr>
</table>
 


### -field ExecutorIndex

The <b>WwanDeviceType</b> member for <b>WWAN_DEVICE_CAPS_EX</b> no longer refers to the modem device but rather to an individual executor. Each device is an RF executor entity of which the OS is aware.


### -field WwanOptionalServiceCaps

A ULONG structure that represents the Microsoft service extensions the underlying modem supports. It is a 64-bit bitmap structure that whose undefined bits are reserved and must be set to "0." As new service extensions are introduced, the reserved bits will be used to represent the new service extensions.

<table>
<tr>
<th>Value</th>
<th>Mask</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_OPTIONAL_SERVICE_CAPS_NONE

</td>
<td>
0h

</td>
<td>
The device and driver do not support optional service extensions.

</td>
</tr>
<tr>
<td>
WWAN_OPTIONAL_SERVICE_CAPS_LTE_ATTACH

</td>
<td>
1h

</td>
<td>
 The device and driver support LTE attach configuration and the following MBIM CIDs:

<ul>
<li>MBIM_CID_MS_LTE_ATTACH_CONFIG</li>
<li>MBIM_CID_MS_LTE_ATTACH_STATUS</li>
</ul>
</td>
</tr>
<tr>
<td>
WWAN_OPTIONAL_SERVICE_CAPS_CONTEXT_MGMT

</td>
<td>
2h

</td>
<td>
The device and driver support the OS managing modem provisioned contexts and the following MBIM CID:

<ul>
<li>MBIM_CID_PROVISIONED_CONTEXT_V2</li>
</ul>
</td>
</tr>
<tr>
<td>
WWAN_OPTIONAL_SERVICE_CAPS_MULTI_SIM

</td>
<td>
4h

</td>
<td>
The device and driver support multi-SIM/multi-executors and the following OIDs:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sys-caps">OID_WWAN_SYS_CAPS_INFO</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-slot-mappings">OID_WWAN_DEVICE_SLOT_MAPPING_INFO</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-slot-info-status">OID_WWAN_SLOT_INFO</a>
</li>
</ul>
</td>
</tr>
<tr>
<td>
WWAN_OPTIONAL_SERVICE_CAPS_EX_SAR

</td>
<td>
8h

</td>
<td>
The device and driver support SAR configuration from the OS and the following MBIM CIDs:

<ul>
<li>MBIM_CID_MS_SAR_CONFIG</li>
<li>MBIM_CID_MS_TRANSMISSION_STATUS</li>
</ul>
</td>
</tr>
<tr>
<td>
WWAN_OPTIONAL_SERVICE_CAPS_NETWORK_BLACKLIST

</td>
<td>
16h

</td>
<td>
The device and driver support network blacklist configuration from the OS and the following MBIM CID:

<ul>
<li>MBIM_CID_MS_NETWORK_BLACKLIST</li>
</ul>
</td>
</tr>

<tr>
     <td>WWAN_OPTIONAL_SERVICE_CAPS_5G_NSA</td>
     <td>
     <td>The device and driver support all new 5G-related extensions in Windows 10, version 1903. The following table shows the NDIS messages and their revisions that the miniport driver must support if this bit is set.
          <table>
               <th>OID</th>
               <th>Message</th>
               <th>Revision</th>
               <tr>
                    <td>WWAN_DEVICE_CAPS_EX</td>
                    <td>NDIS_WWAN_DEVICE_CAPS_EX</td>
                    <td>1</td>
               </tr>
               <tr>
                    <td>WWAN_REGISTER_STATE</td>
                    <td>NDIS_WWAN_REGISTRATION_STATE</td>
                    <td>3</td>
               </tr>
               <tr>
                    <td>WWAN_PACKET_SERVICE</td>
                    <td>NDIS_WWAN_PACKET_SERVICE_STATE</td>
                    <td>2</td>
               </tr>
               <tr>
                    <td>WWAN_SIGNAL_STATE</td>
                    <td>NDIS_WWAN_SIGNAL_STATE</td>
                    <td>2</td>
               </tr>
          </table>
     </td>
</tr>

</table>
 


### -field CellularClassListHeader

A formatted WWAN_LIST_HEADER object that represents a list of cellular classes that a multi-mode capable device supports. The <b>ElementType</b> member in WWAN_LIST_HEADER should always be set to <b>WwanStructCellularClass</b>. The <b>ElementCount</b> member in WWAN_LIST_HEADER is set to the number of cellular classes that follow the WWAN_LIST_HEADER structure. MB devices that are not multi-mode capable should set <b>ElementCount</b> to 0.


## -remarks



Miniport drivers should specify WWAN_DATA_CLASS_CUSTOM if the data service supported by the device
    does not belong to any of the other values defined in the table for the 
    <b>WwanDataClass</b> member. If a miniport driver sets the WWAN_DATA_CLASS_CUSTOM flag, the miniport
    driver should also provide the name of the data-class in the 
    <b>CustomDataClass</b> member.

For GSM-based devices, only GSM-based data-classes must be specified. For example, GPRS, EDGE, UMTS,
    HSDPA, LTE, and TD-SCDMA. If your miniport driver supports TD-SCDMA, then it should specify
    WWAN_DATA_CLASS_CUSTOM in the 
    <b>WwanDataClass</b> member and the string "TD-SCDMA" in the 
    <b>CustomDataClass</b> member.

For CDMA-based devices, only CDMA-related data services must be specified. For example, 1xRTT,
    1xEV-DO, 1xEV-DO RevA, and UMB. 1xEV-DO RevB is defined for future use. 1xEV-DV and 3xRTT are also
    defined for completeness.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndiswwan/ns-ndiswwan-_ndis_wwan_device_caps_ex">NDIS_WWAN_DEVICE_CAPS_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-caps-ex">OID_WWAN_DEVICE_CAPS_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>
 

 

