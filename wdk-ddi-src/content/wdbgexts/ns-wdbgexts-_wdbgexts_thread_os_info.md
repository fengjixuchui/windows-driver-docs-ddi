---
UID: NS:wdbgexts._WDBGEXTS_THREAD_OS_INFO
title: _WDBGEXTS_THREAD_OS_INFO (wdbgexts.h)
description: The IG_GET_THREAD_OS_INFO Ioctl operation returns information about an operating system thread in the target. When calling Ioctl with IoctlType set to IG_GET_THREAD_OS_INFO, IpvData should contain an instance of the WDBGEXTS_THREAD_OS_INFO structure.
old-location: debugger\ig_get_thread_os_info.htm
tech.root: debugger
ms.assetid: 5cd1ba71-af2f-4662-b37d-88f4e4aa7624
ms.date: 05/03/2018
keywords: ["_WDBGEXTS_THREAD_OS_INFO structure"]
ms.keywords: "*PWDBGEXTS_THREAD_OS_INFO, PWDBGEXTS_THREAD_OS_INFO, PWDBGEXTS_THREAD_OS_INFO structure pointer [Windows Debugging], WDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO structure [Windows Debugging], WdbgExts_Ref_dfcc01ec-d4f4-4eba-adb5-d729f951f502.xml, _WDBGEXTS_THREAD_OS_INFO, debugger.ig_get_thread_os_info, wdbgexts/PWDBGEXTS_THREAD_OS_INFO, wdbgexts/WDBGEXTS_THREAD_OS_INFO"
f1_keywords:
 - "wdbgexts/WDBGEXTS_THREAD_OS_INFO"
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
- wdbgexts.h
api_name:
- WDBGEXTS_THREAD_OS_INFO
product:
- Windows
targetos: Windows
req.typenames: WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO
---

# _WDBGEXTS_THREAD_OS_INFO structure


## -description


The IG_GET_THREAD_OS_INFO <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a> operation returns information about an operating system thread in the target.  When calling <b>Ioctl</b> with <i>IoctlType</i> set to IG_GET_THREAD_OS_INFO, <i>IpvData</i> should contain an instance of the WDBGEXTS_THREAD_OS_INFO structure.


## -struct-fields




### -field ThreadId

Specifies the operating system thread ID (within the current process) for the thread whose information is being requested.


### -field ExitStatus

Receives the exit code of the thread.  If the thread is still running or the exit code is not known, <b>ExitStatus</b> will be set to STILL_ACTIVE.


### -field PriorityClass

Receives the priority class of the thread.  The priority classes are defined by the constants <i>XXX</i>_PRIORITY_CLASS in WinBase.h.  See the Platform SDK for more information about thread priority classes.  If the priority class is not know, <b>PriorityClass</b> will be set to zero.


### -field Priority

Receives the priority of the thread relative to the priority class.  Some thread priorities are defined by the constants THREAD_PRIORITY_<i>XXX</i> in WinBase.h.  See the Platform SDK for more information about thread priorities.  If the priority is not known, <b>Priority</b> will be set to THREAD_PRIORITY_NORMAL.


### -field CreateTime

Receives the creation time of the thread.


### -field ExitTime

Receives the exit time of the thread.  If the thread has not exited, <b>ExitTime</b> is undefined.


### -field KernelTime

Receives the amount of time that the thread has executed in kernel mode.


### -field UserTime

Receives the amount of time that the thread has executed in user-mode.


### -field StartOffset

Receives the starting address of the thread.  If the starting address is not known, <b>StartOffset</b> will be set to zero.


### -field Affinity

Receives the thread affinity mask for the thread in a symmetric multiprocessor (SMP) computer.  See the Platform SDK for more information about the thread affinity mask.  If the affinity mask is not known, <b>Affinity</b> is set to zero.


## -remarks



The parameters for the IG_GET_THREAD_OS_INFO <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a> operation are the members of the WDBGEXTS_THREAD_OS_INFO structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a>
 

 

