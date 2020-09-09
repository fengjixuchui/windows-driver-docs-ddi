---
UID: NS:ntpoapi._COUNTED_REASON_CONTEXT
title: _COUNTED_REASON_CONTEXT (ntpoapi.h)
description: The COUNTED_REASON_CONTEXT structure contains one or more strings that give reasons for a power request.
old-location: kernel\counted_reason_context.htm
tech.root: kernel
ms.assetid: beb17d50-d99a-4baf-99bd-9f42fbea0478
ms.date: 04/30/2018
keywords: ["COUNTED_REASON_CONTEXT structure"]
ms.keywords: "*PCOUNTED_REASON_CONTEXT, COUNTED_REASON_CONTEXT, COUNTED_REASON_CONTEXT structure [Kernel-Mode Driver Architecture], PCOUNTED_REASON_CONTEXT, PCOUNTED_REASON_CONTEXT structure pointer [Kernel-Mode Driver Architecture], _COUNTED_REASON_CONTEXT, kernel.counted_reason_context, kstruct_a_52baf683-dfd2-4004-abed-e9ae6221c342.xml, wdm/COUNTED_REASON_CONTEXT, wdm/PCOUNTED_REASON_CONTEXT"
req.header: ntpoapi.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ntpoapi.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
targetos: Windows
req.typenames: COUNTED_REASON_CONTEXT, *PCOUNTED_REASON_CONTEXT
f1_keywords:
 - _COUNTED_REASON_CONTEXT
 - ntpoapi/_COUNTED_REASON_CONTEXT
 - PCOUNTED_REASON_CONTEXT
 - ntpoapi/PCOUNTED_REASON_CONTEXT
 - COUNTED_REASON_CONTEXT
 - ntpoapi/COUNTED_REASON_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - COUNTED_REASON_CONTEXT
---

# _COUNTED_REASON_CONTEXT structure (ntpoapi.h)


## -description

The <b>COUNTED_REASON_CONTEXT</b> structure contains one or more strings that give reasons for a power request.

## -struct-fields

### -field Version

The version number of the structure. Set this member to DIAGNOSTIC_REASON_VERSION.

### -field Flags

Indicates whether the structure contains a simple reason string or a detailed set of reason strings. Set this member to one of the following constants:

<ul>
<li>
DIAGNOSTIC_REASON_SIMPLE_STRING

</li>
<li>
DIAGNOSTIC_REASON_DETAILED_STRING

</li>
</ul>
If <b>Flags</b> = DIAGNOSTIC_REASON_SIMPLE_STRING, the <b>SimpleString</b> member of the union is valid. If <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING, the <b>ResourceFileName</b>, <b>ResourceReasonId</b>, <b>StringCount</b>, and <b>ReasonStrings</b> members are valid (and the <b>SimpleString</b> member is not valid).

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ResourceFileName

A pointer to a wide-character, null-terminated string that contains the pathname of a resource file. This resource file contains one or more localized strings that give reasons for a power request. This member is optional and can be specified as <b>NULL</b> or as an empty string if no resource file is required. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING.

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ResourceReasonId

The resource ID assigned to the first reason string in the resource file that is specified by <b>ResourceFileName</b>. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING.

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.StringCount

The number of reason strings in the <b>ReasonStrings</b> array or in the resource file that is specified by <b>ResourceFileName</b>. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING.

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ReasonStrings

A pointer to an array of string pointers. Each array element is a pointer to a wide-character, null-terminated string. The number of array elements is specified by <b>StringCount</b>. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING.

### -field DUMMYUNIONNAME.SimpleString

A pointer to a wide-character, null-terminated string that explains the reason for a power request. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_SIMPLE_STRING.

## -remarks

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocreatepowerrequest">PoCreatePowerRequest</a> routine.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/power-manager">power manager</a> uses the reason string or strings contained in this structure as a diagnostic aid during functional and performance testing.

The <b>COUNTED_REASON_CONTEXT</b> structure can contain either a simple reason string or a set of detailed reason strings. If <b>Flags</b> = DIAGNOSTIC_REASON_SIMPLE_STRING, the <b>SimpleString</b> member points to a string that explains the reason for the power request. If <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING, the <b>ResourceFileName</b>, <b>ResourceReasonId</b>, <b>StringCount</b>, and <b>ReasonStrings</b> members can give a detailed set of reasons for the power request.

The DIAGNOSTIC_REASON_DETAILED_STRING flag supports localization. If the localized resource file specified by <b>ResourceFileName</b> exists, the power manager retrieves a set of resource strings from the file and uses these strings in place of the strings contained in the <b>ReasonStrings</b> array. <b>ResourceId</b> specifies the resource index of the first string in the file to use as a reason string, and <b>StringCount</b> specifies the number of resource strings to use as reason strings. The resource strings must have consecutive resource indexes.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocreatepowerrequest">PoCreatePowerRequest</a>

