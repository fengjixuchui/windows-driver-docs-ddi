---
UID: NF:winddiui.DrvSplEndDoc
title: DrvSplEndDoc function (winddiui.h)
description: 
old-location: print\drvsplenddoc.htm
tech.root: print
ms.assetid: 7972fd88-ca99-4a42-8476-754b26eb118c
ms.date: 04/20/2018
ms.keywords: DrvSplEndDoc, DrvSplEndDoc function [Print Devices], print.drvsplenddoc, print_interface-graphics_13e407aa-2d2a-4ec5-b3ab-bcb6fa745039.xml, winddiui/DrvSplEndDoc
ms.topic: function
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
- DrvSplEndDoc
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvSplEndDoc function


## -description





## -parameters




### -param hDriver


## -returns



This function does not return a value.

<h2><a id="ddk_drvsplenddoc_gg"></a><a id="DDK_DRVSPLENDDOC_GG"></a></h2>
The <b>DrvSplEndDoc</b> function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> instead of this function.

The <b>DrvSplEndDoc</b> function enables a user-mode rendering DLL to perform operations associated with the end of a print job.

<h3><a id="comments"></a><a id="COMMENTS"></a>Comments</h3>
To supply user-mode image-rendering code for printers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/choosing-user-mode-or-kernel-mode">Choosing User Mode or Kernel Mode</a>.



