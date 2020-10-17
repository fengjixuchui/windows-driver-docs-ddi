---
UID: NF:swenum.KsDereferenceSoftwareBusObject
title: KsDereferenceSoftwareBusObject function (swenum.h)
description: The KsDereferenceSoftwareBusObject function decrements the reference count of the demand-load bus enumerator object's PDO.
old-location: stream\ksdereferencesoftwarebusobject.htm
tech.root: stream
ms.assetid: 11203a5d-1484-4a49-aedc-e11baf22cac9
ms.date: 04/23/2018
keywords: ["KsDereferenceSoftwareBusObject function"]
ms.keywords: KsDereferenceSoftwareBusObject, KsDereferenceSoftwareBusObject function [Streaming Media Devices], ksfunc_e9066001-173a-40e1-a933-2f646a21afad.xml, stream.ksdereferencesoftwarebusobject, swenum/KsDereferenceSoftwareBusObject
req.header: swenum.h
req.include-header: Swenum.h
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
 - KsDereferenceSoftwareBusObject
 - swenum/KsDereferenceSoftwareBusObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsDereferenceSoftwareBusObject
---

# KsDereferenceSoftwareBusObject function


## -description

<i>This function is intended for internal use only.</i>

The <b>KsDereferenceSoftwareBusObject</b> function decrements the reference count of the demand-load bus enumerator object's PDO.

## -parameters

### -param Header 

[in]
Pointer to the device header (extension) of the demand-load bus enumerator.

## -returns

None

## -remarks

A minidriver can access this function through the <b>DereferenceDeviceObject</b> member of the BUS_INTERFACE_SWENUM structure.

When the demand-load bus enumerator object's PDO reference count is 0, it becomes eligible for removal. Note that this condition does not guarantee removal.

## -see-also

<a href="/windows-hardware/drivers/ddi/swenum/ns-swenum-_bus_interface_swenum">BUS_INTERFACE_SWENUM</a>



<a href="/windows-hardware/drivers/ddi/swenum/nf-swenum-ksquerysoftwarebusinterface">KsQuerySoftwareBusInterface</a>



<a href="/windows-hardware/drivers/ddi/swenum/nf-swenum-ksreferencesoftwarebusobject">KsReferenceSoftwareBusObject</a>