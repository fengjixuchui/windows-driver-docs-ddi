---
UID: NS:winsplp.__unnamed_struct_8
title: SHOWUIPARAMS (winsplp.h)
description: The SplPromptUIInUsersSession function uses the SHOWUIPARAMS structure to hold information about the appearance and behavior of a message box.
old-location: print\showuiparams.htm
tech.root: print
ms.assetid: 63ee7f5c-ca95-4c2d-be17-56a769188f8c
ms.date: 04/20/2018
keywords: ["SHOWUIPARAMS structure"]
ms.keywords: "*PSHOWUIPARAMS, PSHOWUIPARAMS, PSHOWUIPARAMS structure pointer [Print Devices], SHOWUIPARAMS, SHOWUIPARAMS structure [Print Devices], print.showuiparams, spoolfnc_bf6ce7c8-8b86-40c9-9b03-64c3e3366a04.xml, winsplp/PSHOWUIPARAMS, winsplp/SHOWUIPARAMS"
f1_keywords:
 - "winsplp/SHOWUIPARAMS"
 - "SHOWUIPARAMS"
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: This function is available in Windows XP and later operating systems.
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
- winsplp.h
api_name:
- SHOWUIPARAMS
targetos: Windows
req.typenames: SHOWUIPARAMS, *PSHOWUIPARAMS
---

# SHOWUIPARAMS structure


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-splpromptuiinuserssession">SplPromptUIInUsersSession</a> function uses the SHOWUIPARAMS structure to hold information about the appearance and behavior of a message box.


## -struct-fields




### -field UIType

Specifies the type of user interface element. This member can be set to a single value: <b>kMessageBox</b>.


### -field MessageBoxParams

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-messagebox_params">MESSAGEBOX_PARAMS</a> structure that contains the information about the message box.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-messagebox_params">MESSAGEBOX_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-splpromptuiinuserssession">SplPromptUIInUsersSession</a>
 

 

