---
UID: NS:ntddrilapitypes.RILPOSITIONINFOGSM
title: RILPOSITIONINFOGSM (ntddrilapitypes.h)
description: This structure represents RILPOSITIONINFOGSM.
old-location: netvista\rilpositioninfogsm.htm
tech.root: netvista
ms.assetid: 86b0510b-54ed-463e-b5d4-a34b0a98c00e
ms.date: 02/16/2018
ms.keywords: "*LPRILPOSITIONINFOGSM, RILPOSITIONINFOGSM, RILPOSITIONINFOGSM structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfogsm, rilapitypes/RILPOSITIONINFOGSM"
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
- RILPOSITIONINFOGSM
product:
- Windows
targetos: Windows
req.typenames: RILPOSITIONINFOGSM, *LPRILPOSITIONINFOGSM
---

# RILPOSITIONINFOGSM structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILPOSITIONINFOGSM.


## -syntax


```cpp
struct RILPOSITIONINFOGSM {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwTimingAdvance;
  DWORD dwARFCN;
  DWORD dwBaseStationID;
  DWORD dwRxLevel;
};
```


## -struct-fields




### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilpositioninfogsmparammask.md">RILPOSITIONINFOGSMPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwMobileCountryCode

Mobile country code (0...999)


### -field dwMobileNetworkCode

Mobile Network Code (0...999)


### -field dwLocationAreaCode

Location Area Code (0…65535)


### -field dwCellID

Cell ID (0...65535)


### -field dwTimingAdvance

Timing Advance (0...255) in bit periods, where a bit period is 48/13µs


### -field dwARFCN

Absolute radio frequency channel number of serving cell (0...1023)


### -field dwBaseStationID

Radio base station ID of serving cell (0..63)


### -field dwRxLevel

Received signal strength of serving cell (0...63) where:

(x=0, RSS < -110dBm

x=63, RSS > -49dBm

0 <x <63, -110+x < RSS < -109+x)


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


