---
UID: NC:wdm.EX_CALLBACK_FUNCTION
title: EX_CALLBACK_FUNCTION (wdm.h)
description: A filter driver's RegistryCallback routine can monitor, block, or modify a registry operation.
old-location: kernel\registrycallback.htm
tech.root: kernel
ms.assetid: 220ce3b8-2820-4753-9659-5ce7b4f4f32d
ms.date: 04/30/2018
keywords: ["EX_CALLBACK_FUNCTION callback function"]
ms.keywords: DrvrRtns_988f8f3d-4ee8-4351-8fc0-703a88bd8421.xml, EX_CALLBACK_FUNCTION, RegistryCallback, RegistryCallback routine [Kernel-Mode Driver Architecture], kernel.registrycallback, wdm/RegistryCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows XP (see Return Value section).
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
req.irql: Called at PASSIVE_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - EX_CALLBACK_FUNCTION
 - wdm/EX_CALLBACK_FUNCTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - RegistryCallback
---

# EX_CALLBACK_FUNCTION callback function


## -description

A filter driver's <i>RegistryCallback</i> routine can monitor, block, or modify a registry operation.

## -parameters

### -param CallbackContext 

[in]
The value that the driver passed as the <i>Context</i> parameter to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a> when it registered this <i>RegistryCallback</i> routine.

### -param Argument1 

[in, optional]
A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_reg_notify_class">REG_NOTIFY_CLASS</a>-typed value that identifies the type of registry operation that is being performed and whether the <i>RegistryCallback</i> routine is being called before or after the registry operation is performed.

### -param Argument2 

[in, optional]
A pointer to a structure that contains information that is specific to the type of registry operation. The structure type depends on the REG_NOTIFY_CLASS-typed value for <i>Argument1</i>, as shown in the following table. For information about which REG_NOTIFY_CLASS-typed values are available for which operating system versions, see <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_reg_notify_class">REG_NOTIFY_CLASS</a>.

| **REG_NOTIFY_CLASS Value** | **Structure Type** | 
|:--|:--|
| **RegNtDeleteKey** | [REG_DELETE_KEY_INFORMATION](./ns-wdm-_reg_delete_key_information.md)  | 
| **RegNtPreDeleteKey** | [REG_DELETE_KEY_INFORMATION](./ns-wdm-_reg_delete_key_information.md)  | 
| **RegNtPostDeleteKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtSetValueKey** | [REG_SET_VALUE_KEY_INFORMATION](./ns-wdm-_reg_set_value_key_information.md)  | 
| **RegNtPreSetValueKey** | [REG_SET_VALUE_KEY_INFORMATION](./ns-wdm-_reg_set_value_key_information.md)  | 
| **RegNtPostSetValueKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtDeleteValueKey** | [REG_DELETE_VALUE_KEY_INFORMATION](./ns-wdm-_reg_delete_value_key_information.md)  | 
| **RegNtPreDeleteValueKey** | [REG_DELETE_VALUE_KEY_INFORMATION](./ns-wdm-_reg_delete_value_key_information.md)  | 
| **RegNtPostDeleteValueKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtSetInformationKey** | [REG_SET_INFORMATION_KEY_INFORMATION](./ns-wdm-_reg_set_information_key_information.md)  | 
| **RegNtPreSetInformationKey** | [REG_SET_INFORMATION_KEY_INFORMATION](./ns-wdm-_reg_set_information_key_information.md)  | 
| **RegNtPostSetInformationKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtRenameKey** | [REG_RENAME_KEY_INFORMATION](./ns-wdm-_reg_rename_key_information.md)  | 
| **RegNtPreRenameKey** | [REG_RENAME_KEY_INFORMATION](./ns-wdm-_reg_rename_key_information.md)  | 
| **RegNtPostRenameKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtEnumerateKey** | [REG_ENUMERATE_KEY_INFORMATION](./ns-wdm-_reg_enumerate_key_information.md)  | 
| **RegNtPreEnumerateKey** | [REG_ENUMERATE_KEY_INFORMATION](./ns-wdm-_reg_enumerate_key_information.md)  | 
| **RegNtPostEnumerateKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtEnumerateValueKey** | [REG_ENUMERATE_VALUE_KEY_INFORMATION](./ns-wdm-_reg_enumerate_value_key_information.md)  | 
| **RegNtPreEnumerateValueKey** | [REG_ENUMERATE_VALUE_KEY_INFORMATION](./ns-wdm-_reg_enumerate_value_key_information.md)  | 
| **RegNtPostEnumerateValueKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtQueryKey** | [REG_QUERY_KEY_INFORMATION](./ns-wdm-_reg_query_key_information.md)  | 
| **RegNtPreQueryKey** | [REG_QUERY_KEY_INFORMATION](./ns-wdm-_reg_query_key_information.md)  | 
| **RegNtPostQueryKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtQueryValueKey** | [REG_QUERY_VALUE_KEY_INFORMATION](./ns-wdm-_reg_query_value_key_information.md)  | 
| **RegNtPreQueryValueKey** | [REG_QUERY_VALUE_KEY_INFORMATION](./ns-wdm-_reg_query_value_key_information.md)  | 
| **RegNtPostQueryValueKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtQueryMultipleValueKey** | [REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION](./ns-wdm-_reg_query_multiple_value_key_information.md)  | 
| **RegNtPreQueryMultipleValueKey** | [REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION](./ns-wdm-_reg_query_multiple_value_key_information.md)  | 
| **RegNtPostQueryMultipleValueKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreCreateKey** | [REG_PRE_CREATE_KEY_INFORMATION](./ns-wdm-_reg_pre_create_key_information.md)  | 
| **RegNtPreCreateKeyEx** | [REG_CREATE_KEY_INFORMATION**](./ns-wdm-_reg_create_key_information.md)  | 
| **RegNtPostCreateKey** | [REG_POST_CREATE_KEY_INFORMATION](./ns-wdm-_reg_post_create_key_information.md)  | 
| **RegNtPostCreateKeyEx** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreOpenKey** | [REG_PRE_OPEN_KEY_INFORMATION**](./ns-wdm-_reg_pre_create_key_information.md)  | 
| **RegNtPreOpenKeyEx** | [REG_OPEN_KEY_INFORMATION](./ns-wdm-_reg_create_key_information.md)  | 
| **RegNtPostOpenKey** | [REG_POST_OPEN_KEY_INFORMATION](./ns-wdm-_reg_post_create_key_information.md)  | 
| **RegNtPostOpenKeyEx** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtKeyHandleClose** | [REG_KEY_HANDLE_CLOSE_INFORMATION](./ns-wdm-_reg_key_handle_close_information.md)  | 
| **RegNtPreKeyHandleClose** | [REG_KEY_HANDLE_CLOSE_INFORMATION](./ns-wdm-_reg_key_handle_close_information.md)  | 
| **RegNtPostKeyHandleClose** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreFlushKey** | [REG_FLUSH_KEY_INFORMATION](./ns-wdm-_reg_delete_key_information.md)  | 
| **RegNtPostFlushKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreLoadKey** | [REG_LOAD_KEY_INFORMATION](./ns-wdm-_reg_load_key_information.md)  | 
| **RegNtPostLoadKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreUnLoadKey** | [REG_UNLOAD_KEY_INFORMATION](./ns-wdm-_reg_unload_key_information.md)  | 
| **RegNtPostUnLoadKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreQueryKeySecurity** | [REG_QUERY_KEY_SECURITY_INFORMATION](./ns-wdm-_reg_query_key_security_information.md)  | 
| **RegNtPostQueryKeySecurity** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreSetKeySecurity** | [REG_SET_KEY_SECURITY_INFORMATION](./ns-wdm-_reg_set_key_security_information.md)  | 
| **RegNtPostSetKeySecurity** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtCallbackObjectContextCleanup** | [REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION](./ns-wdm-_reg_callback_context_cleanup_information.md)  | 
| **RegNtPreRestoreKey** | [REG_RESTORE_KEY_INFORMATION](./ns-wdm-_reg_restore_key_information.md)  | 
| **RegNtPostRestoreKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreSaveKey** | [REG_SAVE_KEY_INFORMATION](./ns-wdm-_reg_save_key_information.md)  | 
| **RegNtPostSaveKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreReplaceKey** | [REG_REPLACE_KEY_INFORMATION](./ns-wdm-_reg_replace_key_information.md)  | 
| **RegNtPostReplaceKey** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
| **RegNtPreQueryKeyName** | [REG_QUERY_KEY_NAME](./ns-wdm-_reg_query_key_name.md)  | 
| **RegNtPostQueryKeyName** | [REG_POST_OPERATION_INFORMATION](./ns-wdm-_reg_post_operation_information.md)  | 
 

** Starting with Windows 7, the actual data structure passed in when the notify class is RegNtPreCreateKeyEx or RegNtPreOpenKeyEx is the V1 version of this structure, [REG_CREATE_KEY_INFORMATION_V1](./ns-wdm-_reg_create_key_information_v1.md)  or [REG_OPEN_KEY_INFORMATION_V1](https://msdn.microsoft.com/library/windows/hardware/ff560959) , respectively. Check the Reserved member to determine the version of the structure.

| **Version number** | **Structure name** | 
|:--|:--|
| 0 | REG_CREATE_KEY_INFORMATION and REG_OPEN_KEY_INFORMATION | 
| 1 | REG_CREATE_KEY_INFORMATION_V1 and REG_OPEN_KEY_INFORMATION_V1 |

## -returns

For more information about when a <i>RegistryCallback</i> routine should return each of these status values, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -remarks

To be notified of registry operations, a kernel-mode component (such as the driver component of an antivirus software package) can call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a> to register a <i>RegistryCallback</i> routine.

The <i>RegistryCallback</i> routine can inspect the contents of the input and output buffers that are supplied for registry operations. A registry operation can be initiated by a user-mode application that calls a user-mode registry routine (such as <a href="/windows/win32/api/winreg/nf-winreg-regcreatekeyexa">RegCreateKeyEx</a> or <a href="/windows/win32/api/winreg/nf-winreg-regopenkeyexa">RegOpenKeyEx</a>) or by a driver that calls a kernel-mode registry routine (such as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>). An <i>input buffer</i> is a memory buffer supplied by the initiator from which the registry reads input data for the operation. An <i>output buffer</i> is a buffer supplied by the initiator into which the registry writes output data requested by the initiator.

Before calling the <i>RegistryCallback</i> routine, the kernel probes (to verify alignment and accessibility) all members of the <i>Argument2</i> structures that point to output buffers in user-mode memory, but does not capture user-mode output buffers in system memory. The callback routine must enclose any access of an output buffer in a <b>try</b>/<b>except</b> block. If the callback routine needs to pass an output buffer pointer to a system routine (for example, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>), and the buffer is in user-mode memory, the callback routine must first capture the buffer.

The handling of input buffers depends on the Windows version. Starting with Windows 8, the kernel captures all input buffers pointed to by members of the <i>Argument2</i> structures in system memory before calling the <i>RegistryCallback</i> routine. In versions of Windows before Windows 8, the kernel probes all members of the <i>Argument2</i> structures that point to input buffers in user-mode memory, but captures only some of these buffers in system memory. In these earlier versions of Windows, the callback routine must enclose any access of an input buffer in a <b>try</b>/<b>except</b> block. Additionally, if the callback routine needs to pass an input buffer pointer to a system routine (for example, <b>ZwOpenKey</b>), and the buffer is in user-mode memory, the callback routine must first capture the buffer.

The following table summarizes the requirements for buffer accesses by the <i>RegistryCallback</i> routine.

<table>
<tr>
<th>Buffer type</th>
<th>Windows version</th>
<th>Buffer pointer passed to callback routine</th>
<th>Safe for callback routine to directly access?</th>
<th>Safe to pass to system routines (such as <b>ZwOpenKey</b>)?</th>
</tr>
<tr>
<td>User-mode input</td>
<td>Windows 8 and later</td>
<td>Points to captured data.</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td>User-mode input</td>
<td>Windows 7 and earlier</td>
<td>Points to captured data or original user-mode buffer.</td>
<td>No. Must read under try/except.</td>
<td>No. Must allocate kernel memory, copy data from the original buffer under try/except, and pass the copied data to the system routine.</td>
</tr>
<tr>
<td>User-mode output</td>
<td>All</td>
<td>Points to original user-mode buffer.</td>
<td>No. Must write under try/except.</td>
<td>No. Must allocate kernel memory, pass kernel memory to the system routine, and copy the results back to the original buffer under try/except.</td>
</tr>
<tr>
<td>Kernel-mode input and output</td>
<td>All</td>
<td>Points to original kernel-mode buffer.</td>
<td>Yes</td>
<td>Yes</td>
</tr>
</table>
 

For more information about <i>RegistryCallback</i> routines and registry filter drivers, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

A <i>RegistryCallback</i> executes at IRQL = PASSIVE_LEVEL and in the context of the thread that is performing the registry operation.


#### Examples

To define a <i>RegistryCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>RegistryCallback</i> callback routine that is named <code>MyRegistryCallback</code>, use the EX_CALLBACK_FUNCTION type as shown in this code example:


```
EX_CALLBACK_FUNCTION MyRegistryCallback;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
NTSTATUS 
  MyRegistryCallback(
    PVOID  CallbackContext,
    PVOID  Argument1,
    PVOID  Argument2 
    )
  {
      // Function body
  }
```

The EX_CALLBACK_FUNCTION function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EX_CALLBACK_FUNCTION function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforread">ProbeForRead</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_reg_notify_class">REG_NOTIFY_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>