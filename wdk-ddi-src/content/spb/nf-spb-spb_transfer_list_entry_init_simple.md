---
UID: NF:spb.SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE
title: SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function (spb.h)
description: The SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer.SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer.
old-location: spb\spb_transfer_list_entry_init_simple.htm
tech.root: SPB
ms.assetid: 38F50F76-5D14-47CE-A211-3FC4F1399A74
ms.date: 04/30/2018
keywords: ["SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function"]
ms.keywords: SPB.spb_transfer_list_entry_init_simple, SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE, SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function [Buses], spb/SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE
req.header: spb.h
req.include-header: 
req.target-type: Desktop
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
req.irql: Any IRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE
 - spb/SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE
---

# SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function


## -description

The <b>SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</b> function returns an <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry">SPB_TRANSFER_LIST_ENTRY</a> structure that is initialized to describe a simple data buffer.

## -parameters

### -param Direction 

[in]
The direction of the transfer. The function writes this value to the <b>Direction</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

### -param DelayInUs 

[in]
An optional delay in microseconds. The function writes this value to the <b>DelayInUs</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

### -param Buffer 

[in]
A pointer to a data buffer. The function writes this value to the <b>Buffer.Simple.Buffer</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>Buffer</b> member in <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer_list_entry">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>.

### -param BufferCb 

[in]
The size, in bytes, of the buffer pointed to by <i>Buffer</i>. The function writes this value to the <b>Buffer.Simple.BufferCb</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>BufferCb</b> member in <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer_list_entry">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>.

## -returns

<b>SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</b> returns an initialized <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

## -remarks

This initialization function returns an unnamed local variable of type <b>SPB_TRANSFER_LIST_ENTRY</b>. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.

<b>SPB_MDL_TRANSFER_ENTRY</b> sets the <b>Buffer.Format</b> member of the  <b>SPB_TRANSFER_LIST_ENTRY</b> structure to <b>SpbTransferBufferFormatSimple</b>. For more information about buffer formats, see <a href="/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_buffer_format">SPB_TRANSFER_BUFFER_FORMAT</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_buffer_format">SPB_TRANSFER_BUFFER_FORMAT</a>



<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer_list_entry">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry">SPB_TRANSFER_LIST_ENTRY</a>