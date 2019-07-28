---
UID: NC:dot11wdi.MINIPORT_WDI_RX_FLUSH
title: MINIPORT_WDI_RX_FLUSH (dot11wdi.h)
description: The MiniportWdiRxFlush handler function is issued after the MiniportWdiRxStop operation is completed. Upon receiving the flush request, the target/RxEngine must discard all unindicated frames on the port/adapter before indicating RxFlushConfirm.
old-location: netvista\miniportwdirxflush.htm
tech.root: netvista
ms.assetid: 76945A84-A6DB-4753-B04E-32249359B8C6
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_RX_FLUSH, MINIPORT_WDI_RX_FLUSH callback, MiniportWdiRxFlush, MiniportWdiRxFlush callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxFlush, netvista.miniportwdirxflush
ms.topic: callback
f1_keywords:
 - "dot11wdi/MiniportWdiRxFlush"
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- dot11wdi.h
api_name:
- MiniportWdiRxFlush
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_RX_FLUSH callback function


## -description


The 
  MiniportWdiRxFlush handler function is issued after the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_stop">MiniportWdiRxStop</a> operation is completed. Upon receiving the flush request, the target/RxEngine must  discard all unindicated frames on the port/adapter before indicating <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-ndis_wdi_rx_flush_confirm">RxFlushConfirm</a>.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_FLUSH</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>
 

 

