---
UID: NC:storport.HW_INITIALIZE_TRACING
title: HW_INITIALIZE_TRACING (storport.h)
description: The HwStorInitializeTracing callback routine allows the Storport virtual miniport driver to set up tracing and any related resources.
old-location: storage\hwstorinitializetracing.htm
tech.root: storage
ms.assetid: e0d4ea58-415b-4ea4-9001-8a23ab44a1bf
ms.date: 03/29/2018
ms.keywords: HW_INITIALIZE_TRACING, HwStorInitializeTracing, HwStorInitializeTracing routine [Storage Devices], storage.hwstorinitializetracing, storport/HwStorInitializeTracing, storvmini_0c53c6e6-7c5c-4400-b923-c03a7756614f.xml
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
- UserDefined
api_location:
- Storport.h
api_name:
- HwStorInitializeTracing
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_INITIALIZE_TRACING callback function


## -description


The <b>HwStorInitializeTracing</b> callback routine allows the Storport virtual miniport driver to set up tracing and any related resources.


## -parameters




### -param Arg1

The first parameter that is passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinitialize">StorPortInitialize</a>.


### -param Arg2

The second parameter that is passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinitialize">StorPortInitialize</a>.


## -returns



None




## -remarks



The name <b>HwStorInitializeTracing</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_INITIALIZE_TRACING (
  _In_ PVOID  Arg1,
  _In_ PVOID  Arg2
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the Storport virtual miniport's <b>HwStorInitializeTracing</b> at PASSIVE_LEVEL.


#### Examples

To define an <b>HwStorInitializeTracing</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorInitializeTracing</b> callback routine that is named <i>MyHwInitializeTracing</i>, use the <b>HW_INITIALIZE_TRACING</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_INITIALIZE_TRACING MyHwInitializeTracing;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
MyHwInitializeTracing (
  _In_ PVOID  Arg1,
  _In_ PVOID  Arg2
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_INITIALIZE_TRACING</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_INITIALIZE_TRACING</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.

<div class="code"></div>


