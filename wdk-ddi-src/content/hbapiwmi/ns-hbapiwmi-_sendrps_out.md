---
UID: NS:hbapiwmi._SendRPS_OUT
title: _SendRPS_OUT (hbapiwmi.h)
description: The SendRPS_OUT structure is used to report the output parameter data of the SendRPS WMI method to the WMI client.
old-location: storage\sendrps_out.htm
tech.root: storage
ms.assetid: 5d243704-7424-4738-b122-6b9467eb5916
ms.date: 03/29/2018
keywords: ["SendRPS_OUT structure"]
ms.keywords: "*PSendRPS_OUT, SendRPS_OUT, SendRPS_OUT structure [Storage Devices], _SendRPS_OUT, hbapiwmi/SendRPS_OUT, storage.sendrps_out, structs-Fibre_0c81817b-666f-4b2b-8ae2-2342894d7c46.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
targetos: Windows
req.typenames: SendRPS_OUT, *PSendRPS_OUT
f1_keywords:
 - _SendRPS_OUT
 - hbapiwmi/_SendRPS_OUT
 - PSendRPS_OUT
 - hbapiwmi/PSendRPS_OUT
 - SendRPS_OUT
 - hbapiwmi/SendRPS_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SendRPS_OUT
---

# _SendRPS_OUT structure


## -description

The SendRPS_OUT structure is used to report the output parameter data of the <a href="/windows-hardware/drivers/storage/sendrps">SendRPS</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field TotalRspBufferSize

Contains the size in bytes of the results of the RPS command.

### -field ActualRspBufferSize

Contains the size in bytes of the data that was actually retrieved.

### -field RspBuffer

Contains the results of the RPS command.

## -remarks

The WMI tool suite generates a declaration of the SendRPS_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/sendrps">SendRPS</a>