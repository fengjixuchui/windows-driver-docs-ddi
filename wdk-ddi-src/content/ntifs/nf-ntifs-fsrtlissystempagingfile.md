---
UID: NF:ntifs.FsRtlIsSystemPagingFile
title: FsRtlIsSystemPagingFile function (ntifs.h)
description: The FsRtlIsSystemPagingFile routine determines whether a given file is currently a system paging file.
old-location: ifsk\fsrtlissystempagingfile.htm
tech.root: ifsk
ms.assetid: BF92ADEA-4A9F-41E0-BE52-0794D1D827A1
ms.date: 04/16/2018
keywords: ["FsRtlIsSystemPagingFile function"]
ms.keywords: FsRtlIsPagingFile, FsRtlIsPagingFile routine [Installable File System Drivers], FsRtlIsSystemPagingFile, ifsk.fsrtlissystempagingfile, ntifs/FsRtlIsPagingFile
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlIsSystemPagingFile
 - ntifs/FsRtlIsSystemPagingFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIsPagingFile
---

# FsRtlIsSystemPagingFile function


## -description

The <b>FsRtlIsSystemPagingFile</b> routine determines whether a given file is currently a system paging file.

## -parameters

### -param FileObject 

[in]
Pointer to a file object for the file.

## -returns

<b>FsRtlIsSystemPagingFile</b> returns <b>TRUE</b> if the file represented by <i>FileObject</i> is a system paging file, otherwise <b>FALSE</b>.

## -see-also

<a href="/previous-versions/ff546873(v=vs.85)">FsRtlIsPagingFile</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpostpagingfilestackoverflow">FsRtlPostPagingFileStackOverflow</a>



<a href="/previous-versions/ff547285(v=vs.85)">FsRtlSupportsPerStreamContexts</a>