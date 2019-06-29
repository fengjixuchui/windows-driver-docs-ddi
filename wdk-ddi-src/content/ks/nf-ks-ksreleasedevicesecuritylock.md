---
UID: NF:ks.KsReleaseDeviceSecurityLock
title: KsReleaseDeviceSecurityLock function (ks.h)
description: The KsReleaseDeviceSecurityLock function releases a previously acquired security lock on the device object header.
old-location: stream\ksreleasedevicesecuritylock.htm
tech.root: stream
ms.assetid: b14a4816-2e72-491d-9881-ae532c287e99
ms.date: 04/23/2018
ms.keywords: KsReleaseDeviceSecurityLock, KsReleaseDeviceSecurityLock function [Streaming Media Devices], ks/KsReleaseDeviceSecurityLock, ksfunc_4f6e594d-1f06-4741-89f2-d153db3a63e7.xml, stream.ksreleasedevicesecuritylock
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsReleaseDeviceSecurityLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsReleaseDeviceSecurityLock function


## -description


The <b>KsReleaseDeviceSecurityLock</b> function releases a previously acquired security lock on the device object header.


## -parameters




### -param Header [in]

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b> whose security lock is to be released.


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksallocatedeviceheader">KsAllocateDeviceHeader</a>
 

 

