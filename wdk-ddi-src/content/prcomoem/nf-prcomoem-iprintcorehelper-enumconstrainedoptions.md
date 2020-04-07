---
UID: NF:prcomoem.IPrintCoreHelper.EnumConstrainedOptions
title: IPrintCoreHelper::EnumConstrainedOptions (prcomoem.h)
description: The IPrintCoreHelper::EnumConstrainedOptions method provides a list of all of the options that are constrained in a particular feature, based on current settings.
old-location: print\iprintcorehelper_enumconstrainedoptions.htm
tech.root: print
ms.assetid: 16a9417c-6d47-49fc-9ba9-e2b522255942
ms.date: 04/20/2018
keywords: ["IPrintCoreHelper::EnumConstrainedOptions"]
ms.keywords: EnumConstrainedOptions, EnumConstrainedOptions method [Print Devices], EnumConstrainedOptions method [Print Devices],IPrintCoreHelper interface, IPrintCoreHelper interface [Print Devices],EnumConstrainedOptions method, IPrintCoreHelper.EnumConstrainedOptions, IPrintCoreHelper::EnumConstrainedOptions, prcomoem/IPrintCoreHelper::EnumConstrainedOptions, print.iprintcorehelper_enumconstrainedoptions, print_unidrv-pscript_allplugins_7a6e6657-1af2-4719-998a-a41090bee035.xml
f1_keywords:
 - "prcomoem/IPrintCoreHelper.EnumConstrainedOptions"
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
- Prcomoem.h
api_name:
- IPrintCoreHelper.EnumConstrainedOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelper::EnumConstrainedOptions


## -description


The <b>IPrintCoreHelper::EnumConstrainedOptions</b> method provides a list of all of the options that are constrained in a particular feature, based on current settings.


## -parameters




### -param pDevmode [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure. If this pointer is provided, <b>IPrintCoreHelper::EnumConstrainedOptions</b> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-devmode">IPrintOemPS::DevMode</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode">IPrintOemUni::DevMode</a> or from a print ticket provider, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.


### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter.


### -param pszFeatureKeyword [in]

A string of ANSI characters that contain the feature name.


### -param pConstrainedOptionList




### -param pdwNumOptions [out]

A pointer to a variable that receives the number of constrained options in the array that is pointed to by the <i>pConstrainedOptionList</i> parameter.


#### - pConstrainedOptionList[] [out]

A pointer to an array of ANSI character strings. When <b>IPrintCoreHelper::EnumConstrainedOptions</b> returns, these strings will contain the names of all of the options that are constrained within the specified feature. The caller is not responsible for freeing the array or the individual strings in the array.


## -returns



<b>IPrintCoreHelper::EnumConstrainedOptions</b> should return one of the following values.

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
There was not enough memory to create the options array or the core driver could not service the request because of lack of memory. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED, or other failures not explicitly listed here</b></dt>
</dl>
</td>
<td width="60%">
An unexpected condition occurred. The core driver is probably in an invalid state. The caller should exit with a failure code.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelper">IPrintCoreHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-enumoptions">IPrintCoreHelper::EnumOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-whyconstrained">IPrintCoreHelper::WhyConstrained</a>
 

 

