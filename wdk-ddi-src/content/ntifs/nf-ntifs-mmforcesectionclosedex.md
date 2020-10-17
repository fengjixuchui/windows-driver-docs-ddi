---
UID: NF:ntifs.MmForceSectionClosedEx
title: MmForceSectionClosedEx function (ntifs.h)
description: The MmForceSectionClosedEx function examines the section object pointers.  If they are NULL, no further action is taken and the value TRUE is returned.
ms.assetid: a33c8323-40ea-4606-bec1-68b955e01c8f
tech.root: ifsk
ms.date: 10/19/2018
keywords: ["MmForceSectionClosedEx function"]
ms.keywords: MmForceSectionClosedEx
req.header: ntifs.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - MmForceSectionClosedEx
 - ntifs/MmForceSectionClosedEx
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmForceSectionClosedEx
---

# MmForceSectionClosedEx function


## -description

The MmForceSectionClosedEx function examines the section object pointers.  If they are NULL, no further action is taken and the value TRUE is returned.

If the section object pointer is not NULL, the section reference count and the map view count are checked.  If both counts are zero, the segment associated with the file is deleted and the file closed. If one of the counts is non-zero, no action is taken and the value FALSE is returned.

## -parameters

### -param SectionObjectPointer

Specifies a pointer to the [SECTION_OBJECT_POINTERS](../wdm/ns-wdm-_section_object_pointers.md) object.

### -param ForceCloseFlags

Contains flags that indicate if the section should  be marked for closing later (as soon as possible) in the event this section cannot be closed now due to outstanding references.

Contains one of the following flags:

* MM_FORCE_CLOSED_LATER_OK if the section should be marked for immediate closing in the event that the section cannot be closed due to outstanding references.

* MM_FORCE_CLOSED_DATA to force data section closure.

* MM_FORCE_CLOSED_IMAGE to force image section closure.

## -returns

This function returns TRUE if the segment was deleted and the file closed or no segment was located.  If more than one segment type is specified (data/image) then they must both be successfully deleted for TRUE to be returned.

This function returns FALSE if the segment was not deleted.

## -remarks

## -see-also