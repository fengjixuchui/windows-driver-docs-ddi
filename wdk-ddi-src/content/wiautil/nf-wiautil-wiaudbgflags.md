---
UID: NF:wiautil.wiauDbgFlags
title: wiauDbgFlags function (wiautil.h)
description: The wiauDbgFlags function determines whether a particular debugging flag is set.
old-location: image\wiaudbgflags.htm
tech.root: image
ms.assetid: 2185a1c0-e952-4dbd-b1a9-82339e417774
ms.date: 05/03/2018
ms.keywords: image.wiaudbgflags, wiauDbgFlags, wiauDbgFlags function [Imaging Devices], wiauFncs_db71e773-84d8-40b9-9688-9fa33aad9182.xml, wiautil/wiauDbgFlags
ms.topic: function
f1_keywords:
 - "wiautil/wiauDbgFlags"
req.header: wiautil.h
req.include-header: Wiautil.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wiautil.h
api_name:
- wiauDbgFlags
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauDbgFlags function


## -description


The <b>wiauDbgFlags</b> function determines whether a particular debugging flag is set.


## -parameters




### -param flags

Is a set of flags that control which information is placed in the log file or displayed in the debugger. See the <i>flags</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaudbgsetflags">wiauDbgSetFlags</a> for a list of the flag values.


### -param prefix

Pointer to a string containing a prefix (such as "ERROR " or "WARN ").


### -param fname

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgDump</b> is inserted.


### -param fmt




### -param param






####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output. 


## -returns



None




## -remarks



If message logging to log file, or debugger, or both is enabled and the particular flag in the <i>flags</i> parameter is enabled, this function logs a message containing the strings pointed to by the <i>prefix</i>, <i>fname</i>, and <i>fmt</i> parameters.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaudbgsetflags">wiauDbgSetFlags</a>
 

 

