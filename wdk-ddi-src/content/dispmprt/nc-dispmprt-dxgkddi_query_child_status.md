---
UID: NC:dispmprt.DXGKDDI_QUERY_CHILD_STATUS
title: DXGKDDI_QUERY_CHILD_STATUS (dispmprt.h)
description: The DxgkDdiQueryChildStatus function returns the status of an individual child device of a display adapter.
old-location: display\dxgkddiquerychildstatus.htm
tech.root: display
ms.assetid: 478e0c52-4324-4062-8e1e-381808b0f481
ms.date: 05/10/2018
ms.keywords: DXGKDDI_QUERY_CHILD_STATUS, DXGKDDI_QUERY_CHILD_STATUS callback, DmFunctions_3da69961-14d3-4bf8-9427-9c47d9bbfb89.xml, DxgkDdiQueryChildStatus, DxgkDdiQueryChildStatus callback function [Display Devices], display.dxgkddiquerychildstatus, dispmprt/DxgkDdiQueryChildStatus
ms.topic: callback
f1_keywords:
 - "dispmprt/DxgkDdiQueryChildStatus"
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiQueryChildStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_QUERY_CHILD_STATUS callback function


## -description


The <i>DxgkDdiQueryChildStatus</i> function returns the status of an individual child device of a display adapter.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param ChildStatus [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_status">DXGK_CHILD_STATUS</a> structure. The caller supplies ChildStatus->Type and ChildStatus->ChildUid. On return, the remaining structure member (a union) receives the requested status.


### -param NonDestructiveOnly [in]

A BOOLEAN value that specifies whether the display miniport driver is permitted to determine the requested status in a way that causes visual artifacts. If the caller sets this parameter to <b>TRUE</b>, then the display miniport driver is not permitted to cause artifacts. If the caller sets this parameter to <b>FALSE</b>, then the display miniport driver is permitted to cause artifacts.


## -returns



<i>DxgkDdiQueryChildStatus </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



During initialization, the display port driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a> to get a list of devices that are children of the display adapter represented by <i>MiniportDeviceContext</i>. Then for each child that has an HPD awareness value of <b>HpdAwarenessPolled</b> or <b>HpdAwarenessInterruptible</b>, the display port driver calls <i>DxgkDdiQueryChildStatus</i> to determine whether the child currently has hardware (for example a monitor) connected to it.

<i>DxgkDdiQueryChildStatus</i> must perform the following actions:

<ul>
<li>
If ChildStatus->Type is equal to <b>StatusConnection</b>, return a Boolean value in ChildStatus->HotPlug.Connected. Return <b>TRUE</b> if the child device identified by ChildStatus->ChildUid has external hardware connected to it; otherwise return <b>FALSE</b>.

</li>
<li>
If ChildStatus->Type is equal to <b>StatusRotation</b>, return (in ChildStatus->Rotation.Angle) the angle of rotation for the display connected to the child device identified by ChildStatus->ChildUid.

</li>
</ul>
<i>DxgkDdiQueryChildStatus</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_status">DXGK_CHILD_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ne-dispmprt-_dxgk_child_status_type">DXGK_CHILD_STATUS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>
 

 

