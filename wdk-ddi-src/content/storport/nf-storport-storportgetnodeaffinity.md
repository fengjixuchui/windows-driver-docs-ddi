---
UID: NF:storport.StorPortGetNodeAffinity
title: StorPortGetNodeAffinity function (storport.h)
description: The StorPortGetNodeAffinity routine constructs a mask of the active processors in a requested non-uniform memory access (NUMA) node.
old-location: storage\storportgetnodeaffinity.htm
tech.root: storage
ms.assetid: 183940c9-f8d9-411f-a593-e283f72e05f8
ms.date: 03/29/2018
keywords: ["StorPortGetNodeAffinity function"]
ms.keywords: StorPortGetNodeAffinity, StorPortGetNodeAffinity routine [Storage Devices], storage.storportgetnodeaffinity, storport/StorPortGetNodeAffinity, storprt_fdd62c09-d9ce-49cd-b390-c7c9a76a098f.xml
f1_keywords:
 - "storport/StorPortGetNodeAffinity"
 - "StorPortGetNodeAffinity"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortGetNodeAffinity
targetos: Windows
req.typenames: 
---

# StorPortGetNodeAffinity function


## -description


The <b>StorPortGetNodeAffinity</b> routine constructs a mask of the active processors in a requested non-uniform memory access (NUMA) node.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param NodeNumber [in]

The NUMA node from which to return the processor mask.


### -param NodeAffinityMask [out]

A pointer to a variable that holds the affinity mask of the given node.


## -returns



The <b>StorPortGetNodeAffinity</b>routine returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>NodeAffinityMask</i> is set to <b>NULL</b>, or if <i>NodeNumber</i> is greater than 65,535.

</td>
</tr>
</table>
 



