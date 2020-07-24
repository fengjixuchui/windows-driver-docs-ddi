---
UID: NF:mbbcx.MbbDeviceReceiveDeviceServiceSessionData
title: MbbDeviceReceiveDeviceServiceSessionData function (mbbcx.h)
description: Client drivers call the MbbDeviceReceiveServiceSessionData method to pass received device service session data up to an application through the MBBCx framework.
tech.root: netvista
ms.assetid: 691429b7-4abd-4a79-80bb-9dade10fda86
ms.date: 06/29/2018
keywords: ["MbbDeviceReceiveDeviceServiceSessionData function"]
f1_keywords:
 - "mbbcx/MbbDeviceReceiveDeviceServiceSessionData"
 - "MbbDeviceReceiveDeviceServiceSessionData"
ms.keywords: MbbDeviceReceiveDeviceServiceSessionData
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: mbbcxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
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
- LibDef
api_location: 
- mbbcxstub.lib
api_name: 
- MbbDeviceReceiveDeviceServiceSessionData
targetos: Windows


ms.custom: RS5
---

# MbbDeviceReceiveDeviceServiceSessionData function


## -description



Client drivers call the **MbbDeviceReceiveServiceSessionData** method to pass received device service session data up to an application through the MBBCx framework.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param SessionId

The ID of the device service session obtained from a previous call to [**MbbAdapterGetSessionId**](nf-mbbcx-mbbadaptergetsessionid.md).

### -param Data

A driver-allocated WDFMEMORY object containing the data to pass to the application.

## -remarks

For more information, see [Handling device service sessions](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#handling-device-service-sessions).

### Example

The following example shows how a client driver might pass received DSS data to the framework's DSS receive handler.

```C++
VOID
MyReceiveDssData(
    _In_ PMY_DEVICE_CONTEXT DeviceContext,
    _In_ ULONG SessionId,
    _In_ PUCHAR InBuffer,
    _In_ ULONG InBufferSize
)
{
    NTSTATUS status = STATUS_SUCCESS;
    WDFMEMORY data;

    // Allocate the WDFMEMORY object from the received data buffer
    status = WdfMemoryAllocatePreallocated(WDF_NO_OBJECT_ATTRIBUTES,
                                            InBuffer,
                                            InBufferSize,
                                            &data);

    // Pass the received data to the framework
    if(NT_SUCCESS(status))
    {
        DeviceContext->DSSPacketsReceivedCount++;

        MbbDeviceReceiveServiceSessionData(DeviceContext->WdfDevice,
                                            SessionId,
                                            data);
        WdfObjectDelete(data);
    }
}
```

## -see-also
