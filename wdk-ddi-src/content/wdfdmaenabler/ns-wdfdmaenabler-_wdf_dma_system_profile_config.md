---
UID: NS:wdfdmaenabler._WDF_DMA_SYSTEM_PROFILE_CONFIG
title: _WDF_DMA_SYSTEM_PROFILE_CONFIG (wdfdmaenabler.h)
description: The WDF_DMA_SYSTEM_PROFILE_CONFIG structure describes the hardware-specific settings related to a system-mode DMA enabler.
old-location: wdf\wdf_dma_system_profile_config.htm
tech.root: wdf
ms.assetid: 80131AB6-4A2B-4D99-9289-CE9FE26E0695
ms.date: 02/26/2018
ms.keywords: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, PWDF_DMA_SYSTEM_PROFILE_CONFIG, PWDF_DMA_SYSTEM_PROFILE_CONFIG structure pointer, WDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG structure, _WDF_DMA_SYSTEM_PROFILE_CONFIG, kmdf.wdf_dma_system_profile_config, wdf.wdf_dma_system_profile_config, wdfdmaenabler/PWDF_DMA_SYSTEM_PROFILE_CONFIG, wdfdmaenabler/WDF_DMA_SYSTEM_PROFILE_CONFIG"
ms.topic: struct
f1_keywords:
 - "wdfdmaenabler/WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
- wdfdmaenabler.h
api_name:
- WDF_DMA_SYSTEM_PROFILE_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
---

# _WDF_DMA_SYSTEM_PROFILE_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DMA_SYSTEM_PROFILE_CONFIG</b> structure describes the hardware-specific settings related to a system-mode DMA enabler.


## -struct-fields




### -field Size

The size of this structure in bytes.


### -field DemandMode

Specifies that the transfer is controlled by the device's DMA  
      request line specified in the <b>DmaDescriptor</b> member of this structure. See more information in Remarks.


### -field LoopedTransfer

Specifies that the DMA adapter should loop around the specified transfer if the length is greater than the size of the buffer.


### -field DmaWidth

The width of the register specified by <b>DeviceAddress</b>. Possible values are Width8Bits, Width16Bits, Width32Bits, and Width64Bits.


### -field DeviceAddress

The translated address to or from which the DMA controller transfers. The driver can specify an offset from this base address on each transaction by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetdeviceaddressoffset">WdfDmaTransactionSetDeviceAddressOffset</a>.


### -field DmaDescriptor

The translated resource descriptor for the DMA channel assigned 
      the device during <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>. This provides the DMA request line for the adapter.


## -remarks



The driver provides this structure to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile">WdfDmaEnablerConfigureSystemProfile</a> after creating a system-profile DMA enabler.

Typically, drivers set <b>DemandMode</b> to TRUE.   The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> callback function then programs the device to assert its DMA request line and initiate the transfer.  In this case, the transfer might begin while <i>EvtProgramDma</i> is still running.

The driver must ensure that the device's DMA request line is not asserted before the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> callback function begins execution. Otherwise, it is possible for the DMA transfer to begin before the framework calls <i>EvtProgramDma</i>.


If <b>DemandMode</b> is set to FALSE, the DMA transfer may begin before the framework calls the driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> function. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdf_dma_system_profile_config_init">WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile">WdfDmaEnablerConfigureSystemProfile</a>
 

 

