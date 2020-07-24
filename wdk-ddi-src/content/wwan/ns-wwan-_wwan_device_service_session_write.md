---
UID: NS:wwan._WWAN_DEVICE_SERVICE_SESSION_WRITE
title: _WWAN_DEVICE_SERVICE_SESSION_WRITE (wwan.h)
description: The WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents data associated with a device service session write request.
old-location: netvista\wwan_device_service_session_write.htm
tech.root: netvista
ms.assetid: 8134E635-5FC3-4990-A7CC-E43ECEB1FBB6
ms.date: 05/02/2018
keywords: ["_WWAN_DEVICE_SERVICE_SESSION_WRITE structure"]
ms.keywords: "*PWWAN_DEVICE_SERVICE_SESSION_WRITE, PWWAN_DEVICE_SERVICE_SESSION_WRITE, PWWAN_DEVICE_SERVICE_SESSION_WRITE structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_SESSION_WRITE, WWAN_DEVICE_SERVICE_SESSION_WRITE structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_SESSION_WRITE, netvista.wwan_device_service_session_write, wwan/PWWAN_DEVICE_SERVICE_SESSION_WRITE, wwan/WWAN_DEVICE_SERVICE_SESSION_WRITE"
f1_keywords:
 - "wwan/WWAN_DEVICE_SERVICE_SESSION_WRITE"
 - "WWAN_DEVICE_SERVICE_SESSION_WRITE"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
- WWAN_DEVICE_SERVICE_SESSION_WRITE
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_SESSION_WRITE, *PWWAN_DEVICE_SERVICE_SESSION_WRITE
---

# _WWAN_DEVICE_SERVICE_SESSION_WRITE structure


## -description


The WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents data associated with a device service session write request.


## -struct-fields




### -field uSessionID

The session ID of the device service.


### -field uDataSize

The size, in bytes, of the device service data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxSessionDataSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_device_service_session_write">NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a>
 

 

