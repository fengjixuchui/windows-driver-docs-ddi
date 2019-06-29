---
UID: NS:dot11wdi._NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
title: _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS (dot11wdi.h)
description: The NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure defines the set of handlers that a WDI miniport driver must implement.
old-location: netvista\ndis_miniport_driver_wdi_characteristics.htm
tech.root: netvista
ms.assetid: 2F69C228-FF2D-4277-A4C9-14FBADA1CD31
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, dot11wdi/NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, dot11wdi/PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, netvista.ndis_miniport_driver_wdi_characteristics"
ms.topic: struct
req.header: dot11wdi.h
req.include-header: Ndis.h
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
- HeaderDef
api_location:
- dot11wdi.h
api_name:
- NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, *PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
---

# _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure


## -description


The NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure defines the set of handlers that a WDI miniport driver must implement. It is used by the IHV driver to register additional handlers for the control path and the full set of handlers for the data path.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_WDI_CHARACTERISTICS.
     

To indicate the version of the NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_WDI_CHARACTERISTICS_REVISION_1.


### -field WdiVersion

The version of WDI used by the driver. Set this member to one of the following values:





#### WDI_VERSION_LATEST

The latest WDI version



#### WDI_VERSION_1_0_1

WDI version 1.0.1



#### WDI_VERSION_1_0

WDI version 1.0


### -field AllocateAdapterHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_allocate_adapter">MiniportWdiAllocateAdapter</a> handler function.


### -field FreeAdapterHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_free_adapter">MiniportWdiFreeAdapter</a> handler function.


### -field OpenAdapterHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_open_adapter">MiniportWdiOpenAdapter</a> handler function.


### -field CloseAdapterHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_close_adapter">MiniportWdiCloseAdapter</a> handler function.


### -field StartOperationHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_start_adapter_operation">MiniportWdiStartOperation</a> handler function.


### -field StopOperationHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_stop_adapter_operation">MiniportWdiStopOperation</a> handler function.


### -field PostPauseHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_post_adapter_pause">MiniportWdiPostAdapterPause</a> handler function.


### -field PostRestartHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_post_adapter_restart">MiniportWdiPostAdapterRestart</a> handler function.


### -field HangDiagnoseHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_adapter_hang_diagnose">MiniportWdiAdapterHangDiagnose</a> handler function.


### -field TalTxRxInitializeHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a> handler function.




### -field TalTxRxDeinitializeHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_deinitialize">MiniportWdiTalTxRxDeinitialize</a> handler function.




### -field LeIdleNotificationHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_idle_notification">MiniportWdiIdleNotification</a> handler function.




### -field LeCancelIdleNotificationHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_cancel_idle_notification">MiniportWdiCancelIdleNotification</a> handler function.



