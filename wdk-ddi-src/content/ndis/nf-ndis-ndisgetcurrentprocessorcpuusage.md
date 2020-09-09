---
UID: NF:ndis.NdisGetCurrentProcessorCpuUsage
title: NdisGetCurrentProcessorCpuUsage function (ndis.h)
description: The NdisGetCurrentProcessorCpuUsage function returns the average amount of activity on the current processor since boot as a percentage.Note  This function is deprecated.
old-location: netvista\ndisgetcurrentprocessorcpuusage.htm
tech.root: netvista
ms.assetid: 03f1559c-83a7-478c-a616-ebe6002cb724
ms.date: 05/02/2018
keywords: ["NdisGetCurrentProcessorCpuUsage function"]
ms.keywords: NdisGetCurrentProcessorCpuUsage, NdisGetCurrentProcessorCpuUsage function [Network Drivers Starting with Windows Vista], ndis/NdisGetCurrentProcessorCpuUsage, ndis_sysinfo_ref_64c35a8c-5776-4902-b062-0685a16f5453.xml, netvista.ndisgetcurrentprocessorcpuusage
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated for NDIS 6.0 and later drivers in Windows Vista and later. Deprecated for NDIS 5.1 drivers (see       NdisGetCurrentProcessorCpuUsage (NDIS 5.1)) in Windows XP and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGetCurrentProcessorCpuUsage
 - ndis/NdisGetCurrentProcessorCpuUsage
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisGetCurrentProcessorCpuUsage
---

# NdisGetCurrentProcessorCpuUsage function


## -description

The 
  <b>NdisGetCurrentProcessorCpuUsage</b> function returns the  average amount of activity on the current processor since boot as a
  percentage.
<div class="alert"><b>Note</b>  This function is deprecated. Do not use it in your driver.</div><div> </div>

## -parameters

### -param pCpuUsage 

[out]
A pointer to a caller-supplied variable that receives the average usage of the current processor since boot, expressed as a percentage.

## -remarks

The <b>NdisGetCurrentProcessorCpuUsage</b> function returns the average amount of activity on the current processor since the last boot, not the current usage level. This information is not particularly useful. Therefore, we recommend that you don't use <b>NdisGetCurrentProcessorCpuUsage</b> in your driver.

As an alternative, you can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetcurrentprocessorcounts">NdisGetCurrentProcessorCounts</a> to see whether the processor is currently loaded.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetcurrentprocessorcounts">NdisGetCurrentProcessorCounts</a>

