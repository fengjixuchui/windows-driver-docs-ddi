---
UID: NF:prcomoem.IPrintCoreHelperPS.EnumFeatures
title: IPrintCoreHelperPS::EnumFeatures (prcomoem.h)
description: The IPrintCoreHelperPS::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
old-location: print\iprintcorehelperps_enumfeatures.htm
tech.root: print
ms.assetid: c67c15a4-3dbf-4317-b6d5-e52f426e7619
ms.date: 04/20/2018
ms.keywords: EnumFeatures, EnumFeatures method [Print Devices], EnumFeatures method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],EnumFeatures method, IPrintCoreHelperPS.EnumFeatures, IPrintCoreHelperPS::EnumFeatures, prcomoem/IPrintCoreHelperPS::EnumFeatures, print.iprintcorehelperps_enumfeatures, print_unidrv-pscript_allplugins_06a6f78b-fa5d-496e-b276-f32bba7c2502.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintCoreHelperPS.EnumFeatures"
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
- IPrintCoreHelperPS.EnumFeatures
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperPS::EnumFeatures


## -description


The<b> IPrintCoreHelperPS::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.


## -parameters




### -param pFeatureList [out]

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a <b>NULL</b> string.


### -param pdwNumFeatures [out]

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the <i>pFeatureList</i> parameter.


## -returns



<b>IPrintCoreHelperPS::EnumFeatures</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperps">IPrintCoreHelperPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-enumoptions">IPrintCoreHelperPS::EnumOptions</a>
 

 

