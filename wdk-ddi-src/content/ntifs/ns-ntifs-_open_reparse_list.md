---
UID: NS:ntifs._OPEN_REPARSE_LIST
title: _OPEN_REPARSE_LIST (ntifs.h)
description: Points to a list of OPEN_REPARSE_LIST_ENTRY structures that specify the tag and possibly GUID that should be opened directly without returning STATUS_REPARSE.
old-location: ifsk\open_reparse_list.htm
tech.root: ifsk
ms.assetid: 2477F904-A470-4FB0-83D8-0264A4838C12
ms.date: 04/16/2018
keywords: ["_OPEN_REPARSE_LIST structure"]
ms.keywords: "*POPEN_REPARSE_LIST, OPEN_REPARSE_LIST, OPEN_REPARSE_LIST structure [Installable File System Drivers], POPEN_REPARSE_LIST, POPEN_REPARSE_LIST structure pointer [Installable File System Drivers], _OPEN_REPARSE_LIST, ifsk.open_reparse_list, ntifs/OPEN_REPARSE_LIST, ntifs/POPEN_REPARSE_LIST"
f1_keywords:
 - "ntifs/OPEN_REPARSE_LIST"
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
- OPEN_REPARSE_LIST
product:
- Windows
targetos: Windows
req.typenames: OPEN_REPARSE_LIST, *POPEN_REPARSE_LIST
---

# _OPEN_REPARSE_LIST structure


## -description


 Points to a list of <b>OPEN_REPARSE_LIST_ENTRY</b>
  structures that specify the tag and possibly GUID that should be  opened directly without returning <b>STATUS_REPARSE</b>.


## -struct-fields




### -field OpenReparseList

 A pointer to a list of <b>OPEN_REPARSE_LIST_ENTRY</b>
  structures that specify the tag and possibly GUID that should be  opened directly without returning <b>STATUS_REPARSE</b>.

