---
UID: NF:portcls.IDmaChannel.BufferSize
title: IDmaChannel::BufferSize (portcls.h)
description: The BufferSize method returns the size in bytes of the DMA channel's data buffer.
tech.root: audio
ms.assetid: e20d36d9-4f2a-43bf-b224-da5501321c7a
ms.date: 10/31/2018
keywords: ["IDmaChannel::BufferSize"]
ms.keywords: IDmaChannel::BufferSize, BufferSize, IDmaChannel.BufferSize, IDmaChannel::BufferSize, IDmaChannel.BufferSize
req.header: portcls.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: Any level
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IDmaChannel::BufferSize
 - portcls/IDmaChannel::BufferSize
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDmaChannel.BufferSize
product:
 - Windows
---

# IDmaChannel::BufferSize


## -description

The BufferSize method returns the size in bytes of the DMA channel's data buffer.

## -returns

This method returns ULONG which is the size in bytes of the buffer.

## -remarks

The BufferSize method returns the buffer size that was set by the previous call to IDmaChannel::SetBufferSize. If SetBufferSize has not been called since the IDmaChannel::AllocateBuffer call, BufferSize returns the allocated buffer size. The DMA-channel object does not actually use this value internally. This value is maintained by the object to allow its various clients to communicate the intended size of the buffer. This call is often used to obtain the map-size parameter to the IDmaChannelSlave::Start method. 

> [!NOTE]
> Microsoft supports a diverse and inclusionary environment. Within this document, there are references to the word slave. Microsoft's Style Guide for Bias-Free Communications recognizes this as an exclusionary word. This wording is used as it is currently the wording used within the software.

## -see-also

[IDmaChannel](nn-portcls-idmachannel.md)

