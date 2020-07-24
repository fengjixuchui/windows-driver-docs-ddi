---
UID: NS:iddcx.IDARG_IN_COMMITMODES
title: IDARG_IN_COMMITMODES (iddcx.h)
description: Gives information about the paths that need to be committed.
old-location: display\idarg_in_commitmodes.htm
tech.root: display
ms.assetid: 242b7573-409a-4fdc-8ebf-596b8e6d41c7
ms.date: 05/10/2018
keywords: ["IDARG_IN_COMMITMODES structure"]
ms.keywords: IDARG_IN_COMMITMODES, IDARG_IN_COMMITMODES structure [Display Devices], display.idarg_in_commitmodes, iddcx/IDARG_IN_COMMITMODES
f1_keywords:
 - "iddcx/IDARG_IN_COMMITMODES"
 - "IDARG_IN_COMMITMODES"
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
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
- iddcx.h
api_name:
- IDARG_IN_COMMITMODES
targetos: Windows
req.typenames: 
---

# IDARG_IN_COMMITMODES structure


## -description


Gives information about the paths that need to be committed.
             


## -struct-fields




### -field PathCount


                     [in] The number of paths in the <b>pPaths</b> array
                 


### -field pPaths


                     [in] A pointer to the array of paths that need to be committed.
                 

