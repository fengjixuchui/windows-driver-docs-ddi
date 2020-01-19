---
UID: NF:scsiwmi.ScsiPortWmiSetData
title: ScsiPortWmiSetData function (scsiwmi.h)
description: The ScsiPortWmiSetData routine updates the WNODE_ALL_DATA structure within the request context to specify the position and length of the data for an instance.
old-location: storage\scsiportwmisetdata.htm
tech.root: storage
ms.assetid: eb4578c9-48e5-4113-ba58-a3d71052f782
ms.date: 03/29/2018
ms.keywords: ScsiPortWmiSetData, ScsiPortWmiSetData routine [Storage Devices], scsiprt_d35b9d5f-3bb4-4739-ab53-55a229eddb51.xml, scsiwmi/ScsiPortWmiSetData, storage.scsiportwmisetdata
ms.topic: function
f1_keywords:
 - "scsiwmi/ScsiPortWmiSetData"
req.header: scsiwmi.h
req.include-header: Miniport.h, Scsi.h
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
- HeaderDef
api_location:
- Scsiwmi.h
api_name:
- ScsiPortWmiSetData
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWmiSetData function


## -description


The <b>ScsiPortWmiSetData</b> routine updates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a> structure within the request context to specify the position and length of the data for an instance. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param RequestContext [in]

Pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a> that contains the request context for a WMI SRB. 


### -param InstanceIndex [in]

Contains an index that indicates the instance for which the position and length of the instance data are to be specified. 


### -param DataLength [in]

Specifies the number of bytes  of data required to describe the instance. 


### -param BufferAvail [out]

Must contain, on input, the number of bytes of buffer space in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a> structure that can be used for describing instance names and data. On return, this member contains the number of bytes of buffer space that remain. 

There are three SCSI Port WMI routines that return a value for the available buffer size in their <i>BufferAvail </i>parameter:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmisetinstancecount">ScsiPortWmiSetInstanceCount</a>


<b>ScsiPortWmiSetData</b>


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmisetinstancename">ScsiPortWmiSetInstanceName</a>


The miniport driver must call <b>ScsiPortWmiSetInstanceCount</b> first, but after <b>ScsiPortWmiSetInstanceCount</b> has been called, it does not matter in what order the minidriver calls <b>ScsiPortWmiSetData</b> and <b>ScsiPortWmiSetInstanceName</b>. When calling either <b>ScsiPortWmiSetData</b> or <b>ScsiPortWmiSetInstanceName</b>, the value passed to the routine in its <i>BufferAvail </i>parameter must be the same as the value returned in the <i>BufferAvail </i>parameter by the most recently called SCSI Port WMI routine. For instance, suppose the minidriver calls <b>ScsiPortWmiSetInstanceCount</b> first, and this routine returns a value of 1,000 in its <i>BufferAvail </i>parameter. Next, the minidriver calls <b>ScsiPortWmiSetData</b> which returns a value of 500 in its <i>BufferAvail </i>parameter. Finally, the minidriver calls <b>ScsiPortWmiSetInstanceName</b> which returns a value of 200 in its <i>BufferAvail </i>parameter. The initial value of 1,000 must be passed to <b>ScsiPortWmiSetData</b> in <i>BufferAvail</i>, and the value of 500 must be passed to <b>ScsiPortWmiSetInstanceName</b>. 

If there is not enough memory available to add new instance data of size <i>DataLength</i> bytes<i>, </i>a zero will be returned in the <i>BufferAvail</i> member. 


### -param SizeNeeded [in, out]

Indicates, on input,  the number of bytes needed to describe the entire WNODE <i>before </i>adding the descriptive data for the instance specified by <i>InstanceIndex</i>. On return, this member will contain the size of the WNODE, including the data for the new instance. 


## -returns



The <b>ScsiPortWmiSetData</b> routine returns a pointer to the buffer where the caller can store descriptive information about the instance identified by <i>InstanceIndex</i>. If <b>ScsiPortWmiSetData</b> cannot allocate enough memory for the instance data, or if the WNODE contained within the request context is not of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>, <b>ScsiPortWmiSetData</b> returns <b>NULL</b>. 




## -remarks



The minidriver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmisetinstancecount">ScsiPortWmiSetInstanceCount</a> before calling <b>ScsiPortWmiSetData</b>.

The parameter <b>RequestContext</b> points to a request context structure, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>, that contains information associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/implementing-wmi">Windows Management Instrumentation</a> (WMI) SCSI request block (SRB). The request context structure, in turn, contains one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/wmi-wnode-xxx-structures">WMI WNODE_XXX Structures</a> that is used by the WMI system to pass data between user-mode data consumers and kernel-mode data providers such as drivers. 

The <b>ScsiPortWmiSetData</b> routine requires the WNODE structure that is defined within the request context to be of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>. This is because <b>ScsiPortWmiSetData</b> can specify the location and length of the data buffers for any of the instances associated with a WMI data block. Unlike the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a> structure which contains information about a single instance, the WNODE_ALL_DATA structure contains an array of pointers to buffer areas for multiple instances, and <b>ScsiPortWmiSetData</b> uses the <i>InstanceIndex </i>parameter as an index into this array to initialize the appropriate array element for a particular instance. Each array element, once initialized, contains the size and location of a buffer area for an instance. 

The memory allocated for the request context must remain valid until after the miniport driver calls <b>ScsiPortWmiPostProcess</b>, and <b>ScsiPortWmiPostProcess</b> returns the final SRB status and buffer size. If the SRB can pend, the memory for the request context should be allocated from the SRB extension. If the SRB cannot pend, the memory can be allocated from a stack frame that does not go out of scope.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a>
 

 

