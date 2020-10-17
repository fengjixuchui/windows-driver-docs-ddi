---
UID: NF:ks.KsMergeAutomationTables
title: KsMergeAutomationTables function (ks.h)
description: The KsMergeAutomationTables function merges two automation tables.
old-location: stream\ksmergeautomationtables.htm
tech.root: stream
ms.assetid: ef90f9da-3169-4b49-9ba2-2cab058e5d00
ms.date: 04/23/2018
keywords: ["KsMergeAutomationTables function"]
ms.keywords: KsMergeAutomationTables, KsMergeAutomationTables function [Streaming Media Devices], avfunc_7e2146e2-0458-48ee-815a-8ea478187e07.xml, ks/KsMergeAutomationTables, stream.ksmergeautomationtables
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsMergeAutomationTables
 - ks/KsMergeAutomationTables
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsMergeAutomationTables
---

# KsMergeAutomationTables function


## -description

The<b> KsMergeAutomationTables</b> function merges two automation tables.

## -parameters

### -param AutomationTableAB 

[out]
A pointer to the location at which a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksautomation_table_">KSAUTOMATION_TABLE</a> is deposited. This structure is the resulting merged automation table.

### -param AutomationTableA 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksautomation_table_">KSAUTOMATION_TABLE</a> structure representing the first of the two automation tables to merge. This table is the dominant table with respect to duplicate entries. If <b>NULL</b>, <i>AutomationTableB</i> is copied into <i>AutomationTableAB</i> and optionally placed in <i>Bag</i>.

### -param AutomationTableB 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksautomation_table_">KSAUTOMATION_TABLE</a> structure representing the second of the two automation tables to merge. If <b>NULL</b>, <i>AutomationTableA</i> is copied into <i>AutomationTableAB</i> and optionally placed in <i>Bag</i>.

### -param Bag 

[in, optional]
The newly created automation table is placed in this KSOBJECT_BAG (equivalent to type PVOID) for later clean up. This parameter is optional.

## -returns

<b>KsMergeAutomationTables</b> returns STATUS_SUCCESS if the merge successfully completes. If unsuccessful, it returns an error code. The most frequent error code is STATUS_INSUFFICIENT_RESOURCES, which indicates that there are insufficient system resources to complete the merge.

## -remarks

If both <i>AutomationTableA</i> and <i>AutomationTableB</i> are <b>NULL</b>, this routine performs no action and returns STATUS_SUCCESS.

The entries in<i> AutomationTableA</i> have priority in the merge<i>.</i> If there is an entry that appears in both <i>AutomationTableA </i>and <i>AutomationTableB</i>, the entry in <i>AutomationTableA</i> is the one that is placed into the merged table. The newly created automation table is placed in the requested object bag if one is provided.

If an input table is in an object bag at call-time, <i>AVStream removes the table from the object bag</i> before <b>KsMergeAutomationTables</b> returns.

If the <i>Bag</i> parameter is not <b>NULL</b>, the minidriver should take the mutex associated with the object bag prior to calling this routine. If the bag is associated with a pin or a filter, then the control mutex must be held. If the bag is associated with a filter factory or a device, then the device mutex should be held. For more information, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

Also see <a href="/windows-hardware/drivers/stream/object-bags">Object Bags</a>  and <a href="/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksadditemtoobjectbag">KsAddItemToObjectBag</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscopyobjectbagitems">KsCopyObjectBagItems</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksremoveitemfromobjectbag">KsRemoveItemFromObjectBag</a>