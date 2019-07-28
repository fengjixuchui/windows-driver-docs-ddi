---
UID: NS:wdm._TRANSACTION_BASIC_INFORMATION
title: _TRANSACTION_BASIC_INFORMATION (wdm.h)
description: The TRANSACTION_BASIC_INFORMATION structure contains information about a transaction object.
old-location: kernel\transaction_basic_information.htm
tech.root: kernel
ms.assetid: 79dd9ff3-2a5f-457a-8a8a-4963a799055c
ms.date: 04/30/2018
ms.keywords: "*PTRANSACTION_BASIC_INFORMATION, PTRANSACTION_BASIC_INFORMATION, PTRANSACTION_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTION_BASIC_INFORMATION, TRANSACTION_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTION_BASIC_INFORMATION, kernel.transaction_basic_information, ktm_ref_3246b7cb-244e-4772-b3ca-bfd69e973f12.xml, wdm/PTRANSACTION_BASIC_INFORMATION, wdm/TRANSACTION_BASIC_INFORMATION"
ms.topic: struct
f1_keywords:
 - "wdm/TRANSACTION_BASIC_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
- wdm.h
api_name:
- TRANSACTION_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: TRANSACTION_BASIC_INFORMATION, *PTRANSACTION_BASIC_INFORMATION
---

# _TRANSACTION_BASIC_INFORMATION structure


## -description


The <b>TRANSACTION_BASIC_INFORMATION</b> structure contains information about a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-objects">transaction object</a>.


## -struct-fields




### -field TransactionId

A GUID that KTM has assigned to the transaction object. This value is also known as the transaction's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ktm-objects">unit of work (UOW) identifier</a>.


### -field State

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_transaction_state">TRANSACTION_STATE</a>-typed value that specifies the transaction's current state.


### -field Outcome

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_transaction_outcome">TRANSACTION_OUTCOME</a>-typed value that specifies the transaction's outcome (result).


## -remarks



The <b>TRANSACTION_BASIC_INFORMATION</b> structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a> routine. This routine fills in the structure's members.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_transaction_outcome">TRANSACTION_OUTCOME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_transaction_state">TRANSACTION_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmgettransactionid">TmGetTransactionId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a>
 

 

