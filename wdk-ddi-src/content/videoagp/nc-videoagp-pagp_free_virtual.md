---
UID: NC:videoagp.PAGP_FREE_VIRTUAL
title: PAGP_FREE_VIRTUAL (videoagp.h)
description: The AgpFreeVirtual function frees virtual memory committed by a previous call to AgpCommitVirtual.
old-location: display\agpfreevirtual.htm
tech.root: display
ms.assetid: a6f689ab-8cf1-4207-af2b-30957500c190
ms.date: 05/10/2018
keywords: ["PAGP_FREE_VIRTUAL callback function"]
ms.keywords: AgpFreeVirtual, AgpFreeVirtual callback function [Display Devices], PAGP_FREE_VIRTUAL, PAGP_FREE_VIRTUAL callback, VideoPort_Functions_49eabd30-2590-466f-b9d4-f2577a7e78e4.xml, display.agpfreevirtual, videoagp/AgpFreeVirtual
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
 - PAGP_FREE_VIRTUAL
 - videoagp/PAGP_FREE_VIRTUAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - videoagp.h
api_name:
 - AgpFreeVirtual
---

# PAGP_FREE_VIRTUAL callback function


## -description

The <b>AgpFreeVirtual</b> function frees virtual memory committed by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a>.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param VirtualReserveContext 

[in]
Identifies a reserved virtual address range. This context handle was obtained from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a>.

### -param Pages 

[in]
Specifies the number of pages of virtual memory that the video port driver should unmap.

### -param Offset 

[in]
Specifies the page offset into the reserved virtual address range identified by <b>VirtualReserveContext</b> that indicates the actual base address at which to unmap virtual memory.

## -remarks

When a miniport driver calls <b>AgpFreeVirtual</b>, <i>Pages</i> pages of virtual addresses are unmapped. The unmapped range begins <b>Offset</b> pages into the range associated with <b>VirtualReserveContext</b>. The miniport driver must specify that the exact offset and number of pages be freed as were committed in a prior call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a>. 

A call to <b>AgpFreeVirtual</b> must be paired with a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a>, and that call to <b>AgpCommitVirtual</b> must be preceded by a successful call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a>. If <b>AgpReserveVirtual</b> fails (returns <b>NULL</b>), you must not call <b>AgpCommitVirtual</b> or <b>AgpFreeVirtual</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a>

