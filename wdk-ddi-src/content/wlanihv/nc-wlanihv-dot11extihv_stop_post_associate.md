---
UID: NC:wlanihv.DOT11EXTIHV_STOP_POST_ASSOCIATE
title: DOT11EXTIHV_STOP_POST_ASSOCIATE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvstoppostassociate.htm
tech.root: netvista
ms.assetid: bd924049-3932-4e85-908e-c3fb488b3a8c
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_STOP_POST_ASSOCIATE callback"]
ms.keywords: DOT11EXTIHV_STOP_POST_ASSOCIATE, Dot11ExtIhvStopPostAssociate, Dot11ExtIhvStopPostAssociate callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_674652ff-a01d-493b-9b11-bff378f25f2a.xml, netvista.dot11extihvstoppostassociate, wlanihv/Dot11ExtIhvStopPostAssociate
f1_keywords:
 - "wlanihv/Dot11ExtIhvStopPostAssociate"
req.header: wlanihv.h
req.include-header: Wlanihv.h, Windot11.h
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
- Dot11ExtIhvStopPostAssociate
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_STOP_POST_ASSOCIATE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div>

The operating system calls the
  <i>Dot11ExtIhvStopPostAssociate</i> function to cancel the post-association operation initiated through a
  call to the
  <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
  Dot11ExtIhvPerformPostAssociate</a> IHV Handler function.


## -prototype


```cpp
DOT11EXTIHV_STOP_POST_ASSOCIATE Dot11ExtIhvStopPostAssociate;

DWORD APIENTRY Dot11ExtIhvStopPostAssociate(
  _In_opt_ HANDLE             hIhvExtAdapter,
  _In_     PDOT11_MAC_ADDRESS pPeer,
  _In_     DOT11_ASSOC_STATUS dot11AssocStatus
)
{ ... }
```


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param pPeer [in]

A pointer to a
     <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a> structure, which
     contains the media access control (MAC) of the access point (AP) with which the IHV Extensions DLL
     initiated a post-association operation.


<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
     service set (BSS) networks.</div>

### -param dot11AssocStatus [in]

A
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dot11-assoc-status-status-codes">DOT11_ASSOC_STATUS</a> type that specifies the
     association status of the 802.11 station to the network.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The operating system calls the
    <i>Dot11ExtIhvStopPostAssociate</i> function to cancel the post-association operation whenever one of the
    following occurs.

<ul>
<li>
The WLAN adapter completes a disassociation operation with the AP. In this situation, the Native
      802.11 miniport driver, which manages the adapter, makes a media-specific
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
      NDIS_STATUS_DOT11_DISASSOCIATION</a> indication. For more information about the disassociation
      operation, see
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/disassociation-operations">Disassociation Operations</a>.

</li>
<li>
The WLAN adapter is disabled or removed. In this situation, the operating system calls the
      <i>Dot11ExtIhvStopPostAssociate</i> function before it calls the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">
      Dot11ExtIhvDeinitAdapter</a> function.

</li>
</ul>
The operating system calls the
    <i>Dot11ExtIhvStopPostAssociate</i> function to notify the IHV Extensions DLL that the data port created
    for the association is down. The operating system calls this function regardless of whether the DLL has
    completed the post-association operation through a call to
    <a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
    Dot11ExtPostAssociateCompletion</a>.

For more information about the post-association operation, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/post-association-operations">Post-Association Operations</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/dot11-assoc-status-status-codes">DOT11_ASSOC_STATUS</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
   NDIS_STATUS_DOT11_DISASSOCIATION</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>



<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>



 

 


