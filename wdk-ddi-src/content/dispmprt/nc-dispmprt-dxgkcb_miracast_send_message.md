---
UID: NC:dispmprt.DXGKCB_MIRACAST_SEND_MESSAGE
title: DXGKCB_MIRACAST_SEND_MESSAGE (dispmprt.h)
description: Sends an asynchronous message to the user-mode display driver.
old-location: display\dxgkcbmiracastsendmessage.htm
tech.root: display
ms.assetid: E8C3B9E3-854C-488D-809B-0F0893591352
ms.date: 05/10/2018
keywords: ["DXGKCB_MIRACAST_SEND_MESSAGE callback function"]
ms.keywords: DXGKCB_MIRACAST_SEND_MESSAGE, DXGKCB_MIRACAST_SEND_MESSAGE callback, DxgkCbMiracastSendMessage, DxgkCbMiracastSendMessage callback function [Display Devices], display.dxgkcbmiracastsendmessage, dispmprt/DxgkCbMiracastSendMessage
f1_keywords:
 - "dispmprt/DxgkCbMiracastSendMessage"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- Dispmprt.h
api_name:
- DxgkCbMiracastSendMessage
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_MIRACAST_SEND_MESSAGE callback function


## -description


Sends an asynchronous message to the user-mode display driver.


## -parameters




### -param MiracastHandle [in]

A driver-supplied handle to the Miracast display device. This handle was originally passed in the <b>MiracastHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_miracast_display_callbacks">DXGK_MIRACAST_DISPLAY_CALLBACKS</a> structure in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a> function.


### -param InputBufferSize [in]

The size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>.


### -param *pInputBuffer [in]

A pointer to the input buffer. <i>InputBufferSize</i> specifies the size of the buffer.

See Remarks for more info about the input buffer.


### -param OutputBufferSize

[in] The size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.

### -param *pOutputBuffer [out]

A pointer to the output buffer. <i>OutBufferSize</i> specifies the size of the buffer.

See Remarks for more info about the output buffer.


### -param pCallback [in, optional]

An optional pointer, supplied by the display miniport driver, to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message_callback">DxgkCbMiracastSendMessageCallback</a> callback function.

If the display miniport driver supplies the pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message_callback">DxgkCbMiracastSendMessageCallback</a>, then after the user-mode driver handles the message, the operating system sends a message to the user-mode driver asynchronously by calling <b>DxgkCbMiracastSendMessageCallback</b>.

See Return value and Remarks sections for more about calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message_callback">DxgkCbMiracastSendMessageCallback</a>.


### -param pCallbackContext [in, optional]

An optional driver-supplied pointer to the driver-supplied callback context. The operating system passes this context to the driver-supplied callback routine after the operation has completed.





## -returns



Returns <b>STATUS_PENDING</b> if it successfully delivers the message. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.

If the display miniport driver needs to know the status of message handling in user mode, it should supply the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message_callback">DxgkCbMiracastSendMessageCallback</a> function in the <i>pCallback</i> parameter and check the return status in that function's <i>pIoStatusBlock</i> parameter.




## -remarks



If the display miniport driver supplies the <i>pInputBuffer</i> and <i>pOutputBuffer</i> buffers, it is the driver’s responsibility to hold these two buffers until the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message_callback">DxgkCbMiracastSendMessageCallback</a> function is called. Otherwise, a random memory corruption issue can be created.

If the driver supplies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message_callback">DxgkCbMiracastSendMessageCallback</a> in the <i>pCallback</i> parameter, it's possible that <b>DxgkCbMiracastSendMessageCallback</b> will return before <b>DxgkCbMiracastSendMessage</b> returns.

<h3><a id="Example_calling_sequence"></a><a id="example_calling_sequence"></a><a id="EXAMPLE_CALLING_SEQUENCE"></a>Example calling sequence</h3>
Here's example code that shows how to use this function:

```cpp
typedef struct _CALLBACK_CONTEXT
{
    UCHAR InputBuffer[INPUT_BUFFER_SIZE];
    UCHAR OutputBuffer[OUTPUT_BUFFER_SIZE];
} CALLBACK_CONTEXT, *PCALLBACK_CONTEXT;

...

_IRQL_requires_(PASSIVE_LEVEL)
VOID
DriverCallbackFunction(
    _In_ PVOID Context,
    _In_ PIO_STATUS_BLOCK pIoStatusBlock
    )
{
    PCALLBACK_CONTEXT CallbackContex = (PCALLBACK_CONTEXT)Context;

    ExFreePool(CallbackContex);
}

...

    CallbackContex = (PCALLBACK_CONTEXT)ExAllocatePoolWithTag(
                            PagedPool,
                            sizeof(CALLBACK_CONTEXT),
                            DRIVER_TAG);

    if (CallbackContex == NULL)
    {
        return STATUS_NO_MEMORY;
    }

    RtlZeroMemory(CallbackContex, sizeof(CALLBACK_CONTEXT));

    CallbackContex->InputBuffer[0] = 0xaa;
    CallbackContex->InputBuffer[1] = 0x55;

    Status = 
      pDeviceContext->MiracastCallbacks.DxgkCbMiracastSendMessage(
          pDeviceContext->MiracastCallbacks.MiracastHandle,
          sizeof(CallbackContex->InputBuffer),
          CallbackContex->InputBuffer,
          sizeof(CallbackContex->OutputBuffer),
          CallbackContext->OutputBuffer,
          &DriverCallbackFunction,
          CallbackContex);

```


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_miracast_display_callbacks">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message_callback">DxgkCbMiracastSendMessageCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a>
 

 

