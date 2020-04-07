---
UID: NS:mpiodisk._DSM_QueryLBPolicy_V2
title: _DSM_QueryLBPolicy_V2 (mpiodisk.h)
description: The DSM_QueryLBPolicy_V2 structure is used to query a LUN's current load balance policy. It is basically the same as the DSM_QueryLBPolicy structure except that it returns the load balance information by using the DSM_Load_Balance_Policy_V2 structure.
old-location: storage\dsm_querylbpolicy_v2.htm
tech.root: storage
ms.assetid: f02f3442-e9c2-4f60-833d-e470de62118e
ms.date: 03/29/2018
keywords: ["_DSM_QueryLBPolicy_V2 structure"]
ms.keywords: "*PDSM_QueryLBPolicy_V2, DSM_QueryLBPolicy_V2, DSM_QueryLBPolicy_V2 structure [Storage Devices], PDSM_QueryLBPolicy_V2, PDSM_QueryLBPolicy_V2 structure pointer [Storage Devices], _DSM_QueryLBPolicy_V2, mpiodisk/DSM_QueryLBPolicy_V2, mpiodisk/PDSM_QueryLBPolicy_V2, storage.dsm_querylbpolicy_v2, structs-scsibus_ea429f47-a439-433a-962e-2ce334aa7498.xml"
f1_keywords:
 - "mpiodisk/DSM_QueryLBPolicy_V2"
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- mpiodisk.h
api_name:
- DSM_QueryLBPolicy_V2
product:
- Windows
targetos: Windows
req.typenames: DSM_QueryLBPolicy_V2, *PDSM_QueryLBPolicy_V2
---

# _DSM_QueryLBPolicy_V2 structure


## -description


The DSM_QueryLBPolicy_V2 structure is used to query a LUN's current load balance policy. It is basically the same as the DSM_QueryLBPolicy structure except that it returns the load balance information by using the DSM_Load_Balance_Policy_V2 structure.


## -struct-fields




### -field LoadBalancePolicy

An instance of the DSM_Load_Balance_Policy_V2 structure that has information about the current load balance policy that is being applied by the DSM on the targeted pseudo-LUN.

