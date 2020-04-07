---
UID: NS:61883._FCP_SEND_REQUEST
title: _FCP_SEND_REQUEST (61883.h)
description: This structure is used for a send request.
old-location: ieee\fcp_send_request.htm
tech.root: IEEE
ms.assetid: 82F36729-57E0-49AB-8C2D-BCBA6EED33EE
ms.date: 02/15/2018
keywords: ["_FCP_SEND_REQUEST structure"]
ms.keywords: "*PFCP_REQUEST, *PFCP_SEND_REQUEST, 61883/FCP_SEND_REQUEST, 61883/PFCP_SEND_REQUEST, FCP_REQUEST, FCP_SEND_REQUEST, FCP_SEND_REQUEST structure [Buses], IEEE.fcp_send_request, PFCP_SEND_REQUEST, PFCP_SEND_REQUEST structure pointer [Buses], _FCP_SEND_REQUEST"
f1_keywords:
 - "61883/FCP_SEND_REQUEST"
req.header: 61883.h
req.include-header: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 61883.h
api_name:
- FCP_SEND_REQUEST
product:
- Windows
targetos: Windows
req.typenames: FCP_REQUEST, *PFCP_REQUEST, FCP_SEND_REQUEST, *PFCP_SEND_REQUEST
---

# _FCP_SEND_REQUEST structure


## -description


This structure is used for a send request. The  request sends an FCP request to the device. If the protocol driver is being used to represent a virtual device on the machine, the client driver must specify the <b>NodeAddress</b> member of FCP_SEND_REQUEST structure. This information is required in order to route the request to the proper node on the 1394 bus. If the protocol driver is being used to control a physical device, the 1394 bus driver determines the node address dynamically, and <b>NodeAddress</b> is not used.


## -struct-fields




### -field NodeAddress

On input, if the protocol driver is being used to control a virtual device, <b>NodeAddress</b> must contain the node address of the device to which this request is being sent so the protocol driver can route the request to the correct device. If the protocol driver is being used to control a physical device, <b>NodeAddress</b> is not used.


### -field Length

On input, the length of the Frame payload in bytes, including the FCP header.


### -field Frame

On input, a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_frame">FCP_FRAME</a> structure that contains the FCP request to send to the device.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp->IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
 

 

