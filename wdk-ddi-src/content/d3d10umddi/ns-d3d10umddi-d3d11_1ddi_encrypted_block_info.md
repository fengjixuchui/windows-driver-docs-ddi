---
UID: NS:d3d10umddi.D3D11_1DDI_ENCRYPTED_BLOCK_INFO
title: D3D11_1DDI_ENCRYPTED_BLOCK_INFO (d3d10umddi.h)
description: Specifies which bytes in a video surface are encrypted.
old-location: display\d3d11_1ddi_encrypted_block_info.htm
ms.assetid: 36d7fab0-e343-4236-9d13-93cc0e41721e
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_ENCRYPTED_BLOCK_INFO structure"]
ms.keywords: D3D11_1DDI_ENCRYPTED_BLOCK_INFO, D3D11_1DDI_ENCRYPTED_BLOCK_INFO structure [Display Devices], d3d10umddi/D3D11_1DDI_ENCRYPTED_BLOCK_INFO, display.d3d11_1ddi_encrypted_block_info
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_ENCRYPTED_BLOCK_INFO"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3d10umddi.h
api_name:
- D3D11_1DDI_ENCRYPTED_BLOCK_INFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_ENCRYPTED_BLOCK_INFO
---

# D3D11_1DDI_ENCRYPTED_BLOCK_INFO structure


## -description


Specifies which bytes in a video surface are encrypted.


## -struct-fields




### -field NumEncryptedBytesAtBeginning

The number of bytes that are encrypted at the start of the buffer.


### -field NumBytesInSkipPattern

The number of bytes that are skipped after the first <b>NumEncryptedBytesAtBeginning</b> bytes, and then after each block of <b>NumBytesInEncryptPattern</b> bytes. Skipped bytes are not encrypted.


### -field NumBytesInEncryptPattern

The number of bytes that are encrypted after each block of skipped bytes.

The skip and encrypt pattern is then repeated until the buffer ends. For more information about the skip-encrypt pattern, see the Remarks section.


## -remarks



Because the buffer's encrypted portion is specified in bytes, an application must ensure that the encrypted blocks match the GPU's crypto-block alignment.

The following examples show how the runtime can partition a buffer's encryption.

<ol>
<li>The following values encrypt the first 100 bytes of the buffer and skip the remaining buffer data:<ul>
<li><b>NumEncryptedBytesAtBeginning</b> = 100;</li>
<li><b>NumBytesInSkipPattern</b> = 0;</li>
<li><b>NumBytesInEnycryptPattern</b> = 0;</li>
</ul>
</li>
<li>The following values encrypt the first 100 bytes of the buffer, skips the next 20 bytes, and then encrypt the next 2 bytes blocks. The process is then repeated where these values skip 20 bytes and encrypt 2 bytes until the end of the buffer.<ul>
<li><b>NumEncryptedBytesAtBeginning</b> = 100;</li>
<li><b>NumBytesInSkipPattern</b> = 20;</li>
<li><b>NumBytesInEnycryptPattern</b> = 2;</li>
</ul>
</li>
</ol>


