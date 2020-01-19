---
UID: NF:prcomoem.IPrintOemDriverUni.DrvGetDriverSetting
title: IPrintOemDriverUni::DrvGetDriverSetting (prcomoem.h)
description: The IPrintOemDriverUni::DrvGetDriverSetting method is provided by the Unidrv driver so that rendering plug-ins can obtain the current status of printer features and other internal information.
old-location: print\iprintoemdriveruni_drvgetdriversetting.htm
tech.root: print
ms.assetid: 29ccd7e6-60eb-4a8e-9a71-9fbed4b2bdcf
ms.date: 04/20/2018
ms.keywords: DrvGetDriverSetting, DrvGetDriverSetting method [Print Devices], DrvGetDriverSetting method [Print Devices],IPrintOemDriverUni interface, IPrintOemDriverUni interface [Print Devices],DrvGetDriverSetting method, IPrintOemDriverUni.DrvGetDriverSetting, IPrintOemDriverUni::DrvGetDriverSetting, prcomoem/IPrintOemDriverUni::DrvGetDriverSetting, print.iprintoemdriveruni_drvgetdriversetting, print_unidrv-pscript_rendering_7fd3ea86-8473-4499-a860-318a66d7838b.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintOemDriverUni.DrvGetDriverSetting"
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
- prcomoem.h
api_name:
- IPrintOemDriverUni.DrvGetDriverSetting
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUni::DrvGetDriverSetting


## -description


The <code>IPrintOemDriverUni::DrvGetDriverSetting</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain the current status of printer features and other internal information.


## -parameters




### -param pdriverobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param Feature

Caller supplied value identifying the printer feature for which option settings will be returned. This can be either a string pointer or a constant, as described in the following Remarks section.


### -param pOutput

Caller-supplied pointer to a buffer to receive the specified information.


### -param cbSize

Caller-supplied size, in bytes, of the buffer pointed to by <i>pOutput</i>.


### -param pcbNeeded

Caller-supplied pointer to a location to receive the minimum buffer size required to contain the requested information.


### -param pdwOptionsReturned

Caller-supplied pointer to a location to receive the number of option strings placed in <i>pOutput</i>.


## -returns



The method must return one of the following values.

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
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



When the <code>IPrintOemDriverUni::DrvGetDriverSetting</code> method is called, either a string pointer or a constant value can be specified for <i>pFeatureKeyword</i>.

<ul>
<li>
If <i>pFeatureKeyword</i> is a string, it must represent a feature name specified in a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/unidrv-minidrivers">Unidrv minidriver</a> GPD file

The method should return one or more NULL-terminated strings in the buffer pointed to by <i>pOutput</i>. Each string should represent the name of a currently selected option. The number of strings should be returned in <i>pdwOptionsReturned</i>.

</li>
<li>
If <i>pFeatureKeyword</i> is a constant, it must be one of the <b>OEMGDS_</b>-prefixed constants defined in printoem.h. The method should return the value indicated by the specified constant by placing it in the buffer pointed to by <i>pOutput</i>. The value returned in <i>pdwOptionsReturned</i> must be 1.

</li>
</ul>


