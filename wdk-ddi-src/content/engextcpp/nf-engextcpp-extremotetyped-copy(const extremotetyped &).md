---
UID: NF:engextcpp.ExtRemoteTyped.Copy(constExtRemoteTyped&)
title: ExtRemoteTyped::Copy(const ExtRemoteTyped &) (engextcpp.h)
description: The Copy method sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_copy_extremotetyped.htm
tech.root: debugger
ms.assetid: 7cc91411-3332-4a33-8873-832f71fd3281
ms.date: 05/03/2018
keywords: ["ExtRemoteTyped::Copy(const ExtRemoteTyped &)"]
ms.keywords: Copy, Copy method [Windows Debugging], Copy method [Windows Debugging],ExtRemoteTyped class, ExtRemoteTyped class [Windows Debugging],Copy method, ExtRemoteTyped.Copy, ExtRemoteTyped.Copy(const ExtRemoteTyped &), ExtRemoteTyped.Copy(const ExtRemoteTyped&), ExtRemoteTyped::Copy, ExtRemoteTyped::Copy(const ExtRemoteTyped &), debugger.extremotetyped_copy_extremotetyped
f1_keywords:
 - "engextcpp/ExtRemoteTyped.Copy"
 - "ExtRemoteTyped.Copy"
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
- ExtRemoteTyped.Copy
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteTyped::Copy(const ExtRemoteTyped &)


## -description


The <b>Copy</b> method sets the typed data represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> object by copying the information from another object.


## -parameters




### -param Typed [in, ref]

An existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> object that represents the typed data description to copy. This becomes the typed data represented by this object. 


## -returns



This method does not return a value.




## -remarks



The typed data can also be copied using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-copy">ExtRemoteTyped::Copy(Debug Typed Data)</a> method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff544357(v=vs.85)">ExtRemoteTyped::operator=</a>
 

 

