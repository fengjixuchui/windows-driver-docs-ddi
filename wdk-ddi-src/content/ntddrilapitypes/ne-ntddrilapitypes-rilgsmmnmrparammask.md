---
UID: NE:ntddrilapitypes.RILGSMMNMRPARAMMASK
title: RILGSMMNMRPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILGSMMNMRPARAMMASK.
old-location: netvista\rilgsmmnmrparammask.htm
tech.root: netvista
ms.assetid: a226956d-2881-4cff-a800-988b70eb99ea
ms.date: 02/16/2018
ms.keywords: RILGSMMNMRPARAMMASK, RILGSMMNMRPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_GSMNMR_ALL, RIL_PARAM_GSMNMR_ARFCN, RIL_PARAM_GSMNMR_BSID, RIL_PARAM_GSMNMR_CELLID, RIL_PARAM_GSMNMR_LAC, RIL_PARAM_GSMNMR_MCC, RIL_PARAM_GSMNMR_MNC, RIL_PARAM_GSMNMR_RXLEVEL, netvista.rilgsmmnmrparammask, rilapitypes/RILGSMMNMRPARAMMASK, rilapitypes/RIL_PARAM_GSMNMR_ALL, rilapitypes/RIL_PARAM_GSMNMR_ARFCN, rilapitypes/RIL_PARAM_GSMNMR_BSID, rilapitypes/RIL_PARAM_GSMNMR_CELLID, rilapitypes/RIL_PARAM_GSMNMR_LAC, rilapitypes/RIL_PARAM_GSMNMR_MCC, rilapitypes/RIL_PARAM_GSMNMR_MNC, rilapitypes/RIL_PARAM_GSMNMR_RXLEVEL
ms.topic: enum
f1_keywords:
 - "ntddrilapitypes/RILGSMMNMRPARAMMASK"
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
- RILGSMMNMRPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILGSMMNMRPARAMMASK
---

# RILGSMMNMRPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILGSMMNMRPARAMMASK.




## -syntax


```cpp
enum RILGSMMNMRPARAMMASK {
  RIL_PARAM_GSMNMR_MCC      = 0x00000001,
  RIL_PARAM_GSMNMR_MNC      = 0x00000002,
  RIL_PARAM_GSMNMR_LAC      = 0x00000004,
  RIL_PARAM_GSMNMR_CELLID   = 0x00000008,
  RIL_PARAM_GSMNMR_ARFCN    = 0x00000010,
  RIL_PARAM_GSMNMR_BSID     = 0x00000020,
  RIL_PARAM_GSMNMR_RXLEVEL  = 0x00000040,
  RIL_PARAM_GSMNMR_ALL      = 0x0000007f

};
```


## -enum-fields




### -field RIL_PARAM_GSMNMR_MCC


### -field RIL_PARAM_GSMNMR_MNC


### -field RIL_PARAM_GSMNMR_LAC


### -field RIL_PARAM_GSMNMR_CELLID


### -field RIL_PARAM_GSMNMR_ARFCN


### -field RIL_PARAM_GSMNMR_BSID


### -field RIL_PARAM_GSMNMR_RXLEVEL


### -field RIL_PARAM_GSMNMR_ALL


## -remarks



In most situations both serving and neighbor cell sites will return all of these values.

<b>Serving network</b>

<table>
<tr>
<th>Entry</th>
<th>Typically returned?</th>
<th>Range</th>
<th>Comment</th>
</tr>
<tr>
<td>
MobileCountryCode

</td>
<td>
Yes

</td>
<td>
0 through 999

</td>
<td>


</td>
</tr>
<tr>
<td>
MobileNetworkCode

</td>
<td>
Yes

</td>
<td>
0 through 999

</td>
<td>


</td>
</tr>
<tr>
<td>
LocationAreaCode

</td>
<td>
Yes

</td>
<td>
0 through 65,535

</td>
<td>


</td>
</tr>
<tr>
<td>
CellID

</td>
<td>
Yes

</td>
<td>
0 through 268,435,455

</td>
<td>
28 bits; may not always be available

</td>
</tr>
<tr>
<td>
ARFCN

</td>
<td>
Yes

</td>
<td>
0 through 1,023

</td>
<td>
Absolute RF channel number

</td>
</tr>
<tr>
<td>
BaseStationID

</td>
<td>
Yes

</td>
<td>
0 through 63

</td>
<td>
Base station identity code ID (BSIC ID), including bcc and ncc;  lower 6 bits can be set to any value

</td>
</tr>
<tr>
<td>
RxLevel

</td>
<td>
Yes

</td>
<td>
0 through 63

</td>
<td>
Serving cell Rx measurement; range is mapped to a measured signal level:

• RxLevel 0 is a signal strength less than −110 dBm

• RxLevel 1 is −110 dBm to −109 dBm

• RxLevel 2 is −109 dBm to −108 dBm

• ...

• RxLevel 62 is −49 dBm to −48 dBm

• RxLevel 63 is greater than −48 dBm

</td>
</tr>
</table>
 

<b>GSM neighbors</b> (subject to availability from network)

<table>
<tr>
<th>Entry</th>
<th>Typically returned?</th>
<th>Range</th>
<th>Comment</th>
</tr>
<tr>
<td>
MobileCountryCode

</td>
<td>
Yes

</td>
<td>
0 through 999

</td>
<td>


</td>
</tr>
<tr>
<td>
MobileNetworkCode

</td>
<td>
Yes

</td>
<td>
0 through 999

</td>
<td>


</td>
</tr>
<tr>
<td>
LocationAreaCode

</td>
<td>
Yes

</td>
<td>
0 through 65,535

</td>
<td>


</td>
</tr>
<tr>
<td>
CellID

</td>
<td>
Yes

</td>
<td>
0 through 268,435,455

</td>
<td>
May not be available always; MCC/MNC/LAC should be ignored if Cell ID is not valid

</td>
</tr>
<tr>
<td>
ARFCN

</td>
<td>
Yes

</td>
<td>
0 through 1,023

</td>
<td>


</td>
</tr>
<tr>
<td>
BaseStationID

</td>
<td>
Yes

</td>
<td>
0 through 63

</td>
<td>
Base station identity code is not available for neighbor cells at all times; it can be set to an invalid number

</td>
</tr>
<tr>
<td>
RxLevel

</td>
<td>
Yes

</td>
<td>
0 through 63

</td>
<td>
Same as RxLevel in serving cell

</td>
</tr>
</table>
 




## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>



 

 


