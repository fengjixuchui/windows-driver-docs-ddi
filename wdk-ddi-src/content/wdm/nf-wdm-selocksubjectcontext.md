---
UID: NF:wdm.SeLockSubjectContext
title: SeLockSubjectContext function (wdm.h)
description: The SeLockSubjectContext routine locks the primary and impersonation tokens of a captured subject context.
old-location: ifsk\selocksubjectcontext.htm
tech.root: ifsk
ms.assetid: 032e203a-9cb0-4232-91fc-883528e15a81
ms.date: 04/16/2018
ms.keywords: SeLockSubjectContext, SeLockSubjectContext routine [Installable File System Drivers], ifsk.selocksubjectcontext, ntifs/SeLockSubjectContext, seref_ea4696ab-8343-4d15-866c-15720d009db8.xml
ms.topic: function
f1_keywords:
 - "wdm/SeLockSubjectContext"
req.header: wdm.h
req.include-header: Ntifs.h, Wdm.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeLockSubjectContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeLockSubjectContext function


## -description


The <b>SeLockSubjectContext</b> routine locks the primary and impersonation tokens of a captured subject context.


## -parameters




### -param SubjectContext [in]

Pointer to a SECURITY_SUBJECT_CONTEXT structure returned by a call to <b>SeCaptureSubjectContext</b>.


## -returns



None




## -remarks



<b>SeLockSubjectContext</b> acquires read locks on the primary and impersonation tokens of a captured subject context.

To capture a subject context, use <b>SeCaptureSubjectContext</b>.

Each call to <b>SeLockSubjectContext</b> must be matched by a subsequent call to <b>SeUnlockSubjectContext</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-secapturesubjectcontext">SeCaptureSubjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-seunlocksubjectcontext">SeUnlockSubjectContext</a>
 

 

