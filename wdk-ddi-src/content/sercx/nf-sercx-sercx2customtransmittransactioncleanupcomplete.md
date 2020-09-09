---
UID: NF:sercx.SerCx2CustomTransmitTransactionCleanupComplete
title: SerCx2CustomTransmitTransactionCleanupComplete function (sercx.h)
description: The SerCx2CustomTransmitTransactionCleanupComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-transmit transaction.
old-location: serports\sercx2customtransmittransactioncleanupcomplete.htm
tech.root: serports
ms.assetid: 5B9EBE82-A49A-4AD9-B07B-C0D17C5F3732
ms.date: 04/23/2018
keywords: ["SerCx2CustomTransmitTransactionCleanupComplete function"]
ms.keywords: 2/SerCx2CustomTransmitTransactionCleanupComplete, SerCx2CustomTransmitTransactionCleanupComplete, SerCx2CustomTransmitTransactionCleanupComplete method [Serial Ports], serports.sercx2customtransmittransactioncleanupcomplete
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SerCx2CustomTransmitTransactionCleanupComplete
 - sercx/SerCx2CustomTransmitTransactionCleanupComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2CustomTransmitTransactionCleanupComplete
---

# SerCx2CustomTransmitTransactionCleanupComplete function


## -description

The <b>SerCx2CustomTransmitTransactionCleanupComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-transmit transaction.

## -parameters

### -param CustomTransmitTransaction 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customtransmittransactioncreate">SerCx2CustomTransmitTransactionCreate</a> method to create this object.

## -remarks

After a custom-transmit transaction ends, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_transmit_transaction_cleanup">EvtSerCx2CustomTransmitTransactionCleanup</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should first do any clean-up work that is needed; then the driver must call <b>SerCx2CustomTransmitTransactionCleanupComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

A serial controller driver must call <b>SerCx2CustomTransmitTransactionCleanupComplete</b> only in response to a call to the <i>EvtSerCx2CustomTransmitTransactionCleanup</i> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265320(v=vs.85)">SerCx2 Custom-Transmit Transactions</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_transmit_transaction_cleanup">EvtSerCx2CustomTransmitTransactionCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMTRANSMITTRANSACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customtransmittransactioncreate">SerCx2CustomTransmitTransactionCreate</a>

