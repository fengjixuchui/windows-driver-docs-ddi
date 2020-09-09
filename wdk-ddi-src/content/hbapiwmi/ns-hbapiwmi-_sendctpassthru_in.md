---
UID: NS:hbapiwmi._SendCTPassThru_IN
title: _SendCTPassThru_IN (hbapiwmi.h)
description: The SendCTPassThru_IN structure is used to deliver input parameter data to the SendCTPassThru WMI method.
old-location: storage\sendctpassthru_in.htm
tech.root: storage
ms.assetid: 5a3e06f5-f7f7-4e89-b78e-d6658c34ba9e
ms.date: 03/29/2018
keywords: ["SendCTPassThru_IN structure"]
ms.keywords: "*PSendCTPassThru_IN, PSendCTPassThru_IN, PSendCTPassThru_IN structure pointer [Storage Devices], SendCTPassThru_IN, SendCTPassThru_IN structure [Storage Devices], _SendCTPassThru_IN, hbapiwmi/PSendCTPassThru_IN, hbapiwmi/SendCTPassThru_IN, storage.sendctpassthru_in, structs-Fibre_f95be355-7a10-483c-83cb-058812977a91.xml"
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
req.typenames: SendCTPassThru_IN, *PSendCTPassThru_IN
f1_keywords:
 - _SendCTPassThru_IN
 - hbapiwmi/_SendCTPassThru_IN
 - PSendCTPassThru_IN
 - hbapiwmi/PSendCTPassThru_IN
 - SendCTPassThru_IN
 - hbapiwmi/SendCTPassThru_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SendCTPassThru_IN
---

# _SendCTPassThru_IN structure


## -description

The SendCTPassThru_IN structure is used to deliver input parameter data to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendctpassthru">SendCTPassThru</a> WMI method.

## -struct-fields

### -field PortWWN

Contains a worldwide name for the HBA through which the target is accessed.

### -field RequestBufferCount

Indicates the size in bytes of the buffer that will hold the results of the common transport command.

### -field RequestBuffer

Contains the results of the common transport command.

## -remarks

The WMI tool suite generates a declaration of the SendCTPassThru_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendctpassthru">SendCTPassThru</a>

