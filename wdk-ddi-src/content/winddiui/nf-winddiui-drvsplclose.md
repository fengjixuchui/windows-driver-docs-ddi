---
UID: NF:winddiui.DrvSplClose
title: DrvSplClose function (winddiui.h)
description: 
old-location: print\drvsplclose.htm
tech.root: print
ms.assetid: bd5f0bf2-ccb8-446c-b1e5-2e32538ebfbd
ms.date: 04/20/2018
ms.keywords: DrvSplClose, DrvSplClose function [Print Devices], print.drvsplclose, print_interface-graphics_e43f66ed-0e5e-4a27-ad52-0faebe549ac5.xml, winddiui/DrvSplClose
ms.topic: function
f1_keywords:
 - "winddiui/DrvSplClose"
req.header: winddiui.h
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
- winddiui.h
api_name:
- DrvSplClose
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvSplClose function


## -description





## -parameters




### -param hDriver


## -returns



This function does not return a value.

<h2><a id="ddk_drvsplclose_gg"></a><a id="DDK_DRVSPLCLOSE_GG"></a></h2>
The <b>DrvSplClose</b> function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> instead of this function.

The <b>DrvSplClose</b> function enables a user-mode rendering DLL to deallocate resources.

<h3><a id="comments"></a><a id="COMMENTS"></a>Comments</h3>
To supply user-mode image-rendering code for printers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/choosing-user-mode-or-kernel-mode">Choosing User Mode or Kernel Mode</a>.



