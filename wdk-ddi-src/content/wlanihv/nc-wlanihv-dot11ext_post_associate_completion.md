---
UID: NC:wlanihv.DOT11EXT_POST_ASSOCIATE_COMPLETION
title: DOT11EXT_POST_ASSOCIATE_COMPLETION (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extpostassociatecompletion.htm
tech.root: netvista
ms.assetid: 25db270c-3de8-4ced-82f1-2cd778006538
ms.date: 02/16/2018
keywords: ["DOT11EXT_POST_ASSOCIATE_COMPLETION callback"]
ms.keywords: DOT11EXT_POST_ASSOCIATE_COMPLETION, Dot11ExtPostAssociateCompletion, Dot11ExtPostAssociateCompletion callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_d7368927-721a-4cd4-9ccc-ccb02964b811.xml, netvista.dot11extpostassociatecompletion, wlanihv/Dot11ExtPostAssociateCompletion
f1_keywords:
 - "wlanihv/Dot11ExtPostAssociateCompletion"
 - "Dot11ExtPostAssociateCompletion"
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
- Dot11ExtPostAssociateCompletion
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_POST_ASSOCIATE_COMPLETION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.

The IHV Extensions DLL calls the
  <b>Dot11ExtPostAssociateCompletion</b> function to asynchronously complete a
  post-association operation initiated through a call to the
  <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
  Dot11ExtIhvPerformPostAssociate</a> IHV Handler function.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtPostAssociateCompletion(
  _In_opt_ HANDLE             hDot11SvcHandle,
  _In_opt_ HANDLE             hSecuritySessionID,
  _In_opt_ PDOT11_MAC_ADDRESS pPeer,
  _In_     DWORD              dwReasonCode,
  _In_     DWORD              dwWin32Error
);
```


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param hSecuritySessionID [in, optional]

The handle of the security session identifier (ID) returned through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
     Dot11ExtIhvPerformPostAssociate</a> IHV Handler function.


### -param pPeer [in, optional]

The media access control (MAC) address of the access point (AP) with which the IHV Extensions DLL
     performed a security operation. This parameter is formatted as a
     <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a> structure.


<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
     service set (BSS) networks.</div>

### -param dwReasonCode [in]

A value that provides additional information for the completion status of the post-association
     operation. The IHV Extensions DLL must set
     <i>dwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in
     L2cmn.h.


The IHV Extensions DLL returns the general completion status of the post-association operation
     through the
     <i>dwWin32Error</i> parameter. Typically, the IHV Extensions DLL sets
     <i>dwReasonCode</i> to a value within the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
     L2_REASON_CODE_GROUP_SIZE-1).


### -param dwWin32Error [in]

The completion status of the post-association operation as defined by an error code within
     Winerror.h. If the operation completes successfully, the IHV Extensions DLL must set
     <i>dwWin32Error</i> to ERROR_SUCCESS.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The IHV Extensions DLL calls the
    <i>Dot11ExtPostAssociateCompletion</i> function to do any of the following:

<ul>
<li>
Complete the post-association operation initiated by a call to the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
      Dot11ExtIhvPerformPostAssociate</a> IHV Handler function.

</li>
<li>
After completing the post-association operation, indicate a change in the port state for the
      security session referenced by the
      <i>hSecuritySessionID</i> parameter.

For example, if the authorization state of the port changes, the IHV Extensions DLL can notify the
      operating system by calling
      <i>Dot11ExtPostAssociateCompletion</i>.

</li>
</ul>
The IHV Extensions DLL must follow these guidelines when calling the
    <b>Dot11ExtPostAssociateCompletion</b> function.

<ul>
<li>
If the post-association operation completed successfully, the IHV Extensions DLL must set
      <i>dwReasonCode</i> to one of the following:

<ul>
<li>
L2_REASON_CODE_SUCCESS.

</li>
<li>
An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).

</li>
</ul>
In this situation, the IHV Extensions DLL must set
      <i>dwWin32Error</i> to ERROR_SUCCESS.

<div class="alert"><b>Note</b>  If the IHV Extensions DLL sets
      <i>dwWin32Error</i> to ERROR_SUCCESS, the operating system will assume that the port state for the
      security session is in an authorized state. After the port is in an authorized state, the operating
      system allows all data packets to be sent through the WLAN adapter.</div>
<div> </div>
</li>
<li>
If the post-association operation completed with a failure, the IHV Extensions DLL must not set
      <i>dwReasonCode</i> to L2_REASON_CODE_SUCCESS. Instead, the DLL must set
      <i>dwReasonCode</i> to one of the following:

<ul>
<li>
An appropriate L2_REASON_CODE_xxxx error value.

</li>
<li>
An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).

</li>
</ul>
In this situation, the IHV Extensions DLL must not set
      <i>dwWin32Error</i> to ERROR_SUCCESS. Instead, the DLL must set
      <i>dwWin32Error</i> to an appropriate error code defined in
      Winerror.h.

<div class="alert"><b>Note</b>  If the IHV Extensions DLL does not set
      <i>dwWin32Error</i> to ERROR_SUCCESS, the operating system will assume the port state for the security
      session is in an unauthorized state. After the port is in an unauthorized state, the operating system
      allows security packets, including packets sent through the
      <a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a> IHV Extensions
      function, to be sent through the WLAN adapter.</div>
<div> </div>
</li>
<li>
The IHV Extensions DLL must call
      <b>Dot11ExtPostAssociateCompletion</b> to cancel all pending post-association operation whenever the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a> or
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a> IHV
      Handler functions are called. In this situation, the DLL must set the
      <i>dwStatus</i> parameter to ERROR_CANCELLED.

</li>
</ul>



## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>



<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a>



 

 


