---
UID: NS:ntddrilapitypes.RILADDRESS
title: RILADDRESS (ntddrilapitypes.h)
description: This structure represents a phone number.
old-location: netvista\riladdress.htm
tech.root: netvista
ms.assetid: d329069d-5455-4c37-b190-02a7bd1e789a
ms.date: 02/16/2018
keywords: ["RILADDRESS structure"]
ms.keywords: "*LPRILADDRESS, RILADDRESS, RILADDRESS structure [Network Drivers Starting with Windows Vista], netvista.riladdress, rilapitypes/RILADDRESS"
f1_keywords:
 - "ntddrilapitypes/RILADDRESS"
 - "RILADDRESS"
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
- RILADDRESS
targetos: Windows
req.typenames: RILADDRESS, *LPRILADDRESS
---

# RILADDRESS structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a phone number.


## -syntax


```cpp
struct RILADDRESS {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwType;
  DWORD dwNumPlan;
  WCHAR wszAddress[MAXLENGTH_ADDRESS];
};
```


## -struct-fields




### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riladdressparammask.md">RILADDRESSPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwType

The type of address. Possible values are shown in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
RIL_ADDRTYPE_UNKNOWN

</td>
<td>
Unknown type

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_INTERNATIONAL

</td>
<td>
International number

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_NATIONAL

</td>
<td>
National/regional number

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_NETWKSPECIFIC

</td>
<td>
Network-specific number

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_SUBSCRIBER

</td>
<td>
Subscriber number (protocol-specific)

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_ALPHANUM

</td>
<td>
Alphanumeric address

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_ABBREV

</td>
<td>
Abbreviated number

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_IP

</td>
<td>
IP address

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_EMAIL

</td>
<td>
Internet email address (RFC 822)

</td>
</tr>
</table>
 


### -field dwNumPlan

The numbering scheme of the address. Possible values are shown in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
RIL_NUMPLAN_UNKNOWN

</td>
<td>
Unknown numbering plan

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_TELEPHONE

</td>
<td>
ISDN/telephone numbering plan (E.164/E.163)

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_DATA

</td>
<td>
Data numbering plan (X.121)

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_TELEX

</td>
<td>
Telex numbering plan

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_NATIONAL

</td>
<td>
National/regional numbering plan

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_PRIVATE

</td>
<td>
Private numbering plan

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_ERMES

</td>
<td>
ERMES numbering plan (ETSI DE/PS 3 01-3)

</td>
</tr>
</table>
 


### -field wszAddress

An array of address characters. The minimum length of this array is 3. When <b>dwType</b> is set to <b>RIL_ADDRTYPE_INTERNATIONAL</b>, the plus sign (+) is not prefixed to <b>wszAddress</b>. It is up to the client or modem to attach the symbol.


## -remarks



When a <b>RILADDRESS</b> represents a phone number on a UICC card, the contents of <b>wszAddress</b> are constrained to values that can be represented on the card (as defined by 3GPP TS 31.102 table 4.4). In the UICC file, a phone number is represented by a string of 4-bit nibbles padded on the right with 0xF. The defined mapping is shown in the following table.

<table>
<tr>
<th>nibble in UICC EF</th>
<th>WCHAR in wszAddress</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0x0

</td>
<td>
L'0'

</td>
<td>
Digit 0

</td>
</tr>
<tr>
<td>
0x1

</td>
<td>
L'1'

</td>
<td>
Digit 1

</td>
</tr>
<tr>
<td>
0x2

</td>
<td>
L'2'

</td>
<td>
Digit 2

</td>
</tr>
<tr>
<td>
0x3

</td>
<td>
L'3'

</td>
<td>
Digit 3

</td>
</tr>
<tr>
<td>
0x4

</td>
<td>
L'4'

</td>
<td>
Digit 4

</td>
</tr>
<tr>
<td>
0x5

</td>
<td>
L'5'

</td>
<td>
Digit 5

</td>
</tr>
<tr>
<td>
0x6

</td>
<td>
L'6'

</td>
<td>
Digit 6

</td>
</tr>
<tr>
<td>
0x7

</td>
<td>
L'7'

</td>
<td>
Digit 7

</td>
</tr>
<tr>
<td>
0x8

</td>
<td>
L'8'

</td>
<td>
Digit 8

</td>
</tr>
<tr>
<td>
0x9

</td>
<td>
L'9'

</td>
<td>
Digit 9

</td>
</tr>
<tr>
<td>
0xA

</td>
<td>
L'*'

</td>
<td>
Asterisk character

</td>
</tr>
<tr>
<td>
0xB

</td>
<td>
L'#'

</td>
<td>
Pound character

</td>
</tr>
<tr>
<td>
0xC

</td>
<td>
L'p' or L'P'

</td>
<td>
DTMF control digits separator (see 3GPP TS 22.101)

</td>
</tr>
<tr>
<td>
0xD

</td>
<td>
L'?'

</td>
<td>
"Wild" value (see 3GPP TS 22.101)

</td>
</tr>
<tr>
<td>
0xE

</td>
<td>


</td>
<td>
RFU—not to be used

</td>
</tr>
<tr>
<td>
0xF

</td>
<td>


</td>
<td>
Padding for unused nibbles on UICC card—not to be used

</td>
</tr>
</table>
 

In the case of the control digits separator, either uppercase or lowercase 'P' may be passed in; the output is always lowercase. The RFU value 0xE should never appear on the card, but if it does it is reported as L'e'. It is an error to pass L'e' as input.




## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


