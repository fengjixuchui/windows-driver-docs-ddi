---
UID: NF:prcomoem.IPrintCoreHelperPS.EnumOptions
title: IPrintCoreHelperPS::EnumOptions (prcomoem.h)
description: The IPrintCoreHelperPS::EnumOptions method gets a list of available options for the given feature.
old-location: print\iprintcorehelperps_enumoptions.htm
tech.root: print
ms.assetid: bd23f4e6-7a99-4347-ae29-a1e832db2e03
ms.date: 04/20/2018
ms.keywords: EnumOptions, EnumOptions method [Print Devices], EnumOptions method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],EnumOptions method, IPrintCoreHelperPS.EnumOptions, IPrintCoreHelperPS::EnumOptions, prcomoem/IPrintCoreHelperPS::EnumOptions, print.iprintcorehelperps_enumoptions, print_unidrv-pscript_allplugins_89c5ea61-aedf-43c6-9a8b-020656476f35.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintCoreHelperPS.EnumOptions"
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
- IPrintCoreHelperPS.EnumOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperPS::EnumOptions


## -description


The <b>IPrintCoreHelperPS::EnumOptions</b> method gets a list of available options for the given feature. 


## -parameters




### -param pszFeatureKeyword [in]

An ANSI character string that contains the feature whose options are requested. 


### -param pOptionList




### -param pdwNumOptions [out]

A pointer to a variable that receives the number of options in the option array that is pointed to by the <i>pOptionList</i> parameter.


#### - pOptionList[] [out]

A pointer to an array of ANSI character strings that contain all of the options for the feature that is specified in the <i>pszFeatureKeyword</i> parameter. <b>IPrintCoreHelperPS::EnumOptions</b> is responsible for allocating the memory for the array. The last element of the array must be a <b>NULL</b> string.


## -returns



<b>IPrintCoreHelperPS::EnumOptions</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



When <b>IPrintCoreHelperPS::EnumOptions</b> returns, the option list contains all options, regardless of constraints or other factors.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nn-prcomoem-iprintcorehelperps">IPrintCoreHelperPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-enumconstrainedoptions">IPrintCoreHelperPS::EnumConstrainedOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-enumfeatures">IPrintCoreHelperPS::EnumFeatures</a>
 

 

