---
UID: NS:hbapiwmi._SendRPL_OUT
title: _SendRPL_OUT (hbapiwmi.h)
description: The SendRPL_OUT structure is used to report the output parameter data of the SendRPL WMI method to the WMI client.
old-location: storage\sendrpl_out.htm
tech.root: storage
ms.assetid: 36ca3d6e-7012-4bbb-a2a0-e19708aa1058
ms.date: 03/29/2018
keywords: ["SendRPL_OUT structure"]
ms.keywords: "*PSendRPL_OUT, PSendRPL_OUT, PSendRPL_OUT structure pointer [Storage Devices], SendRPL_OUT, SendRPL_OUT structure [Storage Devices], _SendRPL_OUT, hbapiwmi/PSendRPL_OUT, hbapiwmi/SendRPL_OUT, storage.sendrpl_out, structs-Fibre_aef41c84-1718-4e82-aeae-d0280d6cf3b1.xml"
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
req.typenames: SendRPL_OUT, *PSendRPL_OUT
f1_keywords:
 - _SendRPL_OUT
 - hbapiwmi/_SendRPL_OUT
 - PSendRPL_OUT
 - hbapiwmi/PSendRPL_OUT
 - SendRPL_OUT
 - hbapiwmi/SendRPL_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SendRPL_OUT
---

# _SendRPL_OUT structure


## -description

The SendRPL_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendrpl">SendRPL</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field TotalRspBufferSize

Contains the size in bytes of the results of the read port list (RPL) command.

### -field ActualRspBufferSize

Contains the size in bytes of the data that was actually retrieved.

### -field RspBuffer

Contains the results of the read port list (RPL) command.

## -remarks

The WMI tool suite generates a declaration of the SendRPL_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendrpl">SendRPL</a>

