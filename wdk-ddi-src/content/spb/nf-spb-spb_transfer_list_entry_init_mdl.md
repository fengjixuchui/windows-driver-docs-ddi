---
UID: NF:spb.SPB_TRANSFER_LIST_ENTRY_INIT_MDL
title: SPB_TRANSFER_LIST_ENTRY_INIT_MDL function (spb.h)
description: The SPB_TRANSFER_LIST_ENTRY_INIT_MDL function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to use an MDL to describe a data buffer.
old-location: spb\spb_transfer_list_entry_init_mdl.htm
tech.root: SPB
ms.assetid: FFE8761B-5769-48E5-ACE9-50009C490714
ms.date: 04/30/2018
ms.keywords: SPB.spb_transfer_list_entry_init_mdl, SPB_TRANSFER_LIST_ENTRY_INIT_MDL, SPB_TRANSFER_LIST_ENTRY_INIT_MDL function [Buses], spb/SPB_TRANSFER_LIST_ENTRY_INIT_MDL
ms.topic: function
f1_keywords:
 - "spb/SPB_TRANSFER_LIST_ENTRY_INIT_MDL"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Spb.h
api_name:
- SPB_TRANSFER_LIST_ENTRY_INIT_MDL
product:
- Windows
targetos: Windows
req.typenames: 
---

# SPB_TRANSFER_LIST_ENTRY_INIT_MDL function


## -description


The <b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> function returns an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry">SPB_TRANSFER_LIST_ENTRY</a> structure that is initialized to use an MDL to describe a data buffer.


## -parameters




### -param Direction [in]

The direction of the transfer. The function writes this value to the <b>Direction</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.


### -param DelayInUs [in]

An optional delay in microseconds. The function writes this value to the <b>DelayInUs</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.


### -param Mdl [in]

A pointer to an MDL that describes a data buffer. The function writes this value to the <b>Buffer.Mdl</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>Mdl</b> member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer">SPB_TRANSFER_BUFFER</a>.


## -returns



<b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> returns an initialized <b>SPB_TRANSFER_LIST_ENTRY</b> structure.




## -remarks



This initialization function returns an unnamed local variable of type <b>SPB_TRANSFER_LIST_ENTRY</b>. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.

<b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> sets the <b>Buffer.Format</b> member of the  <b>SPB_TRANSFER_LIST_ENTRY</b> structure to <b>SpbTransferBufferFormatMdl</b>. For more information about buffer formats, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_buffer_format">SPB_TRANSFER_BUFFER_FORMAT</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer">SPB_TRANSFER_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_buffer_format">SPB_TRANSFER_BUFFER_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry">SPB_TRANSFER_LIST_ENTRY</a>
 

 

