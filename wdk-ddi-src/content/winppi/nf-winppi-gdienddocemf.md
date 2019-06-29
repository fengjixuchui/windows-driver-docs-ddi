---
UID: NF:winppi.GdiEndDocEMF
title: GdiEndDocEMF function (winppi.h)
description: The GdiEndDocEMF function ends EMF playback operations for an EMF-formatted print job.
old-location: print\gdienddocemf.htm
tech.root: print
ms.assetid: e58403d4-aacc-4d22-98e5-86db1a69c54a
ms.date: 04/20/2018
ms.keywords: GdiEndDocEMF, GdiEndDocEMF function [Print Devices], gdifnc_632b9c31-c0c1-4447-8a0c-ac8fb6b5af55.xml, print.gdienddocemf, winppi/GdiEndDocEMF
ms.topic: function
req.header: winppi.h
req.include-header: Winppi.h
req.target-type: Universal
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
req.lib: Gdi32.Lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
- Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
- GDI32Full.dll
api_name:
- GdiEndDocEMF
product:
- Windows
targetos: Windows
req.typenames: 
---

# GdiEndDocEMF function


## -description


The <b>GdiEndDocEMF</b> function ends EMF playback operations for an EMF-formatted print job.


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winppi/nf-winppi-gdigetspoolfilehandle">GdiGetSpoolFileHandle</a>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>, and an error code can be obtained by calling <b>GetLastError</b>.




## -remarks



The <b>GdiEndDocEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

The function performs operations that must be performed after a print job's EMF records have been played. The function calls the spooler's <b>EndDoc</b> function (described in the Microsoft Window SDK documentation), which in turn calls the printer driver's <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvenddoc">DrvEndDoc</a> function.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-gdi-functions-in-print-processors">Using GDI Functions in Print Processors</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winppi/nf-winppi-gdistartdocemf">GdiStartDocEMF</a>
 

 

