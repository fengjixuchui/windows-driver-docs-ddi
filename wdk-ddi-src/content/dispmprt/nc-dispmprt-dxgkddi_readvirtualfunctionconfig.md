---
UID: NC:dispmprt.DXGKDDI_READVIRTUALFUNCTIONCONFIG
title: DXGKDDI_READVIRTUALFUNCTIONCONFIG
author: windows-driver-content
description: This routine supplies the non-privileged virtual machine with the contents of a PCI Express SR-IOV Virtual Function’s configuration space values.
tech.root: display
ms.assetid: 5c812c6f-6adf-41f4-bb88-19375373e1f7
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_READVIRTUALFUNCTIONCONFIG callback function"]
f1_keywords:
 - "dispmprt/DXGKDDI_READVIRTUALFUNCTIONCONFIG"
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - dispmprt.h
api_name: 
 - DXGKDDI_READVIRTUALFUNCTIONCONFIG
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_READVIRTUALFUNCTIONCONFIG callback function

## -description

This routine supplies the non-privileged virtual machine with the contents of a PCI Express SR-IOV Virtual Function’s configuration space values. 

## -prototype

```
//Declaration

DXGKDDI_READVIRTUALFUNCTIONCONFIG DxgkddiReadvirtualfunctionconfig; 

// Definition

NTSTATUS DxgkddiReadvirtualfunctionconfig 
(
	HANDLE Context
	DXGKARG_READVIRTUALFUNCTIONCONFIG * pArgs
)
{...}

```

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

[in, out] A pointer to the DXGKARG_READVIRTUALFUNCTIONCONFIG structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks

Granting the guest partition direct access to the config space can be problematic, so this function provides a method of safely accessing the virtual functions config block. 

Note that this should return values as if read from the virtual device’s config block. Use of this interface may accomplish the read by handling it internally inside the driver supplying the interface, or by calling [GetVirtualFunctionData](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data) (from the PCI_VIRTUALIZATION_INTERFACE of the lower level PDO) or some combination of the two.

Kernel mode drivers should filter the request against the Virtual Function parameters and fail if there is access request out of the allowed range.

## -see-also
