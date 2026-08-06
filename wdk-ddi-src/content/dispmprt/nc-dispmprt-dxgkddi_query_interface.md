---
UID: NC:dispmprt.DXGKDDI_QUERY_INTERFACE
title: DXGKDDI_QUERY_INTERFACE (dispmprt.h)
description: Learn more about the DXGKDDI_QUERY_INTERFACE callback function.
tech.root: display
ms.date: 04/05/2024
keywords: ["DXGKDDI_QUERY_INTERFACE callback function"]
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_QUERY_INTERFACE
 - dispmprt/DXGKDDI_QUERY_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_QUERY_INTERFACE
---

# DXGKDDI_QUERY_INTERFACE callback function

## -description

The **DxgkDdiQueryInterface** function returns a functional interface that is implemented by the display miniport driver.

## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param QueryInterface [in]

A pointer to a [**QUERY_INTERFACE**](../video/ns-video-_query_interface.md) structure in which the display miniport driver should return information about the interface it supports.

## -returns

**DxgkDdiQueryInterface** returns STATUS_SUCCESS if it succeeds; otherwise, it returns an appropriate NTSTATUS code. If a display miniport driver doesn't support the requested interface, it must return STATUS_NOT_SUPPORTED. By returning STATUS_NOT_SUPPORTED, the display miniport driver informs the operating system to pass the query on to the next driver.

## -remarks

**DxgkDdiQueryInterface** exposes a communication mechanism between the display miniport driver and the driver of a child device (for example, a video capture device). A display miniport driver that exposes such a mechanism should implement this function.

**DxgkDdiQueryInterface** should fill in the members of the [**INTERFACE**](../wdm/ns-wdm-_interface.md) structure that **QueryInterface->Interface** points to as follows:

* Set **Size** to the number of bytes in the INTERFACE structure. This value must not exceed the number of bytes specified by **QueryInterface**->**Size**.

* Set **Version** to the version of the interface being returned by the display miniport driver. The display miniport driver should best match the version requested by the child driver in **QueryInterface**->**Version**.

* Set **Context** to point to a display miniport driver-defined context for the interface. Typically, a display miniport driver would set **Context** to the handle to the display adapter's context block that is identified by **MiniportDeviceContext**.

* Initialize **InterfaceReference** and **InterfaceDereference** to point to the display miniport driver-implemented reference and dereference routines for this interface.

* Initialize all additional interface-specific members to point to the appropriate routines of the interface being exposed.

**DxgkDdiQueryInterface** runs at IRQL = PASSIVE_LEVEL and should be made pageable.

## -see-also

[**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiQueryChildRelations**](nc-dispmprt-dxgkddi_query_child_relations.md)

[**QUERY_INTERFACE**](../video/ns-video-_query_interface.md)
