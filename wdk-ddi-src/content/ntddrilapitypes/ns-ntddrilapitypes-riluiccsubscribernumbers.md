---
UID: NS:ntddrilapitypes.RILUICCSUBSCRIBERNUMBERS
title: RILUICCSUBSCRIBERNUMBERS (ntddrilapitypes.h)
description: This structure represents RILUICCSUBSCRIBERNUMBERS.
old-location: netvista\riluiccsubscribernumbers.htm
tech.root: netvista
ms.assetid: 7c9f7c52-edb3-48cd-b532-0e100692fee4
ms.date: 02/16/2018
ms.keywords: "*LPRILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS structure [Network Drivers Starting with Windows Vista], netvista.riluiccsubscribernumbers, rilapitypes/RILUMTSMRL"
ms.topic: struct
f1_keywords:
 - "ntddrilapitypes/RILUMTSMRL"
req.header: ntddrilapitypes.h
req.include-header: Ntddrilapitypes.h
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
- rilapitypes.h
api_name:
- RILUMTSMRL
product:
- Windows
targetos: Windows
req.typenames: RILUICCSUBSCRIBERNUMBERS, *LPRILUICCSUBSCRIBERNUMBERS
---

# RILUICCSUBSCRIBERNUMBERS structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILUICCSUBSCRIBERNUMBERS.


## -syntax


```cpp
struct RILUMTSMRL {
  DWORD             cbSize;
  DWORD             dwNumSubscribers;
  RILSUBSCRIBERINFO rsiInfo[1];
};
```


## -struct-fields




### -field cbSize

The size of the structure in bytes.


### -field dwNumSubscribers

The number of subscribers.


### -field rsiInfo

Array of <a href="..\rilapitypes\ns-rilapitypes-rilsubscriberinfo.md">RILSUBSCRIBERINFO</a>, each of which specifies a phone number assigned to the user as defined below. Although statically declared as a one-element array, the actual length is dwNumSubscribers.


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


