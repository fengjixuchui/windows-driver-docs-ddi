---
UID: NF:bidispl.IBidiSpl2.BindDevice
title: IBidiSpl2::BindDevice (bidispl.h)
description: The BindDevice method binds a printer to a bidirectional printer communication (bidi communication) request. This method is similar to the OpenPrinter function.
old-location: print\ibidispl2_ibidispl2__binddevice.htm
tech.root: print
ms.assetid: c5bd238d-4b85-4463-aa73-ff3a7798ccff
ms.date: 04/20/2018
ms.keywords: BIDI_ACCESS_ADMINISTRATOR, BIDI_ACCESS_USER, BindDevice, BindDevice method [Print Devices], BindDevice method [Print Devices],IBidiSpl2 interface, IBidiSpl2 interface [Print Devices],BindDevice method, IBidiSpl2.BindDevice, IBidiSpl2::BindDevice, _win32_IBidiSpl2_BindDevice, bidispl/IBidiSpl2::BindDevice, gdi.ibidispl2_ibidispl2__binddevice, print.ibidispl2_ibidispl2__binddevice
ms.topic: method
f1_keywords:
 - "bidispl/IBidiSpl2.BindDevice"
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
req.dll: Bidispl.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- bidispl.dll
api_name:
- IBidiSpl2.BindDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl2::BindDevice


## -description


The <b>BindDevice</b> method binds a printer to a bidirectional printer communication (bidi communication) request. This method is similar to the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/openprinter">OpenPrinter</a> function.


## -parameters




### -param pszDeviceName [in]

A pointer to a null-terminated string that contains the name of the printer or print server. If <b>NULL</b>, this parameter indicates the local print server.


### -param dwAccess [in]

The access privileges for the printer. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="BIDI_ACCESS_ADMINISTRATOR"></a><a id="bidi_access_administrator"></a><dl>
<dt><b>BIDI_ACCESS_ADMINISTRATOR</b></dt>
</dl>
</td>
<td width="60%">
Permits users to perform all administrative tasks and basic printing operations except for SYNCHRONIZE. This is the same as PRINTER_ALL_ACCESS in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/openprinter">OpenPrinter</a>.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_ACCESS_USER"></a><a id="bidi_access_user"></a><dl>
<dt><b>BIDI_ACCESS_USER</b></dt>
</dl>
</td>
<td width="60%">
Permits users to perform basic printing operations. This is the same as PRINTER_ACCESS_USE in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/openprinter">OpenPrinter</a>.

</td>
</tr>
</table>
 


## -returns



The method returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code that corresponds to the last error.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nn-bidispl-ibidispl2">IBidiSpl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/openprinter">OpenPrinter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/print-spooler-components">Print Spooler Components</a>
 

 

