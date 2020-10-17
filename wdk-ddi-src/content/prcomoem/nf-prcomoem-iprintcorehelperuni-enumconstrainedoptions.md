---
UID: NF:prcomoem.IPrintCoreHelperUni.EnumConstrainedOptions
title: IPrintCoreHelperUni::EnumConstrainedOptions (prcomoem.h)
description: The IPrintCoreHelperUni::EnumConstrainedOptions method provides a list of all of the options that are constrained in a particular feature, based on current settings.
old-location: print\iprintcorehelperuni_enumconstrainedoptions.htm
tech.root: print
ms.assetid: 362d858a-5087-4cd2-8778-e6564297bc8f
ms.date: 04/20/2018
keywords: ["IPrintCoreHelperUni::EnumConstrainedOptions"]
ms.keywords: EnumConstrainedOptions, EnumConstrainedOptions method [Print Devices], EnumConstrainedOptions method [Print Devices],IPrintCoreHelperUni interface, IPrintCoreHelperUni interface [Print Devices],EnumConstrainedOptions method, IPrintCoreHelperUni.EnumConstrainedOptions, IPrintCoreHelperUni::EnumConstrainedOptions, prcomoem/IPrintCoreHelperUni::EnumConstrainedOptions, print.iprintcorehelperuni_enumconstrainedoptions, print_unidrv-pscript_allplugins_1acbff6a-b43d-4504-b2dc-69713a61261f.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintCoreHelperUni::EnumConstrainedOptions
 - prcomoem/IPrintCoreHelperUni::EnumConstrainedOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelperUni.EnumConstrainedOptions
---

# IPrintCoreHelperUni::EnumConstrainedOptions


## -description

The <code>IPrintCoreHelperUni::EnumConstrainedOptions</code> method provides a list of all of the options that are constrained in a particular feature, based on current settings.

## -parameters

### -param pDevmode 

[in, optional]
A pointer to a <a href="/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure. If this pointer is provided, <code>IPrintCoreHelperUni::EnumConstrainedOptions</code> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode">IPrintOemUni::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.

### -param cbSize 

[in]
The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter.

### -param pszFeatureKeyword 

[in]
A string of ANSI characters that contains the feature name.

### -param pConstrainedOptionList

### -param pdwNumOptions 

[out]
A pointer to a variable that receives the number of constrained options in the array that is pointed to by the <i>pConstrainedOptionList</i> parameter.


#### - pConstrainedOptionList[] [out]

A pointer to an array of ANSI character strings. When <code>IPrintCoreHelperUni::EnumConstrainedOptions</code> returns, these strings will contain the names of all of the options that are constrained within the specified feature. The caller is not responsible for freeing the array or the individual strings in the array.

## -returns

<code>IPrintCoreHelperUni::EnumConstrainedOptions</code> should return one of the following values.

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
The constrained options were set for the specified feature.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The caller provided information that resulted in an invalid request, such as a request for a feature that does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One or more of the arguments were invalid. This value might mean that the feature is not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
There was not enough memory to create the options array or the core driver could not service the request due to lack of memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED, or other failures not listed here</b></dt>
</dl>
</td>
<td width="60%">
An unexpected condition occurred. The core driver is probably in an invalid state. The caller should exit with a failure code.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperuni">IPrintCoreHelperUni</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-enumoptions">IPrintCoreHelperUni::EnumOptions</a>