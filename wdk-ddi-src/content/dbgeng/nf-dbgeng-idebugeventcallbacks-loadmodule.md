---
UID: NF:dbgeng.IDebugEventCallbacks.LoadModule
title: IDebugEventCallbacks::LoadModule (dbgeng.h)
description: The LoadModule callback method is called by the engine when a module-load debugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_loadmodule.htm
tech.root: debugger
ms.assetid: f4efcbf3-f78a-4e0e-9741-4f9b68814e5b
ms.date: 05/03/2018
keywords: ["IDebugEventCallbacks::LoadModule"]
ms.keywords: ComCallbacks_3d8f0501-0915-425e-a940-aa5f41bad734.xml, IDebugEventCallbacks interface [Windows Debugging],LoadModule method, IDebugEventCallbacks.LoadModule, IDebugEventCallbacks::LoadModule, LoadModule, LoadModule method [Windows Debugging], LoadModule method [Windows Debugging],IDebugEventCallbacks interface, dbgeng/IDebugEventCallbacks::LoadModule, debugger.idebugeventcallbacks_loadmodule
f1_keywords:
 - "dbgeng/IDebugEventCallbacks.LoadModule"
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
- COM
api_location:
- dbgeng.h
api_name:
- IDebugEventCallbacks.LoadModule
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks::LoadModule


## -description


The <b>LoadModule</b> callback method is called by the engine when a module-load debugging event occurs in the target.


## -parameters




### -param ImageFileHandle [in]

Specifies the handle to the module's image file.  If this information is not available, <i>ImageFileHandle</i> will be <b>NULL</b>. 


### -param BaseOffset [in]

Specifies the base address of the module in the target's memory address space.  If this information is not available, <i>BaseOffset</i> will be <b>NULL</b>.


### -param ModuleSize [in]

Specifies the module's image size in bytes.  If this information is not available, <i>ModuleSize</i> will be <b>NULL</b>.


### -param ModuleName [in, optional]

Specifies the simplified module name that is used by the debugger engine.  In most cases, this matches the image file name excluding the extension.  If this information is not available, <i>ModuleName</i> will be <b>NULL</b>.


### -param ImageName [in, optional]

Specifies the module's image file name, which can include the path.  If this information is not available, <i>ImageName</i> will be <b>NULL</b>.


### -param CheckSum [in]

Specifies the checksum of the module's image file.  If this information is not available, <i>CheckSum</i> will be <b>NULL</b>.


### -param TimeDateStamp [in]

Specifies the time and date stamp of the module's image file.  If this information is not available, <i>TimeDateStamp</i> will be zero.


## -returns



This method returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_LOAD_MODULE flag is set in the mask returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-getinterestmask">IDebugEventCallbacks::GetInterestMask</a>.

After calling this method, the engine will call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changesymbolstate">IDebugEventCallbacks::ChangeSymbolState</a>, with the <i>Flags</i> parameter containing the bit flag DEBUG_CSS_LOADS.

For more information about handling events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>. 



