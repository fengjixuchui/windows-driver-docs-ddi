---
UID: NC:wlanihv.DOT11EXTIHV_PERFORM_PRE_ASSOCIATE
title: DOT11EXTIHV_PERFORM_PRE_ASSOCIATE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvperformpreassociate.htm
tech.root: netvista
ms.assetid: 5bf7a1ce-bff0-481e-8053-584fb6319146
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_PERFORM_PRE_ASSOCIATE callback"]
ms.keywords: DOT11EXTIHV_PERFORM_PRE_ASSOCIATE, Dot11ExtIhvPerformPreAssociate, Dot11ExtIhvPerformPreAssociate callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_431e221a-0022-47ad-b2bf-e7580eb889e8.xml, netvista.dot11extihvperformpreassociate, wlanihv/Dot11ExtIhvPerformPreAssociate
f1_keywords:
 - "wlanihv/Dot11ExtIhvPerformPreAssociate"
req.header: wlanihv.h
req.include-header: Wlanihv.h, L2cmn.h
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
- Dot11ExtIhvPerformPreAssociate
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PERFORM_PRE_ASSOCIATE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvPerformPreAssociate</i> function to request that the IHV Extensions DLL initiate a
  pre-association operation with the basic service set (BSS) network.


## -prototype


```cpp
DOT11EXTIHV_PERFORM_PRE_ASSOCIATE Dot11ExtIhvPerformPreAssociate;

DWORD APIENTRY Dot11ExtIhvPerformPreAssociate(
  _In_opt_ HANDLE                             hIhvExtAdapter,
  _In_opt_ HANDLE                             hConnectSession,
  _In_opt_ PDOT11EXT_IHV_PROFILE_PARAMS       pIhvProfileParams,
  _In_     PDOT11EXT_IHV_CONNECTIVITY_PROFILE pIhvConnProfile,
  _In_     PDOT11EXT_IHV_SECURITY_PROFILE     pIhvSecProfile,
  _In_     PDOT11_BSS_LIST                    pConnectableBssid,
  _Out_    PDWORD                             pdwReasonCode
)
{ ... }
```


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param hConnectSession [in, optional]

The handle used by the operating system to reference the connection session with the basic service
     set (BSS) network.


### -param pIhvProfileParams [in, optional]

A pointer to a
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">
     DOT11EXT_IHV_PROFILE_PARAMS</a> structure. This structure defines the attributes of the basic service
     set (BSS) network to which the profile extensions will be applied.


### -param pIhvConnProfile [in]

A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</a> structure that contains connectivity settings for the IHV
     profile.


### -param pIhvSecProfile [in]

A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">
     DOT11EXT_IHV_SECURITY_PROFILE</a> structure that specifies security settings for the IHV
     profile.


### -param pConnectableBssid [in]

A pointer to a
     <a href="..\wlclient\ns-wlclient-_dot11_bss_list.md">DOT11_BSS_LIST</a> structure, which contains one
     or more 802.11 Beacon or Probe Response frames for the service set identifier (SSID) of the BSS network
     with which the DLL will perform the pre-association operation.


### -param pdwReasonCode [out]

A pointer to a DWORD value, which provides additional information for the return value of the
     <i>Dot11ExtIhvPerformPreAssociate</i> function. The IHV Extensions DLL must set *
     <i>pdwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in
     L2cmn.h.


## -returns



If the IHV Extension DLL can initiate the pre-association operation, it must complete the operation
      asynchronously. In this situation, the function returns ERROR_SUCCESS.

If the IHV Extensions DLL cannot initiate the pre-association operation, it returns an error code
      defined in
      <i>Winerror.h</i>.




## -remarks



The operating system calls the
    <i>Dot11ExtIhvPerformPreAssociate</i> function to initiate a pre-association operation with the IHV
    Extensions DLL. The operating system initiates this operation before it initiates a connection operation
    with a basic service set (BSS) network through the WLAN adapter. For more information about the
    connection operation, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/connection-operations">Connection Operations</a>.

The pre-association operation must be completed asynchronously from the call to
    <i>Dot11ExtIhvPerformPreAssociate</i>. After the pre-association operation completes, the IHV Extensions
    DLL must call
    <a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
    Dot11ExtPreAssociateCompletion</a>.

When the
    <i>Dot11ExtIhvPerformPreAssociate</i> function is called, the IHV Extensions DLL must follow these
    guidelines.

<ul>
<li>
If the IHV Extensions DLL can initiate the pre-association operation, the
      <i>Dot11ExtIhvPerformPreAssociate</i> function must return ERROR_SUCCESS and complete the operation
      asynchronously.

</li>
<li>
The IHV Extensions DLL provides more information regarding the initiation of the pre-association
      operation through the
      <i>pdwReasonCode</i> parameter. The DLL must set *
      <i>pdwReasonCode</i> to one of the following:

<ul>
<li>
L2_REASON_CODE_SUCCESS, if the pre-association operation can initiated successfully.

</li>
<li>
An appropriate L2_REASON_CODE_xxxx error value, if the pre-association operation could not be
        initiated.

</li>
<li>
An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1), regardless of whether the pre-association operation could be initiated
        or not.

</li>
</ul>
</li>
</ul>
For more information about the pre-association operation, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/pre-association-operation-overview">Pre-Association Operation</a>.




## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>



<a href="..\wlclient\ns-wlclient-_dot11_bss_list.md">DOT11_BSS_LIST</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
   Dot11ExtPreAssociateCompletion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-connect-request">OID_DOT11_CONNECT_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-extensibility-functions">Native 802.11 IHV
   Extensibility Functions</a>



<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>



 

 


