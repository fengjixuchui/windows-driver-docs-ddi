---
UID: NS:ntifs._WOF_VERSION_INFO
title: _WOF_VERSION_INFO (ntifs.h)
description: The WOF_VERSION_INFO structure contains the version corresponding to the driver supporting a given provider.
old-location: ifsk\wof_version_info.htm
tech.root: ifsk
ms.assetid: 953F34FC-2E8F-4569-89B8-2F9541456F3B
ms.date: 04/16/2018
ms.keywords: "*PWOF_VERSION_INFO, PWOF_VERSION_INFO, PWOF_VERSION_INFO structure pointer [Installable File System Drivers], WOF_VERSION_INFO, WOF_VERSION_INFO structure [Installable File System Drivers], _WOF_VERSION_INFO, ifsk.wof_version_info, ntifs/PWOF_VERSION_INFO, ntifs/WOF_VERSION_INFO"
ms.topic: struct
f1_keywords:
 - "ntifs/WOF_VERSION_INFO"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntifs.h
api_name:
- WOF_VERSION_INFO
product:
- Windows
targetos: Windows
req.typenames: WOF_VERSION_INFO, *PWOF_VERSION_INFO
---

# _WOF_VERSION_INFO structure


## -description


The <b>WOF_VERSION_INFO</b> structure contains the version corresponding to the driver supporting a given provider.


## -struct-fields




### -field WofVersion

The version of the WOF driver. This value includes the major and minor version numbers of the operating system in the high-order word, and the build number of the operating system in the low-order word. The major version can be extracted with HIBYTE(HIWORD(<i>WofVersion</i>)); the minor version can be extracted with LOBYTE(HIWORD(<i>WofVersion</i>)); the build number can be extracted with LOWORD(<i>WofVersion</i>). 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-wof-version">FSCTL_GET_WOF_VERSION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_wof_external_file_id">WOF_EXTERNAL_FILE_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_wof_external_info">WOF_EXTERNAL_INFO</a>
 

 

