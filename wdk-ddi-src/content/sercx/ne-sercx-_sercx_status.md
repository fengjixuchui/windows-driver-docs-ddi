---
UID: NE:sercx._SERCX_STATUS
title: _SERCX_STATUS (sercx.h)
description: The SERCX_STATUS enumeration indicates the status of a serial receive or transmit operation.
old-location: serports\sercx_status.htm
tech.root: serports
ms.assetid: 7EF129C7-25C3-49D2-8FC5-FFA1C4E77935
ms.date: 04/23/2018
keywords: ["SERCX_STATUS enumeration"]
ms.keywords: "*PSERCX_STATUS, 1/SERCX_STATUS, 1/SerCxStatusCancelled, 1/SerCxStatusSuccess, 1/SerCxStatusTimeout, SERCX_STATUS, SERCX_STATUS enumeration [Serial Ports], SerCxStatusCancelled, SerCxStatusSuccess, SerCxStatusTimeout, _SERCX_STATUS, serports.sercx_status"
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: 
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
f1_keywords:
 - _SERCX_STATUS
 - sercx/_SERCX_STATUS
 - PSERCX_STATUS
 - sercx/PSERCX_STATUS
 - SERCX_STATUS
 - sercx/SERCX_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1.0\Sercx.h
api_name:
 - SERCX_STATUS
---

# _SERCX_STATUS enumeration


## -description

The <b>SERCX_STATUS</b> enumeration indicates the status of a serial receive or transmit operation.

## -enum-fields

### -field SerCxStatusSuccess

The operation is proceeding successfully.

### -field SerCxStatusCancelled

The operation was canceled.

### -field SerCxStatusTimeout

The operation timed out. This enumeration value applies only to read interval time-outs for receive operations. For more information, see the description of the <b>ReadIntervalTimeout</b> member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxprogressreceive">SerCxProgressReceive</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxprogresstransmit">SerCxProgressTransmit</a> methods have parameters that are <b>SERCX_STATUS</b> enumeration values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxprogressreceive">SerCxProgressReceive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxprogresstransmit">SerCxProgressTransmit</a>

