---
UID: NF:engextcpp.ExtRemoteData.Write
title: ExtRemoteData::Write (engextcpp.h)
description: The Write method writes the data cached by the ExtRemoteData object to the region of memory on the target, represented by this object.
old-location: debugger\extremotedata_write.htm
tech.root: debugger
ms.assetid: 970c725b-4ea0-42b7-a373-83cb463cd80d
ms.date: 05/03/2018
keywords: ["ExtRemoteData::Write"]
ms.keywords: EngExtCpp_Ref_1288bed4-2f61-4af4-a226-5157a0622f42.xml, ExtRemoteData class [Windows Debugging],Write method, ExtRemoteData.Write, ExtRemoteData::Write, Write, Write method [Windows Debugging], Write method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_write
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
 - ExtRemoteData::Write
 - engextcpp/ExtRemoteData::Write
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.Write
---

# ExtRemoteData::Write


## -description

The <b>Write</b> method writes the data cached by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object to the region of memory on the target, represented by this object.

## -returns

This method does not return a value.

## -remarks

This method can be used to reset the region of memory on the target to the currently cached value that was previously read from the target.

It is also possible to directly set the value cached by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, for example:


```
ExtRemoteData ext_remote_data = new ExtRemoteData(address, sizeof(USHORT));
ext_remote_data.m_Data = (ULONG64) my_ushort;
ext_remote_data.Write();
```


## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-read">ExtRemoteData::Read</a>