---
UID: NF:wudfddi.IWDFNamedPropertyStore.SetNamedValue
title: IWDFNamedPropertyStore::SetNamedValue (wudfddi.h)
description: The SetNamedValue method sets the value of a property.
old-location: wdf\iwdfnamedpropertystore_setnamedvalue.htm
tech.root: wdf
ms.assetid: 1fd075c9-7d0e-4670-bac0-b7b8ba0a714f
ms.date: 02/26/2018
ms.keywords: IWDFNamedPropertyStore interface,SetNamedValue method, IWDFNamedPropertyStore.SetNamedValue, IWDFNamedPropertyStore::SetNamedValue, SetNamedValue, SetNamedValue method, SetNamedValue method,IWDFNamedPropertyStore interface, UMDFPropertyStoreObjectRef_00f9168d-5017-4b48-929c-fc9acfee5d24.xml, umdf.iwdfnamedpropertystore_setnamedvalue, wdf.iwdfnamedpropertystore_setnamedvalue, wudfddi/IWDFNamedPropertyStore::SetNamedValue
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFNamedPropertyStore.SetNamedValue"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFNamedPropertyStore.SetNamedValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFNamedPropertyStore::SetNamedValue


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetNamedValue</b> method sets the value of a property.


## -parameters




### -param pszName [in]

A pointer to a null-terminated string that contains the name of the property.


### -param pv [in]

A pointer to the value that the property is set to. 


## -returns



<b>SetNamedValue</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



The following variant types are supported for property values. The following table shows the types of values that the framework writes for particular variant types.

<table>
<tr>
<th>Variant type</th>
<th>Write</th>
</tr>
<tr>
<td>
VT_BSTR

</td>
<td rowspan="3">
Writes a string value.

</td>
</tr>
<tr>
<td>
VT_LPWSTR

</td>
</tr>
<tr>
<td>
VT_LPSTR

</td>
</tr>
<tr>
<td>
VT_I1

</td>
<td rowspan="7">
Writes an integer value.

</td>
</tr>
<tr>
<td>
VT_UI1

</td>
</tr>
<tr>
<td>
VT_I2

</td>
</tr>
<tr>
<td>
VT_UI2

</td>
</tr>
<tr>
<td>
VT_I4

</td>
</tr>
<tr>
<td>
VT_UI4

</td>
</tr>
<tr>
<td>
VT_UINT

</td>
</tr>
<tr>
<td>
VT_BLOB

</td>
<td>
Writes a binary value.

</td>
</tr>
<tr>
<td>
VT_VECTOR | VT_LPWSTR

</td>
<td>
Writes a string array.

</td>
</tr>
</table>
 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfnamedpropertystore">IWDFNamedPropertyStore</a>
 

 

