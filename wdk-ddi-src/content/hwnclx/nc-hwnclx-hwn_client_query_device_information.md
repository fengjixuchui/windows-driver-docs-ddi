---
UID: NC:hwnclx.HWN_CLIENT_QUERY_DEVICE_INFORMATION
title: HWN_CLIENT_QUERY_DEVICE_INFORMATION (hwnclx.h)
description: Implemented by the client driver to retrieve hardware notification component attributes.
old-location: gpiobtn\hwn_client_query_device_information.htm
tech.root: gpiobtn
ms.assetid: e67f0384-79a8-4040-aab4-bf5b865ad989
ms.date: 02/15/2018
ms.keywords: HWN_CLIENT_QUERY_DEVICE_INFORMATION, HwnClientQueryDeviceInformation, HwnClientQueryDeviceInformation callback function, PHWN_CLIENT_QUERY_DEVICE_INFORMATION, PHWN_CLIENT_QUERY_DEVICE_INFORMATION callback function pointer, gpiobtn.hwn_client_query_device_information, hwnclx/HwnClientQueryDeviceInformation
ms.topic: callback
req.header: hwnclx.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Hwnclx.h
api_name:
- PHWN_CLIENT_QUERY_DEVICE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: HPMI_QUERY_CAPABILITIES_RESPONSE, *PHPMI_QUERY_CAPABILITIES_RESPONSE
---

# HWN_CLIENT_QUERY_DEVICE_INFORMATION callback


## -description



Implemented by the client driver to retrieve hardware notification component attributes.


## -prototype


```cpp
HWN_CLIENT_QUERY_DEVICE_INFORMATION HwnClientQueryDeviceInformation;

NTSTATUS HwnClientQueryDeviceInformation(
  _In_  PVOID                      Context,
  _Out_ PCLIENT_DEVICE_INFORMATION Information
)
{ ... }

typedef HWN_CLIENT_QUERY_DEVICE_INFORMATION PHWN_CLIENT_QUERY_DEVICE_INFORMATION;
```


## -parameters




### -param Context [in]

Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.


### -param Information [out]

Pointer to a buffer that receives the controller’s attributes.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.




## -remarks



Register your implementation of this callback function by setting the appropriate member of <a href="https://docs.microsoft.com/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Hardware notifications reference</a>



 

 


