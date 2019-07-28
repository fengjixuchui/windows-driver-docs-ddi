---
UID: NF:engextcpp.ExtRemoteData.GetPtr
title: ExtRemoteData::GetPtr (engextcpp.h)
description: The GetPtr method returns a pointer from the target's memory version of the ExtRemoteData object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.
old-location: debugger\extremotedata_getptr.htm
tech.root: debugger
ms.assetid: f9778881-9b53-49c5-9fe8-80f9a866b9af
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_6aea2145-72ce-4bdc-afb2-1fa360e643da.xml, ExtRemoteData class [Windows Debugging],GetPtr method, ExtRemoteData.GetPtr, ExtRemoteData::GetPtr, GetPtr, GetPtr method [Windows Debugging], GetPtr method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getptr
ms.topic: method
f1_keywords:
 - "engextcpp/ExtRemoteData.GetPtr"
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
- ExtRemoteData.GetPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteData::GetPtr


## -description


The <b>GetPtr</b> method returns a pointer from the target's memory version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.


## -parameters






## -returns



<b>GetPtr</b> returns a pointer from the target's memory.  As with all pointers, if the target uses 32-bit pointers, it is sign-extended to 64-bits.




## -remarks



The size of the memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getlongptr">ExtRemoteData::GetLongPtr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getulong">ExtRemoteData::GetUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getulong64">ExtRemoteData::GetUlong64</a>
 

 

