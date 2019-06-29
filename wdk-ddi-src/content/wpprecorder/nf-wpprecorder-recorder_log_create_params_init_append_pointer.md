---
UID: NF:wpprecorder.RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
title: RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function (wpprecorder.h)
description: The RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER method initializes the RECORDER_LOG_CREATE_PARAMS with the pointer to link logs.
old-location: devtest\recorder_log_create_params_init_append_pointer.htm
tech.root: devtest
ms.assetid: EC94E27C-C863-49F0-B13C-B661E96991B7
ms.date: 02/23/2018
ms.keywords: RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER, RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function [Driver Development Tools], devtest.recorder_log_create_params_init_append_pointer, wpprecorder/RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
ms.topic: function
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
- wpprecorder.h
api_name:
- RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
product:
- Windows
targetos: Windows
req.typenames: 
---

# RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function


## -description


The <b>RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER</b> method initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wpprecorder/ns-wpprecorder-_recorder_log_create_params">RECORDER_LOG_CREATE_PARAMS</a> with the pointer to link logs.


## -parameters




### -param Params [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wpprecorder/ns-wpprecorder-_recorder_log_create_params">RECORDER_LOG_CREATE_PARAMS</a> structure.


### -param LogIdentifier [in, optional]

String identifier for the log.


### -param LogIdentifierAppendPointer [in]

A pointer from each debug message to its IFR’s metadata structure.


## -returns



This function does not return a value.



