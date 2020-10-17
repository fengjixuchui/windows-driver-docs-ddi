---
UID: NF:wdm.DbgPrint
title: DbgPrint function (wdm.h)
description: The DbgPrint routine sends a message to the kernel debugger.
old-location: devtest\dbgprint.htm
tech.root: devtest
ms.assetid: abff1656-dceb-464f-a89c-30d7a24f742d
ms.date: 02/23/2018
keywords: ["DbgPrint function"]
ms.keywords: DbgPrint, DbgPrint routine [Driver Development Tools], DebugFns_5e11bbcc-adc2-46c0-b371-0e54c50bb2dc.xml, ULONG, devtest.dbgprint, wdm/DbgPrint
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: <= DIRQL (see Comments section)
targetos: Windows
req.typenames: 
f1_keywords:
 - DbgPrint
 - wdm/DbgPrint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - NtosKrnl.exe
api_name:
 - DbgPrint
---

# DbgPrint function


## -description

The <b>DbgPrint</b> routine sends a message to the kernel debugger. 

 In Windows Vista and later versions of Windows, <b>DbgPrint</b> sends a message only when the conditions that you specify apply (see the <a href="#remarks">Remarks</a> section for information).

## -parameters

### -param Format 

[in]
Specifies a pointer to the format string to print. The <i>Format</i> string supports most of the <b>printf</b>-style <a href="/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions">format specification fields</a>. However, the Unicode format codes (<b>%C</b>, <b>%S</b>, <b>%lc</b>, <b>%ls</b>, <b>%wc</b>, <b>%ws</b>, and <b>%wZ</b>) can only be used with IRQL = PASSIVE_LEVEL. The <b>DbgPrint</b> routine does not support any of the floating point types (<b>%f</b>, <b>%e</b>, <b>%E</b>, <b>%g</b>, <b>%G</b>, <b>%a</b>, or <b>%A</b>).

### -param param

Specifies arguments for the format string, as in <b>printf</b>.

## -returns

If successful, <b>DbgPrint</b> returns the NTSTATUS code STATUS_SUCCESS; otherwise it returns the appropriate error code.

## -remarks

<h3><a id="remarks"></a><a id="REMARKS"></a></h3>
<b>DbgPrint</b> and <b>DbgPrintEx</b> can be called at IRQL&lt;=DIRQL. However, Unicode format codes (%wc and %ws) can be used only at IRQL=PASSIVE_LEVEL. Also, because the debugger uses interprocess interrupts (IPIs) to communicate with other processors, calling <b>DbgPrint</b> at IRQL&gt;DIRQL can cause deadlocks.

Only kernel-mode drivers can call the <b>DbgPrint</b> routine. 

In Microsoft Windows Server 2003 and earlier versions of Windows, the <b>DbgPrint</b> routine sends a message to the kernel debugger. In Windows Vista and later versions of Windows, <b>DbgPrint</b> sends a message only if certain conditions apply. Specifically, it behaves like the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgprintex">DbgPrintEx</a> routine with the DEFAULT component and a message importance level of DPFLTR_INFO_LEVEL. In other words, the following two function calls are identical:


```
DbgPrint ( Format, arguments )

DbgPrintEx ( DPFLTR_DEFAULT_ID, DPFLTR_INFO_LEVEL, Format, arguments )
```

For more information about message filtering, components, and message importance level, see <a href="/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages">Reading and Filtering Debugging Messages</a>.

<div class="alert"><b>Note</b>    Regardless of which version of Windows you are using, it is recommended that you use <b>DbgPrintEx</b> instead of <b>DbgPrint</b>, since this allows you to control the conditions under which the message is sent.</div>
<div> </div>
Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>DbgPrint</b>. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.

There is no upper limit to the size of the <i>Format</i> string or the number of arguments. However, any single call to <b>DbgPrint</b> will only transmit 512 bytes of information. There is also a limit to the size of the DbgPrint buffer. See <a href="/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages">DbgPrint Buffer and the Debugger</a> for details.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgprintex">DbgPrintEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kdprint">KdPrint</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kdprintex">KdPrintEx</a>