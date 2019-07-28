---
UID: NS:wdm._OB_POST_DUPLICATE_HANDLE_INFORMATION
title: _OB_POST_DUPLICATE_HANDLE_INFORMATION (wdm.h)
description: The OB_POST_DUPLICATE_HANDLE_INFORMATION structure provides information to an ObjectPostCallback routine about a thread or process handle that has been duplicated.
old-location: kernel\ob_post_duplicate_handle_information.htm
tech.root: kernel
ms.assetid: 780ace20-bb88-47fe-b504-dd6a5e903840
ms.date: 04/30/2018
ms.keywords: "*POB_POST_DUPLICATE_HANDLE_INFORMATION, OB_POST_DUPLICATE_HANDLE_INFORMATION, OB_POST_DUPLICATE_HANDLE_INFORMATION structure [Kernel-Mode Driver Architecture], POB_POST_DUPLICATE_HANDLE_INFORMATION, POB_POST_DUPLICATE_HANDLE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _OB_POST_DUPLICATE_HANDLE_INFORMATION, kernel.ob_post_duplicate_handle_information, kstruct_c_7b277d55-5e47-4b6d-a77b-9f10decc3dbd.xml, wdm/OB_POST_DUPLICATE_HANDLE_INFORMATION, wdm/POB_POST_DUPLICATE_HANDLE_INFORMATION"
ms.topic: struct
f1_keywords:
 - "wdm/OB_POST_DUPLICATE_HANDLE_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of the Windows operating system.
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
- Wdm.h
api_name:
- OB_POST_DUPLICATE_HANDLE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: OB_POST_DUPLICATE_HANDLE_INFORMATION, *POB_POST_DUPLICATE_HANDLE_INFORMATION
---

# _OB_POST_DUPLICATE_HANDLE_INFORMATION structure


## -description


The <b>OB_POST_DUPLICATE_HANDLE_INFORMATION</b> structure provides information to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pob_post_operation_callback">ObjectPostCallback</a> routine about a thread or process handle that has been duplicated.


## -struct-fields




### -field GrantedAccess

An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that specifies the access that is granted for the handle.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pob_post_operation_callback">ObjectPostCallback</a>
 

 

