---
UID: NF:wpprecorder.WppRecorderLogSetIdentifier
title: WppRecorderLogSetIdentifier macro (wpprecorder.h)
description: The WppRecorderLogSetIdentifier method sets a string identifier for the recorder log.
old-location: devtest\wpprecorderlogsetidentifier.htm
tech.root: devtest
ms.assetid: E2687B3C-2BCF-4764-99E0-4495296F14C4
ms.date: 02/23/2018
ms.keywords: WppRecorderLogSetIdentifier, devtest.wpprecorderlogsetidentifier, imp_WppRecorderLogSetIdentifier, imp_WppRecorderLogSetIdentifier function [Driver Development Tools], wpprecorder/imp_WppRecorderLogSetIdentifier
ms.topic: macro
f1_keywords:
 - "wpprecorder/imp_WppRecorderLogSetIdentifier"
req.header: wpprecorder.h
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
- Wpprecorder.h
api_name:
- imp_WppRecorderLogSetIdentifier
product:
- Windows
targetos: Windows
req.typenames: 
---

# WppRecorderLogSetIdentifier macro


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogsetidentifier">WppRecorderLogSetIdentifier</a> method sets a string identifier for the recorder log.


## -parameters




### -param RecorderLog

A recorder log handle returned in a previous call to WppRecorderLogCreate.


### -param LogIdentifier

A string identifier to set.


## -remarks



Do not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogsetidentifier">WppRecorderLogSetIdentifier</a> on the default log handle returned by <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn895240(v=vs.85)">WppRecorderLogGetDefault</a>.



