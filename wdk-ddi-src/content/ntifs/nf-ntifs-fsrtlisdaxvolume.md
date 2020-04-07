---
UID: NF:ntifs.FsRtlIsDaxVolume
title: FsRtlIsDaxVolume function (ntifs.h)
description: This routine queries if the specified file is on a direct access (DAX) volume.
old-location: ifsk\fsrtlisdaxvolume.htm
tech.root: ifsk
ms.assetid: FFCD2329-FD6A-48AE-8E9D-56AA7D79B174
ms.date: 04/16/2018
keywords: ["FsRtlIsDaxVolume function"]
ms.keywords: FsRtlIsDaxVolume, FsRtlIsDaxVolume routine [Installable File System Drivers], ifsk.fsrtlisdaxvolume, ntifs/FsRtlIsDaxVolume
f1_keywords:
 - "ntifs/FsRtlIsDaxVolume"
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
- ntifs.h
api_name:
- FsRtlIsDaxVolume
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsDaxVolume function


## -description


This routine queries if the specified file is on a  direct access (DAX) volume.


## -parameters




### -param FileObject [in]

A file object for a file, on the volume which is being queried.


## -returns



Returns <b>true</b> if the file is on a DAX volume; otherwise, <b>false</b>.




## -remarks



In DAX volumes,  user files
    are mapped directly to the persistent memory device.  Files are
    then accessed using the memory bus, to help boost system performance.



