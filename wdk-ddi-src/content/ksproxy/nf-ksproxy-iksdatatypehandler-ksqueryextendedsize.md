---
UID: NF:ksproxy.IKsDataTypeHandler.KsQueryExtendedSize
title: IKsDataTypeHandler::KsQueryExtendedSize (ksproxy.h)
description: The KsQueryExtendedSize method retrieves extended header information required for input and output (I/O) operations.
old-location: stream\iksdatatypehandler_ksqueryextendedsize.htm
tech.root: stream
ms.assetid: 14d03e6f-d02c-4b39-8f21-b339c65fb036
ms.date: 04/23/2018
keywords: ["IKsDataTypeHandler::KsQueryExtendedSize"]
ms.keywords: IKsDataTypeHandler interface [Streaming Media Devices],KsQueryExtendedSize method, IKsDataTypeHandler.KsQueryExtendedSize, IKsDataTypeHandler::KsQueryExtendedSize, KsQueryExtendedSize, KsQueryExtendedSize method [Streaming Media Devices], KsQueryExtendedSize method [Streaming Media Devices],IKsDataTypeHandler interface, ksproxy/IKsDataTypeHandler::KsQueryExtendedSize, ksproxy_b76ac8b2-6bf7-4839-9783-35c865efeb29.xml, stream.iksdatatypehandler_ksqueryextendedsize
f1_keywords:
 - "ksproxy/IKsDataTypeHandler.KsQueryExtendedSize"
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
- COM
api_location:
- ksproxy.h
api_name:
- IKsDataTypeHandler.KsQueryExtendedSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsDataTypeHandler::KsQueryExtendedSize


## -description


The <b>KsQueryExtendedSize</b> method retrieves extended header information required for input and output (I/O) operations. 


## -parameters




### -param ExtendedSize [out]

Pointer to a variable that receives the extended header size in bytes.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



If <b>KsQueryExtendedSize</b> returns zero at <i>ExtendedSize</i>, clients should not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-ksprepareiooperation">KsPrepareIoOperation</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-kscompleteiooperation">KsCompleteIoOperation</a> methods of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksdatatypehandler">IKsDataTypeHandler</a> interface because I/O preparation and completion operations are not required. For all other values that <b>KsQueryExtendedSize</b> returns at <i>ExtendedSize</i>, clients should allocate memory space for the extended stream header per the returned value and call <b>KsPrepareIoOperation</b> and <b>KsCompleteIoOperation</b> to prepare and complete the I/O operation associated with the header.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-kscompleteiooperation">IKsDataTypeHandler::KsCompleteIoOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-ksprepareiooperation">IKsDataTypeHandler::KsPrepareIoOperation</a>
 

 

