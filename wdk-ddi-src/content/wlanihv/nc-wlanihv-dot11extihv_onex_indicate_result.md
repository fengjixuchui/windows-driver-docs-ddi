---
UID: NC:wlanihv.DOT11EXTIHV_ONEX_INDICATE_RESULT
title: DOT11EXTIHV_ONEX_INDICATE_RESULT (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvonexindicateresult.htm
tech.root: netvista
ms.assetid: bf865b33-6e44-4724-868d-73150cf5b589
ms.date: 02/16/2018
ms.keywords: DOT11EXTIHV_ONEX_INDICATE_RESULT, Dot11ExtIhvOneXIndicateResult, Dot11ExtIhvOneXIndicateResult callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_af60ece5-6f3a-4a5b-9207-0e3cf68a012b.xml, netvista.dot11extihvonexindicateresult, wlanihv/Dot11ExtIhvOneXIndicateResult
ms.topic: callback
f1_keywords:
 - "wlanihv/Dot11ExtIhvOneXIndicateResult"
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wlanihv.h
api_name:
- Dot11ExtIhvOneXIndicateResult
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_ONEX_INDICATE_RESULT callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvOneXIndicateResult</i> IHV Handler function when it completes an 802.1X authentication
  operation with the access point (AP).


## -prototype


```cpp
DOT11EXTIHV_ONEX_INDICATE_RESULT Dot11ExtIhvOneXIndicateResult;

DWORD APIENTRY Dot11ExtIhvOneXIndicateResult(
  _In_opt_ HANDLE                      hIhvExtAdapter,
  _In_     DOT11_MSONEX_RESULT         msOneXResult,
  _In_opt_ PDOT11_MSONEX_RESULT_PARAMS pDot11MsOneXResultParams
)
{ ... }
```


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param msOneXResult [in]

The result of the 802.1X authentication operation specified through a
     <a href="..\wlanihv\ne-wlanihv-_dot11_msonex_result.md">DOT11_MSONEX_RESULT</a> enumeration
     value.


### -param pDot11MsOneXResultParams [in, optional]

A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11_msonex_result_params.md">
     DOT11_MSONEX_RESULT_PARAMS</a> structure that contains result parameters.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The IHV Extensions DLL can initiate an 802.1X authentication operation by using the 802.1X module of
    the Native 802.11 framework. This allows the DLL to make use of the standard extensible authentication
    protocol (EAP) algorithms that are supported by the operating system.

The IHV Extensions DLL initiates the 802.1X authentication operation by calling the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a> function.
    <b>Dot11ExtStartOneX</b> can only be called either during a post-association operation or after the
    operation has completed. For more information about this operation, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/post-association-operations">Post-Association Operations</a>.

After the operating system has completed the 802.1X authentication operation, it calls the
    <i>
    Dot11ExtIhvOneXIndicateResult</i> IHV Handler function.

For more information about using the 802.1X module for authentication, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/interface-to-the-native-802-11-802-1x-module">Interface to the Native
    802.11 802.1X Module</a>





## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
   Dot11ExtIhvOneXIndicateResult</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>



<a href="..\wlanihv\ns-wlanihv-_dot11_msonex_result_params.md">DOT11_MSONEX_RESULT_PARAMS</a>



<a href="..\wlanihv\ne-wlanihv-_dot11_msonex_result.md">DOT11_MSONEX_RESULT</a>



 

 


