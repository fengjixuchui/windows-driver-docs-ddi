---
UID: NC:swenum.PFNDEREFERENCEDEVICEOBJECT
title: PFNDEREFERENCEDEVICEOBJECT (swenum.h)
description: The driver can use this routine to decrement the reference count of the PDO.
old-location: stream\kstrdereferencedeviceobject.htm
tech.root: stream
ms.assetid: 8d220b69-122c-4019-9c70-4c744503481d
ms.date: 04/23/2018
ms.keywords: KStrDereferenceDeviceObject, KStrDereferenceDeviceObject routine [Streaming Media Devices], PFNDEREFERENCEDEVICEOBJECT, ks/KStrDereferenceDeviceObject, ksfunc_521a642c-7a09-416b-a883-09ec5af4f026.xml, stream.kstrdereferencedeviceobject
ms.topic: callback
req.header: swenum.h
req.include-header: Ks.h, Swenum.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
- ks.h
api_name:
- KStrDereferenceDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNDEREFERENCEDEVICEOBJECT callback function


## -description


The driver can use this routine to decrement the reference count of the PDO.


## -parameters




### -param Context [in]

Pointer to a device extension of the device's PDO.


## -returns



Returns STATUS_SUCCESS if the request is handled. Otherwise returns an appropriate error code.




## -remarks



Minidrivers access this method through the <b>DereferenceDeviceObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-bus_interface_reference">BUS_INTERFACE_REFERENCE</a> structure.

When the PDO's reference count is 0, it becomes eligible for removal. Note that this condition does not guarantee removal.



