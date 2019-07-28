---
UID: NS:scsi.__unnamed_struct_19
title: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER (scsi.h)
description: A token, created as a representation of data (ROD), for an offload read data operation is returned in a RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure.
old-location: storage\receive_token_information_response_header.htm
tech.root: storage
ms.assetid: 54168476-1C55-4343-858C-7FBA863D35D0
ms.date: 03/29/2018
ms.keywords: "*PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure pointer [Storage Devices], RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure [Storage Devices], scsi/PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, scsi/RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, storage.receive_token_information_response_header"
ms.topic: struct
f1_keywords:
 - "scsi/RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER"
req.header: scsi.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- scsi.h
api_name:
- RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
product:
- Windows
targetos: Windows
req.typenames: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, *PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
---

# RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure


## -description


A token, created as a representation of data (ROD), for an offload read data operation is returned in a <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure.


## -struct-fields




### -field TokenDescriptorsLength

The length, in bytes, of the <b>TokenDescriptor</b> member.


### -field TokenDescriptor

The data containing a token created as the offload read ROD.


## -remarks



The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure is included with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/ns-storport-receive_token_information_header">RECEIVE_TOKEN_INFORMATION_HEADER</a>structure  as a response to a POPULATE TOKEN command. The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure follows the <b>SenseData</b> member of <b>RECEIVE_TOKEN_INFORMATION_HEADER</b>.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/ns-storport-receive_token_information_header">RECEIVE_TOKEN_INFORMATION_HEADER</a>
 

 

