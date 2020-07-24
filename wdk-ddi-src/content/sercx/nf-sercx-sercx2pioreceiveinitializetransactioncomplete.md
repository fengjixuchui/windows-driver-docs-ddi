---
UID: NF:sercx.SerCx2PioReceiveInitializeTransactionComplete
title: SerCx2PioReceiveInitializeTransactionComplete function (sercx.h)
description: The SerCx2PioReceiveInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new PIO-receive transaction.
old-location: serports\sercx2pioreceiveinitializetransactioncomplete.htm
tech.root: serports
ms.assetid: 66F8DA69-F4AD-45BE-A211-184E87882908
ms.date: 04/23/2018
keywords: ["SerCx2PioReceiveInitializeTransactionComplete function"]
ms.keywords: 2/SerCx2PioReceiveInitializeTransactionComplete, SerCx2PioReceiveInitializeTransactionComplete, SerCx2PioReceiveInitializeTransactionComplete method [Serial Ports], serports.sercx2pioreceiveinitializetransactioncomplete
f1_keywords:
 - "sercx/SerCx2PioReceiveInitializeTransactionComplete"
 - "SerCx2PioReceiveInitializeTransactionComplete"
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2PioReceiveInitializeTransactionComplete
targetos: Windows
req.typenames: 
---

# SerCx2PioReceiveInitializeTransactionComplete function


## -description


The <b>SerCx2PioReceiveInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new PIO-receive transaction.


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -remarks



Before SerCx2 starts a PIO-receive transaction, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_initialize_transaction">EvtSerCx2PioReceiveInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller hardware. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2PioReceiveInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2PioReceiveInitializeTransactionComplete</b> only in response to a call to the <i>EvtSerCx2PioReceiveInitializeTransaction</i> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265332(v=vs.85)">SerCx2 PIO-Receive Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_initialize_transaction">EvtSerCx2PioReceiveInitializeTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>
 

 

