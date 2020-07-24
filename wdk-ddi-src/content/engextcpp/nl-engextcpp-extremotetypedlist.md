---
UID: NL:engextcpp.ExtRemoteTypedList
title: ExtRemoteTypedList (engextcpp.h)
description: The ExtRemoteTypedList class extends the ExtRemoteList class. The ExtRemoteTypedList class adds type information allowing each item in the list to be represented by an instance of the ExtRemoteTyped class.
old-location: debugger\extremotetypedlist.htm
tech.root: debugger
ms.assetid: a7b87f06-491a-4b41-a355-0f2806c0dd8a
ms.date: 05/03/2018
keywords: ["ExtRemoteTypedList class"]
ms.keywords: EngExtCpp_Ref_5e1242e6-5704-4b87-85e1-b02a41fc4243.xml, ExtRemoteTypedList, ExtRemoteTypedList class [Windows Debugging], ExtRemoteTypedList class [Windows Debugging],described, debugger.extremotetypedlist, engextcpp/ExtRemoteTypedList
f1_keywords:
 - "engextcpp/ExtRemoteTypedList"
 - "ExtRemoteTypedList"
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Windows
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
- ExtRemoteTypedList
targetos: Windows
req.typenames: 
---

# ExtRemoteTypedList class


## -description


The <b>ExtRemoteTypedList</b> class extends the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotelist">ExtRemoteList</a> class.  The <b>ExtRemoteTypedList</b> class adds type information allowing each item in the list to be represented by an instance of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> class.

The <b>ExtRemoteTypedList</b> class includes the following constructors and methods:
<dl>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList::ExtRemoteTypedList(ExtRemoteData)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList::ExtRemoteTypedList(ULONG64)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-settypeandlink">SetTypeAndLink</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-gettypednodeptr">GetTypedNodePtr</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-gettypednode">GetTypedNode</a>


</dd>
</dl><pre class="syntax" xml:space="preserve"><code>class ExtRemoteTypedList : public ExtRemoteList
{
public:
    PCSTR  m_Type;
    ULONG64  m_TypeModBase;
    ULONG  m_TypeId;
};</code></pre>
<dl>
<dt><a id="m_Type"></a><a id="m_type"></a><a id="M_TYPE"></a><b>m_Type</b></dt>
<dd>
The type name for the list items.  <i>Type</i> can include a module qualifier (for example, <b>mymodule!mytype</b>).  If <b>m_TypeId</b> is not zero, <i>Type</i> is not used.

</dd>
<dt><a id="m_TypeModBase"></a><a id="m_typemodbase"></a><a id="M_TYPEMODBASE"></a><b>m_TypeModBase</b></dt>
<dd>
The location in the target's memory of the base address of the module that contains the type specified by <b>m_TypeId</b>.  If <b>m_TypeId</b> is zero, <b>m_TypeModBase</b> is not used.

</dd>
<dt><a id="m_TypeId"></a><a id="m_typeid"></a><a id="M_TYPEID"></a><b>m_TypeId</b></dt>
<dd>
The type ID of the type relative to the module specified by <b>m_TypeModBase</b>.  If <b>m_TypeId</b> is zero, <b>m_Type</b> is used to specify the type of the list items.

</dd>
</dl>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotelist">ExtRemoteList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList::ExtRemoteTypedList(ExtRemoteData)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList::ExtRemoteTypedList(ULONG64)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-gettypednode">GetTypedNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-gettypednodeptr">GetTypedNodePtr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-settypeandlink">SetTypeAndLink</a>
 

 

