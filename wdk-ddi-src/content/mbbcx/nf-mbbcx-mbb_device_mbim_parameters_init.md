---
UID: NF:mbbcx.MBB_DEVICE_MBIM_PARAMETERS_INIT
title: MBB_DEVICE_MBIM_PARAMETERS_INIT function (mbbcx.h)
description: The MBB_DEVICE_MBIM_PARAMETERS_INIT method initializes a MBB_DEVICE_MBIM_PARAMETERS structure.
tech.root: netvista
ms.assetid: 679409cd-b6bd-4eb7-9f15-d8cd8216e785
ms.date: 02/06/2019
ms.topic: function
f1_keywords:
 - "mbbcx/-	MBB_DEVICE_MBIM_PARAMETERS_INIT"
ms.keywords: MBB_DEVICE_MBIM_PARAMETERS_INIT
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib: mbbcxstub.lib
req.dll:
req.irql: Any level as long as target memory is resident
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	LibDef
api_location: 
-	mbbcxstub.lib
api_name: 
-	MBB_DEVICE_MBIM_PARAMETERS_INIT
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# MBB_DEVICE_MBIM_PARAMETERS_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1903.

The **MBB_DEVICE_MBIM_PARAMETERS_INIT** method initializes a [**MBB_DEVICE_MBIM_PARAMETERS**](ns-mbbcx-_mbb_device_mbim_parameters.md) structure.

## -parameters

### -param MbimParameters

A pointer to the client driver-allocated [**MBB_DEVICE_MBIM_PARAMETERS**](ns-mbbcx-_mbb_device_mbim_parameters.md) structure to be initialized.

### -param Version

An [**MBB_MBIM_VERSION**](ne-mbbcx-_mbb_mbim_version.md) value that defines the version of the MBIM specification that the client driver supports. The value of this field must be **MBB_MBIM_VERSION1_0_ERRATA**.

### -param MaximumFragmentSize

The maximum size, in bytes, of MBIM control messages that the client driver can support.

### -param ExtendedVersion

An [**MBB_MBIM_EXTENDED_VERSION**](../mbbcx/ne-mbbcx-_mbb_mbim_extended_version.md) value that defines the version of the extended MBIM specification that the client driver supports. The value of this field must be **MBB_MBIM_EXTENDED_VERSION2_0**.

## -returns

This method does not return a value.

## -remarks

The client driver typically calls this method from its [*EVT_WDF_DEVICE_PREPARE_HARDWARE*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) event callback function in preparation for calling [**MbbDeviceSetMbimParameters**](nf-mbbcx-mbbdevicesetmbimparameters.md).

## -see-also

[Mobile Broadband (MBB) WDF class extension (MBBCx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/mobile-broadband-mbb-wdf-class-extension-mbbcx)
