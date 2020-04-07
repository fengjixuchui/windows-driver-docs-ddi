---
UID: NC:wdm.PCW_CALLBACK
title: PCW_CALLBACK (wdm.h)
description: Providers can implement a PCW_CALLBACK function to receive notification when consumers perform certain actions, such as adding or removing counters from a query.
old-location: devtest\pcwcallback.htm
tech.root: devtest
ms.assetid: 5058fc17-1016-45bc-a6ea-5e2458824e7b
ms.date: 02/23/2018
keywords: ["PCW_CALLBACK callback function"]
ms.keywords: PCW_CALLBACK, PCW_CALLBACK callback, PcwCallback, PcwCallback callback function [Driver Development Tools], devtest.pcwcallback, km_pcw_f4d70925-0361-4aa6-9e4b-3f1e00a01535.xml, wdm/PcwCallback
f1_keywords:
 - "wdm/PcwCallback"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- PcwCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCW_CALLBACK callback function


## -description


Providers can implement a <i>PCW_CALLBACK</i> function to receive notification when consumers perform certain actions, such as adding or removing counters from a query. The Performance Counter Library (PERFLIB version 2.0) calls the <i>PCW_CALLBACK</i> function before the consumer's request completes.


## -parameters




### -param Type [in]

The callback type. Specifies why the callback is called. Possible values are PcwCallbackAddCounter, PcwCallbackRemoveCounter, PcwCallbackEnumerateInstances, and PcwCallbackCollectData. 


### -param Info [in]

A pointer to a PCW_CALLBACK_INFORMATION union that supplies details about the reason why the provider is being called.


### -param Context [in, optional]

A pointer to the callback context. This value is supplied by the provider when calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwregister">PcwRegister</a>.


## -returns



The <i>PCW_CALLBACK</i> callback function must return STATUS_SUCCESS if the callback was successfully executed. Otherwise, this callback function must return STATUS_UNSUCCESSFUL.




## -remarks



Providers that do not want to, or are unable to, create and destroy instances can register a callback function that is called when data is requested. For example, the following code examples show how the provider can use the <i>PCW_CALLBACK</i> callback function to enumerate and collect data.

The following code, from KcsCounters.h shows the inline function <b>KcsRegisterGeometricWave</b> that Ctrpp.exe generates from the manifest for the KCS sample in the WDK, Kcs.man. This function registers the counter set and takes a parameter to an optional custom <i>Callback</i> function. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EXTERN_C FORCEINLINE NTSTATUS
KcsRegisterGeometricWave(
    __in_opt PPCW_CALLBACK Callback,
    __in_opt PVOID CallbackContext
    )
{
    PCW_REGISTRATION_INFORMATION RegInfo;
    UNICODE_STRING Name = RTL_CONSTANT_STRING(L"Geometric Waves");
    PCW_COUNTER_DESCRIPTOR Descriptors[] = {
 { 1, 0, FIELD_OFFSET(GEOMETRIC_WAVE_VALUES, Triangle), RTL_FIELD_SIZE(GEOMETRIC_WAVE_VALUES, Triangle)},
 { 2, 0, FIELD_OFFSET(GEOMETRIC_WAVE_VALUES, Square), RTL_FIELD_SIZE(GEOMETRIC_WAVE_VALUES, Square)},
    };

    PAGED_CODE();

 RtlZeroMemory(&RegInfo, sizeof RegInfo);

 RegInfo.Version = PCW_CURRENT_VERSION;
 RegInfo.Counters = Descriptors;
 RegInfo.CounterCount = RTL_NUMBER_OF(Descriptors);
 RegInfo.Callback = Callback;
 RegInfo.CallbackContext = CallbackContext;
 RegInfo.Name = &Name;

 return PcwRegister(&KcsGeometricWave, &RegInfo);
}</pre>
</td>
</tr>
</table></span></div>
The provider can implement the <i>Callback</i> function to handle the requests. The following code example shows a <i>PCW_CALLBACK</i> function that enumerates and collects data. The function is named <i>KcsGeometricWaveCallback</i>. This function is then passed to the <i>KcsRegisterGeometricWave</i> in the <i>Callback</i> parameter.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS NTAPI
KcsGeometricWaveCallback (
    __in PCW_CALLBACK_TYPE Type,
    __in PPCW_CALLBACK_INFORMATION Info,
    __in_opt PVOID Context
    )

/*++

Routine Description:
    This function returns the list of counter instances and counter data.
Arguments:
    Type - Request type.
    Info - Buffer for returned data.
 Context - Not used.
Return Value:
 NTSTATUS indicating if the function succeeded.

--*/

{
    NTSTATUS Status;
    UNICODE_STRING UnicodeName;

    UNREFERENCED_PARAMETER(Context);

    PAGED_CODE();

 switch (Type) {
 case PcwCallbackEnumerateInstances:

        //
        // Instances are being enumerated, so we add them without values.
        //

 RtlInitUnicodeString(&UnicodeName, L"Small Wave");
        Status = KcsAddGeometricWave(Info->EnumerateInstances.Buffer,
                                     &UnicodeName,
                                     0,
                                     NULL);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

 RtlInitUnicodeString(&UnicodeName, L"Medium Wave");
        Status = KcsAddGeometricWave(Info->EnumerateInstances.Buffer,
                                     &UnicodeName,
                                     0,
                                     NULL);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

 RtlInitUnicodeString(&UnicodeName, L"Large Wave");
        Status = KcsAddGeometricWave(Info->EnumerateInstances.Buffer,
                                     &UnicodeName,
                                     0,
                                     NULL);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

 break;

 case PcwCallbackCollectData:

        //
        // Add values for 3 instances of Geometric Wave Counter Set.
        //

        Status = KcsAddGeometricInstance(Info->CollectData.Buffer,
 L"Small Wave",
                                         40,
                                         20);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

        Status = KcsAddGeometricInstance(Info->CollectData.Buffer,
 L"Medium Wave",
                                         30,
                                         40);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

        Status = KcsAddGeometricInstance(Info->CollectData.Buffer,
 L"Large Wave",
                                         20,
                                         60);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

 break;
    }

 return STATUS_SUCCESS;
}</pre>
</td>
</tr>
</table></span></div>
In the <i>DriverEntry</i> routine of the KCS example, the <i>KcsGeometricWaveCallback</i> function is specified as the <i>Callback</i> when <i>KcsRegisterGeometricWave</i> registers the counter set. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
    // Register Countersets.
    //

    Status = KcsRegisterGeometricWave(KcsGeometricWaveCallback, NULL);
 if (!NT_SUCCESS(Status)) {
 return Status;
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwregister">PcwRegister</a>



<a href="https://go.microsoft.com/fwlink/p/?linkid=144623">Performance Counter Library (PERFLIB)</a>
 

 

