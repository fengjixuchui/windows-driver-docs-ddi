---
UID: NF:wdm.TmRollbackEnlistment
title: TmRollbackEnlistment function (wdm.h)
description: The TmRollbackEnlistment routine rolls back a specified enlistment.
old-location: kernel\tmrollbackenlistment.htm
tech.root: kernel
ms.assetid: 1f089f2c-73e2-4c77-a398-0d369aafdf3a
ms.date: 04/30/2018
ms.keywords: TmRollbackEnlistment, TmRollbackEnlistment routine [Kernel-Mode Driver Architecture], kernel.tmrollbackenlistment, ktm_ref_adca7b83-77e1-4c1d-9ed8-aac2c713d43c.xml, wdm/TmRollbackEnlistment
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ext-MS-Win-ntos-tm-l1-1-0.dll
- tm.sys
api_name:
- TmRollbackEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmRollbackEnlistment function


## -description


The <b>TmRollbackEnlistment</b> routine rolls back a specified enlistment.


## -parameters




### -param Enlistment [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a> provided.


### -param TmVirtualClock [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>TmRollbackEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The enlistment cannot be rolled back.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



The <b>TmRollbackEnlistment</b> routine is a pointer-based version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntrollbackenlistment">ZwRollbackEnlistment</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-tmxxx-routines">Using TmXxx Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ptm_rm_notification">ResourceManagerNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmcreateenlistment">TmCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntrollbackenlistment">ZwRollbackEnlistment</a>
 

 

