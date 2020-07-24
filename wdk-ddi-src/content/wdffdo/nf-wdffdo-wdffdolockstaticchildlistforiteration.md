---
UID: NF:wdffdo.WdfFdoLockStaticChildListForIteration
title: WdfFdoLockStaticChildListForIteration function (wdffdo.h)
description: The WdfFdoLockStaticChildListForIteration method prepares the framework for retrieving items from the static child list that belongs to a specified parent device.
old-location: wdf\wdffdolockstaticchildlistforiteration.htm
tech.root: wdf
ms.assetid: 79ff278c-a30e-49f6-9146-badf24970de2
ms.date: 02/26/2018
keywords: ["WdfFdoLockStaticChildListForIteration function"]
ms.keywords: DFDeviceObjectFdoPdoRef_d20e71b2-fc76-4eb5-9911-bb7014467b4e.xml, WdfFdoLockStaticChildListForIteration, WdfFdoLockStaticChildListForIteration method, kmdf.wdffdolockstaticchildlistforiteration, wdf.wdffdolockstaticchildlistforiteration, wdffdo/WdfFdoLockStaticChildListForIteration
f1_keywords:
 - "wdffdo/WdfFdoLockStaticChildListForIteration"
 - "WdfFdoLockStaticChildListForIteration"
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfFdoLockStaticChildListForIteration
targetos: Windows
req.typenames: 
---

# WdfFdoLockStaticChildListForIteration function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFdoLockStaticChildListForIteration</b> method prepares the framework for retrieving items from the static child list that belongs to a specified parent device. 


## -parameters




### -param Fdo [in]

A handle to a framework device object that represents the parent device.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




Bus drivers that use static bus enumeration can call <b>WdfFdoLockStaticChildListForIteration</b>. 

After calling <b>WdfFdoLockStaticChildListForIteration</b>, the driver can repeatedly call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoretrievenextstaticchild">WdfFdoRetrieveNextStaticChild</a> to obtain information about each child device in the child list. 

After the driver has finished calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoretrievenextstaticchild">WdfFdoRetrieveNextStaticChild</a>, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdounlockstaticchildlistfromiteration">WdfFdoUnlockStaticChildListFromIteration</a>.

If the driver makes changes to the child list after calling <b>WdfFdoLockStaticChildListForIteration</b>, the framework stores all of the changes and notifies the Plug and Play (PnP) manager of the changes when the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdounlockstaticchildlistfromiteration">WdfFdoUnlockStaticChildListFromIteration</a>.

The driver can nest calls to <b>WdfFdoLockStaticChildListForIteration</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdounlockstaticchildlistfromiteration">WdfFdoUnlockStaticChildListFromIteration</a>. If the driver nests calls to these methods, the framework stores all of the changes until the last call to <b>WdfFdoUnlockStaticChildListFromIteration</b>.

For more information about static child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/static-enumeration">Static Enumeration</a>.


#### Examples

For a code example that uses <b>WdfFdoLockStaticChildListForIteration</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoretrievenextstaticchild">WdfFdoRetrieveNextStaticChild</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdounlockstaticchildlistfromiteration">WdfFdoUnlockStaticChildListFromIteration</a>
 

 

