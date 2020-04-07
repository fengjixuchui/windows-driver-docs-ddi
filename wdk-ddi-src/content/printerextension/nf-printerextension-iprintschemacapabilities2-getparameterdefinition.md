---
UID: NF:printerextension.IPrintSchemaCapabilities2.GetParameterDefinition
title: IPrintSchemaCapabilities2::GetParameterDefinition (printerextension.h)
description: The GetParameterDefinition method retrieves the IPrintSchemaParameterDefinition object, and it represents the <psf:ParameterDef> element in the PrintCapabilites XML.
old-location: print\iprintschemacapabilities2_getparameterdefinition.htm
tech.root: print
ms.assetid: 19C3A3C5-446B-48FD-8E77-2E0F787B16B1
ms.date: 04/20/2018
keywords: ["IPrintSchemaCapabilities2::GetParameterDefinition"]
ms.keywords: GetParameterDefinition, GetParameterDefinition method [Print Devices], GetParameterDefinition method [Print Devices],IPrintSchemaCapabilities2 interface, IPrintSchemaCapabilities2 interface [Print Devices],GetParameterDefinition method, IPrintSchemaCapabilities2.GetParameterDefinition, IPrintSchemaCapabilities2::GetParameterDefinition, print.iprintschemacapabilities2_getparameterdefinition, printerextension/IPrintSchemaCapabilities2::GetParameterDefinition
f1_keywords:
 - "printerextension/IPrintSchemaCapabilities2.GetParameterDefinition"
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- Printerextension.h
api_name:
- IPrintSchemaCapabilities2.GetParameterDefinition
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaCapabilities2::GetParameterDefinition


## -description

The <b>GetParameterDefinition</b> method retrieves the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaparameterdefinition">IPrintSchemaParameterDefinition</a> object, and it  represents the <psf:ParameterDef> element in the PrintCapabilites XML.

 The keyword name and keyword namespace URI specify the <b>IPrintSchemaParameterDefinition</b> object to be retrieved.

## -parameters

### -param bstrName [in]

The keyword name.

### -param bstrNamespaceUri [in]

The keyword namespace URI.

### -param ppParameterDefinition [out, retval]

The <b>IPrintSchemaParameterDefinition</b> object.

## -returns

The <b>GetParameterDefinition</b> method returns an <b>HRESULT</b> value. If the property call was not successful, it returns the appropriate <b>HRESULT</b> error code.

## -remarks

To be consistent with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature">IPrintSchemaCapabilities::GetFeature</a>, the <b>GetParameterDefinition</b> method works for any <psf:ParameterDef> element that is defined in the public keyword namespaces.  The <b>GetParameterDefinition</b> method also works for any IHV-defined  private keyword namespace that uses  either the StringParamType or the IntegerParamType data type.

When you use the <psf:ParameterDef> element with the QNameParamType or the DecimalParamType data type, <b>GetParameterDefinition</b> will return HRESULT_FROM_WIN32 (ERROR_NOT_SUPPORTED).

For more information about the data types that you can use with the <psf:ParameterDef> element, see section 2.1.3.1 of the [Print Schema Specification](https://download.microsoft.com/download/d/e/c/deca6e6b-3e81-48e7-b7ef-6d92a547d03c/print-schema-spec-2-0.zip).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities2">IPrintSchemaCapabilities2</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaparameterdefinition">IPrintSchemaParameterDefinition</a>

[Print Schema Specification](https://download.microsoft.com/download/d/e/c/deca6e6b-3e81-48e7-b7ef-6d92a547d03c/print-schema-spec-2-0.zip)
 
