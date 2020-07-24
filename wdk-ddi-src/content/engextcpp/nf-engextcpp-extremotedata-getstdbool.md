---
UID: NF:engextcpp.ExtRemoteData.GetStdBool
title: ExtRemoteData::GetStdBool (engextcpp.h)
description: The GetStdBool method returns a bool version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getstdbool.htm
tech.root: debugger
ms.assetid: f6a55181-7e1a-4af0-ac45-1991c42cdc87
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetStdBool"]
ms.keywords: EngExtCpp_Ref_65fe8202-99dc-45b3-9b38-5fca10341b1b.xml, ExtRemoteData class [Windows Debugging],GetStdBool method, ExtRemoteData.GetStdBool, ExtRemoteData::GetStdBool, GetStdBool, GetStdBool method [Windows Debugging], GetStdBool method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getstdbool
f1_keywords:
 - "engextcpp/ExtRemoteData.GetStdBool"
 - "ExtRemoteData.GetStdBool"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- engextcpp.hpp
api_name:
- ExtRemoteData.GetStdBool
targetos: Windows
req.typenames: 
---

# ExtRemoteData::GetStdBool


## -description


The <b>GetStdBool</b> method returns a <b>bool</b> version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -returns



The <b>bool</b> version ofthe <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(bool)</code>.

<div class="alert"><b>Note</b>    There are several different types that can be used to represent a Boolean value. <b>bool</b> is one of these types.  For the BOOLEAN type, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getboolean">ExtRemoteData::GetBoolean</a>.  For the BOOL type, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getw32bool">ExtRemoteData::GetW32Bool</a>.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getboolean">ExtRemoteData::GetBoolean</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getw32bool">ExtRemoteData::GetW32Bool</a>
 

 

