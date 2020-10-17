---
UID: NF:engextcpp.ExtExtension.HasUnnamedArg
title: ExtExtension::HasUnnamedArg (engextcpp.h)
description: The HasUnnamedArg method indicates whether a specified unnamed argument is present in the command line used to invoke the current extension command.
old-location: debugger\hasunnamedarg.htm
tech.root: debugger
ms.assetid: 26917b2b-abbf-4d1b-b086-104390998a35
ms.date: 05/03/2018
keywords: ["ExtExtension::HasUnnamedArg"]
ms.keywords: EngExtCpp_Ref_5d191b46-bac6-415e-8c02-732ce433f950.xml, ExtExtension class [Windows Debugging],HasUnnamedArg method, ExtExtension.HasUnnamedArg, ExtExtension::HasUnnamedArg, HasUnnamedArg, HasUnnamedArg method [Windows Debugging], HasUnnamedArg method [Windows Debugging],ExtExtension class, debugger.hasunnamedarg
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
 - ExtExtension::HasUnnamedArg
 - engextcpp/ExtExtension::HasUnnamedArg
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Engextcpp.hpp
api_name:
 - ExtExtension.HasUnnamedArg
---

# ExtExtension::HasUnnamedArg


## -description

The <b>HasUnnamedArg</b> method indicates whether a specified unnamed argument is present in the command line used to invoke the current extension command.

## -parameters

### -param Index 

[in]
Specifies the index of the argument.  <i>Index</i> should be between zero and the number of unnamed arguments returned by <a href="/previous-versions/windows/hardware/previsioning-framework/ff548001(v=vs.85)">GetNumUnnamedArgs</a> minus one (unnamed arguments - 1).

## -returns

<i>HasUnnamedArg</i> returns <code>true</code> if the argument is present; <code>false</code> if it is not present.

## -remarks

This method will work for all types of unnamed arguments. For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.

## -see-also

<a href="/previous-versions/ff543981(v=vs.85)">ExtExtension</a>



<a href="/previous-versions/windows/hardware/previsioning-framework/ff548001(v=vs.85)">GetNumUnnamedArgs</a>