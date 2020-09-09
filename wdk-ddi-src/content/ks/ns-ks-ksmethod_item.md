---
UID: NS:ks.__unnamed_struct_69
title: KSMETHOD_ITEM (ks.h)
description: The KSMETHOD_ITEM structure describes a single method within a method set.
old-location: stream\ksmethod_item.htm
tech.root: stream
ms.assetid: 79119458-a6a7-433e-9306-d7a56ca056c2
ms.date: 04/23/2018
keywords: ["KSMETHOD_ITEM structure"]
ms.keywords: "*PKSMETHOD_ITEM, KSMETHOD_ITEM, KSMETHOD_ITEM structure [Streaming Media Devices], PKSMETHOD_ITEM, PKSMETHOD_ITEM structure pointer [Streaming Media Devices], ks-struct_e3c7b451-337f-4cc5-a5b8-a28aa9bea679.xml, ks/KSMETHOD_ITEM, ks/PKSMETHOD_ITEM, stream.ksmethod_item"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: KSMETHOD_ITEM, *PKSMETHOD_ITEM
f1_keywords:
 - PKSMETHOD_ITEM
 - ks/PKSMETHOD_ITEM
 - KSMETHOD_ITEM
 - ks/KSMETHOD_ITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSMETHOD_ITEM
---

# KSMETHOD_ITEM structure


## -description

The KSMETHOD_ITEM structure describes a single method within a method set.

## -struct-fields

### -field MethodId

Specifies the identifier of this method within its method set.

### -field MethodHandler

Pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler">KStrMethodHandler</a> callback routine.

### -field MethodSupported

Specifies if this method is supported or not.

### -field MinMethod

Specifies the minimum size of buffer required to specify the method completely. This size is at least <b>sizeof</b>(KSMETHOD) bytes.

### -field MinData

Specifies the minimum size buffer required to specify the method data buffer. This buffer is used to read and/or write information related to the method.

### -field SupportHandler

Pointer to a minidriver-supplied <a href="https://docs.microsoft.com/previous-versions/ff567206(v=vs.85)">KStrSupportHandler</a> callback routine.

### -field Flags

Specifies the request type of this method request.

<table>
<tr>
<th>Value</th>
<th>Type of method request</th>
</tr>
<tr>
<td>
KSMETHOD_TYPE_NONE

</td>
<td>
Indicates that the <i>Data</i> buffer of the handler is not expected to be used. For buffered methods, although space is allocated, no data is copied to or from the system buffer. When in source mode (KSMETHOD_TYPE_SOURCE), no MDL is created.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_READ

</td>
<td>
Indicates that parameters are expected to be read from the <i>Data</i> buffer of the handler. When buffered, data is copied to the system buffer. When in source mode, the data is probed and locked for <b>IoReadAccess</b>.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_WRITE

</td>
<td>
Indicates that parameters are expected to be written to the <i>Data</i> buffer of the handler. When buffered, data is copied from the system buffer. When in source mode, the data is probed and locked for <b>IoWriteAccess</b>.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_MODIFY

</td>
<td>
Indicates that parameters are expected to be read and written to the <i>Data</i> buffer of the handler. The data passed in is overwritten by the data returned. This might imply that a structure passed in could be merely updated. When buffered, the data is copied to the system buffer, and copied back when the IRP is completed. When in source mode, the data is probed and locked for <b>IoModifyAccess</b>.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_SOURCE

</td>
<td>
Indicates that the method is to be processed in source mode. An MDL is allocated and the data is probed and locked. To indicate a buffered method, OR this flag with other flags from this list.

</td>
</tr>
</table>

## -remarks

A minidriver uses the KSMETHOD_ITEM structure to define methods in a method set. The minidriver implements methods and uses the <b>MethodHandler</b> member to point to these methods. A client can then use the IOCTL_KS_METHOD request along with the KSMETHOD structure to execute methods on a kernel streaming object that the minidriver handles. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-methods">KS Methods</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksfastmethod_item">KSFASTMETHOD_ITEM</a>



<a href="https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)">KSMETHOD</a>



<a href="https://docs.microsoft.com/previous-versions/ff567206(v=vs.85)">KStrSupportHandler</a>

