---
UID: NI:bthxddi.IOCTL_BTHX_WRITE_HCI
title: IOCTL_BTHX_WRITE_HCI (bthxddi.h)
description: IOCTL_BTHX_WRITE_HCI is used to write Bluetooth ACL Data and Commands to the transport layer.
old-location: bltooth\ioctl_bthx_hci_write.htm
tech.root: bltooth
ms.assetid: 77BBF6AC-F5FA-4795-8898-6DC02983F573
ms.date: 04/27/2018
keywords: ["IOCTL_BTHX_WRITE_HCI IOCTL"]
ms.keywords: IOCTL_BTHX_WRITE_HCI, IOCTL_BTHX_WRITE_HCI control, IOCTL_BTHX_WRITE_HCI control code [Bluetooth Devices], bltooth.ioctl_bthx_hci_write, bltooth.ioctl_bthx_write_hci, bthxddi/IOCTL_BTHX_WRITE_HCI
req.header: bthxddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
 - IOCTL_BTHX_WRITE_HCI
 - bthxddi/IOCTL_BTHX_WRITE_HCI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - BthXDDI.h
api_name:
 - IOCTL_BTHX_WRITE_HCI
---

# IOCTL_BTHX_WRITE_HCI IOCTL


## -description

IOCTL_BTHX_WRITE_HCI is used to write Bluetooth ACL Data and Commands to the transport layer.

## -ioctlparameters

### -input-buffer

Profile drivers should use KMDF and its <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> method to retrieve input parameters.  For example, to get the input buffer:

<code>Status = WdfRequestRetrieveInputMemory(_Request, &ReqInMemory);</code>

The buffer describes a <a href="/windows-hardware/drivers/ddi/bthxddi/ns-bthxddi-_bthx_hci_read_write_context">BTHX_HCI_READ_WRITE_CONTEXT</a> structure that specifies the type of write and the data associated with the write. 

Refer to the WDK Bluetooth samples for more information.

### -input-buffer-length

The length of the buffer is the size of the <b>BTHX_HCI_READ_WRITE_CONTEXT</b> structure.

### -output-buffer

Profile drivers should use KMDF and its <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> method to retrieve input parameters.  For example, to get the output buffer:

<code>Status = WdfRequestRetrieveOutputMemory(_Request, &ReqOutMemory);</code>

The buffer describes a ULONG of the number of bytes written for the input data specified in the <b>BTHX_HCI_READ_WRITE_CONTEXT</b> structure. 

Refer to the WDK Bluetooth samples for more information.

### -output-buffer-length

The length of the buffer is the size of a ULONG.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the number of bytes in the Output Parameter.

The 
      <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
</table>

## -remarks

The Bluetooth stack sends IOCTL_BTHX_WRITE_HCI to write HCI ACL data and HCI command to the controller.

The input buffer points to a BTHX_HCI_READ_WRITE_CONTEXT structure whose <b>DataLen</b> member specifies the number of bytes in the <b>Data</b> member. The <b>Type</b> member is set based on whether the packet is a command packet or an ACL data packet.