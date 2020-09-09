---
UID: NF:ks.KsValidateClockCreateRequest
title: KsValidateClockCreateRequest function (ks.h)
description: The KsValidateClockCreateRequest function validates the clock creation request and returns the create structure associated with the request.This can only be called at PASSIVE_LEVEL.
old-location: stream\ksvalidateclockcreaterequest.htm
tech.root: stream
ms.assetid: ec10c10e-4604-47fc-a2e7-4df9d90acf0b
ms.date: 04/23/2018
keywords: ["KsValidateClockCreateRequest function"]
ms.keywords: KsValidateClockCreateRequest, KsValidateClockCreateRequest function [Streaming Media Devices], ks/KsValidateClockCreateRequest, ksfunc_e681d03e-44fb-43fb-b317-dc7e63fe6cb2.xml, stream.ksvalidateclockcreaterequest
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsValidateClockCreateRequest
 - ks/KsValidateClockCreateRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsValidateClockCreateRequest
---

# KsValidateClockCreateRequest function


## -description

The <b>KsValidateClockCreateRequest</b> function validates the clock creation request and returns the create structure associated with the request.

This can only be called at PASSIVE_LEVEL.

## -parameters

### -param Irp

### -param ClockCreate 

[out]
Specifies the clock create structure pointer passed to the create request.


#### - lrp [in]

Specifies the IRP with the clock create request being handled.

## -returns

The <b>KsValidateClockCreateRequest</b> function returns STATUS_SUCCESS if successful, or an error if unsuccessful.

