---
UID: NF:engextcpp.ExtRemoteList.Next
title: ExtRemoteList::Next (engextcpp.h)
description: The Next method changes the current item to the next item in the list.
old-location: debugger\extremotelist_next.htm
tech.root: debugger
ms.assetid: a1bf6f5b-c23d-40ed-b6e2-788066fcf0fc
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_27cc32ed-e2da-4041-8dd7-e2d5a0910c5e.xml, ExtRemoteList class [Windows Debugging],Next method, ExtRemoteList.Next, ExtRemoteList::Next, Next, Next method [Windows Debugging], Next method [Windows Debugging],ExtRemoteList class, debugger.extremotelist_next
ms.topic: method
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
- ExtRemoteList.Next
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteList::Next


## -description


The <b>Next</b> method changes the current item to the next item in the list.


## -parameters






## -returns



This method does not return a value.




## -remarks



If <b>Next</b> reaches the end of the list, subsequent calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotelist-hasnode">ExtRemoteList::HasNode</a> will return <code>false</code>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nl-engextcpp-extremotelist">ExtRemoteList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotelist-hasnode">ExtRemoteList::HasNode</a>
 

 

