---
UID: NS:d3dkmddi._DXGK_POWER_COMPONENT_FLAGS
title: _DXGK_POWER_COMPONENT_FLAGS (d3dkmddi.h)
description: Describes state transition information about a power component.
old-location: display\dxgk_power_component_flags.htm
ms.assetid: aa8cce5b-d582-4c5b-99e2-fad1f0e80128
ms.date: 05/10/2018
keywords: ["_DXGK_POWER_COMPONENT_FLAGS structure"]
ms.keywords: DXGK_POWER_COMPONENT_FLAGS, DXGK_POWER_COMPONENT_FLAGS structure [Display Devices], _DXGK_POWER_COMPONENT_FLAGS, d3dkmddi/DXGK_POWER_COMPONENT_FLAGS, display.dxgk_power_component_flags
f1_keywords:
 - "d3dkmddi/DXGK_POWER_COMPONENT_FLAGS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- HeaderDef
api_location:
- D3dkmddi.h
api_name:
- DXGK_POWER_COMPONENT_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_POWER_COMPONENT_FLAGS
---

# _DXGK_POWER_COMPONENT_FLAGS structure


## -description


Describes state transition information about a power component.


## -struct-fields




### -field Reserved0

Reserved for system use and should be set to zero.


### -field DriverCompletesFStateTransition

If set, indicates that the display miniport driver will call the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_completefstatetransition">DxgkCbCompleteFStateTransition</a> function for a registered power component when the component completes an F-state transition.

For more information, see Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_completefstatetransition">DxgkCbCompleteFStateTransition</a> function.


### -field TransitionTo_F0_OnDx

If set, indicates that the Windows power management framework will place a registered power component into the F0 power state during device power state (Dx) transitions.

If set, during a Dx transition the power manager places the component into the F0 state before it dispatches a Dx IRP to the device stack. The power manager keeps the component in the F0 state until the D0 IRP is completed.


### -field NoDebounce

 


### -field ActiveInD3

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that <b>DXGK_POWER_COMPONENT_FLAGS</b> contains that can hold a 32-bit value that identifies information about the power component.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_completefstatetransition">DxgkCbCompleteFStateTransition</a>
 

 

