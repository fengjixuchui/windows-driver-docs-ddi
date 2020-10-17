---
UID: NF:ntifs.SeDeleteClientSecurity
title: SeDeleteClientSecurity macro (ntifs.h)
description: The SeDeleteClientSecurity routine deletes a client security context.
old-location: ifsk\sedeleteclientsecurity.htm
tech.root: ifsk
ms.assetid: 413469b9-2f6c-4f4d-8723-80645a72744c
ms.date: 04/16/2018
keywords: ["SeDeleteClientSecurity macro"]
ms.keywords: SeDeleteClientSecurity, SeDeleteClientSecurity routine [Installable File System Drivers], ifsk.sedeleteclientsecurity, ntifs/SeDeleteClientSecurity, seref_bab4478e-d302-478b-8819-79c9b2f79aa7.xml
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SeDeleteClientSecurity
 - ntifs/SeDeleteClientSecurity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SeDeleteClientSecurity
---

# SeDeleteClientSecurity macro


## -description

The <b>SeDeleteClientSecurity</b> routine deletes a client security context.

## -parameters

### -param C

<p>Pointer to the client security context structure to be deleted.</p>

## -remarks

<b>SeDeleteClientSecurity</b> deletes a client security context structure and performs any necessary cleanup, such as removing any client token references.

Each call to <b>SeCreateClientSecurity</b> or <b>SeCreateClientSecurityFromSubjectContext</b> must be matched by a subsequent call to <b>SeDeleteClientSecurity</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-secreateclientsecurity">SeCreateClientSecurity</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-secreateclientsecurityfromsubjectcontext">SeCreateClientSecurityFromSubjectContext</a>