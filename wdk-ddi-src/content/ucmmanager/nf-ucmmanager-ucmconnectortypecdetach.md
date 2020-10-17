---
UID: NF:ucmmanager.UcmConnectorTypeCDetach
title: UcmConnectorTypeCDetach function (ucmmanager.h)
description: Notifies the USB connector manager framework extension (UcmCx) when the partner connector detaches from the specified Type-C connector.
old-location: buses\ucmconnectortypecdetach.htm
tech.root: usbref
ms.assetid: E89DC8B6-9379-4FE2-BF4C-897DA9DFA11C
ms.date: 05/07/2018
keywords: ["UcmConnectorTypeCDetach function"]
ms.keywords: UcmConnectorTypeCDetach, UcmConnectorTypeCDetach method [Buses], buses.ucmconnectortypecdetach, ucmmanager/UcmConnectorTypeCDetach
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcmConnectorTypeCDetach
 - ucmmanager/UcmConnectorTypeCDetach
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - UcmCxstub.lib
 - UcmCxstub.dll
api_name:
 - UcmConnectorTypeCDetach
---

# UcmConnectorTypeCDetach function


## -description

Notifies the USB connector manager framework extension (UcmCx) when the partner connector  detaches from the specified Type-C connector.

## -parameters

### -param Connector 

[in]
Handle to the connector object that the client driver received in the previous call to <a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>.

## -returns

<b>UcmConnectorTypeCDetach</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> value.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypecattach">UcmConnectorTypeCAttach</a>