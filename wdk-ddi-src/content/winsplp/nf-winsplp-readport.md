---
UID: NF:winsplp.ReadPort
title: ReadPort function (winsplp.h)
description: A port monitor's ReadPort function reads data from a printer port.
old-location: print\readport.htm
tech.root: print
ms.assetid: ab1fb259-edcb-4e19-9afb-18aa6688764a
ms.date: 02/02/2018
keywords: ["ReadPort function"]
ms.keywords: ReadPort, spoolfnc_f4b817ce-afeb-4d3f-b8ce-e060b8de8143.xml, ReadPort function [Print Devices], print.readport, winsplp/ReadPort
f1_keywords:
 - "winsplp/ReadPort"
 - "ReadPort"
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.lib: NtosKrnl.exe
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
- ReadPort
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# ReadPort function


## -description


A port monitor's <code>ReadPort</code> function reads data from a printer port.


## -syntax


```cpp
BOOL ReadPort(
  _In_  HANDLE  hPort,
  _Out_ LPBYTE  pBuffer,
        DWORD   cbBuffer,
  _Out_ LPDWORD pcbRead
);
```


## -parameters




### -param hPort [in]

Caller-supplied port handle.


### -param pBuffer [out]

Caller-supplied pointer to a buffer to receive data read from the port.


### -param cbBuffer

Caller-supplied size, in bytes, of <i>pBuffer</i>.


### -param pcbRead [out]

Caller-supplied pointer to a location to receive the number of bytes successfully read from the port.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.




## -remarks




<a href="https://docs.microsoft.com/windows-hardware/drivers/print/language-monitors">Language monitors</a> and port monitor server DLLs are required to define a <code>ReadPort</code> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The handle received as the function's <i>hPort</i> argument is the port handle that the monitor's <a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a> or <a href="https://docs.microsoft.com/previous-versions/ff559596(v=vs.85)">OpenPortEx</a> function supplied.

Typically, a language monitor's <code>ReadPort</code> function calls the associated port monitor's <code>ReadPort</code> function, and returns the obtained buffer contents to the caller.

Additionally, a language monitor might create a separate thread that calls the port monitor's <code>ReadPort</code> function to check for unsolicited status information. If such a read operation succeeds, the status information should be returned to the spooler by calling <b>SetPort</b> (described in the Microsoft Windows SDK documentation).

Typically, a port monitor server DLL's <code>ReadPort</code> function calls <b>ReadFile</b> (described in the Windows SDK documentation) to obtain data from the kernel-mode port driver. The function just returns the data to the caller.

Even though both language monitors and port monitors must define <code>ReadPort</code> functions and place their addresses in MONITOR2 structures, a language monitor's <code>ReadPort</code> function is never actually called by the spooler or an application. The function is solely for the internal use of the language monitor itself.

For example pjlmon.dll, the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/sample-language-monitor">sample language monitor</a>, creates a separate thread that calls its own <code>ReadPort</code> to watch for unsolicited printer status information, and the <code>ReadPort</code> function calls the port monitor's <code>ReadPort</code> function. When the port monitor returns data to the language monitor, the language monitor parses the received data and calls <b>SetPort</b> (described in the Windows SDK documentation) to send status information to the spooler.

The function should return the number of bytes successfully read by placing the number in the location pointed to by <i>pcbRead</i>. The caller determines the success or failure of the write operation by checking <code>ReadPort's</code> return value, not the returned byte count. So a returned byte count of zero does not represent a failed read unless the function returns <b>FALSE</b>.

Some sort of system-implemented or monitor-implemented time-out mechanism must ensure that the <code>ReadPort</code> function will return within a reasonable amount of time, to avoid stalling the spooler.

It is acceptable for a language monitor to call a port monitor's <code>ReadPort</code> routine outside of a <a href="https://docs.microsoft.com/previous-versions/ff562710(v=vs.85)">StartDocPort</a>/<a href="https://docs.microsoft.com/previous-versions/ff548742(v=vs.85)">EndDocPort</a> pair. (Such a call might be generated by a thread checking for unsolicited status.) However, some port monitors might fail such a call, so the language monitor must be written to handle this failure.




## -see-also

<a href="https://docs.microsoft.com/previous-versions/ff550506(v=vs.85)">GetPrinterDataFromPort</a>



<a href="https://docs.microsoft.com/previous-versions/ff562710(v=vs.85)">StartDocPort</a>



<a href="https://docs.microsoft.com/previous-versions/ff559596(v=vs.85)">OpenPortEx</a>



<a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a>



<a href="https://docs.microsoft.com/previous-versions/ff548742(v=vs.85)">EndDocPort</a>



 

 


