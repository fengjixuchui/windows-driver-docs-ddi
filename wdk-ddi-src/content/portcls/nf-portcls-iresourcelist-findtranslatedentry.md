---
UID: NF:portcls.IResourceList.FindTranslatedEntry
title: IResourceList::FindTranslatedEntry (portcls.h)
description: The FindTranslatedEntry method returns a pointer to a translated entry of the specified type, or NULL if no such entry is found.
old-location: audio\iresourcelist_findtranslatedentry.htm
tech.root: audio
ms.assetid: b3e8ae4d-a923-406e-ad1a-f7ed7277f676
ms.date: 05/08/2018
keywords: ["IResourceList::FindTranslatedEntry"]
ms.keywords: FindTranslatedEntry, FindTranslatedEntry method [Audio Devices], FindTranslatedEntry method [Audio Devices],IResourceList interface, IResourceList interface [Audio Devices],FindTranslatedEntry method, IResourceList.FindTranslatedEntry, IResourceList::FindTranslatedEntry, audio.iresourcelist_findtranslatedentry, audmp-routines_a4100c1c-8955-46bb-a9cc-8cee22609598.xml, portcls/IResourceList::FindTranslatedEntry
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IResourceList::FindTranslatedEntry
 - portcls/IResourceList::FindTranslatedEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IResourceList.FindTranslatedEntry
---

# IResourceList::FindTranslatedEntry


## -description

The <code>FindTranslatedEntry</code> method returns a pointer to a translated entry of the specified type, or <b>NULL</b> if no such entry is found.

## -parameters

### -param Type 

[in]
Identifies the resource type of the entry to find. For a list of valid resource-type values, see the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.

### -param Index 

[in]
Specifies the index of the entry to find. If the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method returns a pointer to the translated version of the first occurrence of an entry of the specified type from the resource list.

## -returns

<code>FindTranslatedEntry</code> returns a pointer to the specified entry or is <b>NULL</b> if the entry does not exist. This pointer remains valid until the resource list object is deleted.

## -remarks

For each resource type, a macro is defined to call this method. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>.

The <i>Index</i> parameter indicates which occurrence of an entry of the specified type to find in the list of translated resource entries. The first occurrence in the list has an index of zero.

For each resource type, a macro is defined to call this method. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>.

For more information about translated and untranslated (or "raw") resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-finduntranslatedentry">IResourceList::FindUntranslatedEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a>

