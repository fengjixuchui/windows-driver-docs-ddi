---
UID: NS:wdm._REG_CREATE_KEY_INFORMATION
title: _REG_CREATE_KEY_INFORMATION (wdm.h)
description: The REG_CREATE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key that is being created.
old-location: kernel\reg_create_key_information.htm
tech.root: kernel
ms.assetid: 5609a2c4-71db-432a-8a39-e407130a6e4c
ms.date: 04/30/2018
keywords: ["REG_CREATE_KEY_INFORMATION structure"]
ms.keywords: "*PREG_CREATE_KEY_INFORMATION, *PREG_OPEN_KEY_INFORMATION, PREG_CREATE_KEY_INFORMATION, PREG_CREATE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PREG_OPEN_KEY_INFORMATION, PREG_OPEN_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_CREATE_KEY_INFORMATION, REG_CREATE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], REG_OPEN_KEY_INFORMATION, REG_OPEN_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_CREATE_KEY_INFORMATION, kernel.reg_create_key_information, kstruct_d_08c0de2c-94fb-4c4f-888c-e3485f213224.xml, wdm/PREG_CREATE_KEY_INFORMATION, wdm/PREG_OPEN_KEY_INFORMATION, wdm/REG_CREATE_KEY_INFORMATION, wdm/REG_OPEN_KEY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Server 2003, but some structure members are available only in Windows Vista and later versions.
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
req.typenames: REG_CREATE_KEY_INFORMATION, REG_OPEN_KEY_INFORMATION, *PREG_CREATE_KEY_INFORMATION, *PREG_OPEN_KEY_INFORMATION
f1_keywords:
 - _REG_CREATE_KEY_INFORMATION
 - wdm/_REG_CREATE_KEY_INFORMATION
 - PREG_CREATE_KEY_INFORMATION
 - wdm/PREG_CREATE_KEY_INFORMATION
 - REG_CREATE_KEY_INFORMATION
 - wdm/REG_CREATE_KEY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - REG_CREATE_KEY_INFORMATION
---

# _REG_CREATE_KEY_INFORMATION structure


## -description

The <b>REG_CREATE_KEY_INFORMATION</b> structure contains information that a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can use when a registry key that is being created.
<div class="alert"><b>Note</b>  Starting with Windows 7, the V1 version of this structure, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information_v1">REG_CREATE_KEY_INFORMATION_V1</a>, is used instead.</div><div> </div>

## -struct-fields

### -field CompleteName

A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the path of the new registry key. The path can be absolute or relative. If the path is absolute, this structure contains a fully qualified path that starts with the "\\" character. For an absolute path, the <b>RootObject</b> member specifies the <b>\REGISTRY</b> key, which is the root directory of the registry tree. If the path is relative, the path starts with a character other than "\\", and is relative to the key that is specified by the <i>RootObject</i> member.

### -field RootObject

Pointer to the registry key object that serves as the root for the path specified by the <i>CompleteName</i> member.

### -field ObjectType

The <b>ObjectType</b> member is reserved for internal use. Drivers must not access this member. This member is defined starting with Windows Vista.

### -field CreateOptions

A bitwise OR of flags. For more information about these flags, see the <i>CreateOptions</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> routine. This member is defined starting with Windows Vista.

### -field Class

A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that identifies the key's object class. For more information about this member, see the <i>Class</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> routine. This member is defined starting with Windows Vista.

### -field SecurityDescriptor

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure that contains security information for the key object. This member is defined starting with Windows Vista.

### -field SecurityQualityOfService

A pointer to a <b>SECURITY_QUALITY_OF_SERVICE</b> structure, which is defined in Winnt.h. This member is defined starting with Windows Vista.

### -field DesiredAccess

The access mask that was specified by the thread that is attempting to create the registry key. This member is defined starting with Windows Vista.

### -field GrantedAccess

An access mask that indicates the access rights that have been granted to the thread that is attempting to create the registry key. For more information about this member, see Remarks. This member is defined starting with Windows Vista.

### -field Disposition

A value that indicates whether the registry key was created. For more information about this member, see the <i>Disposition</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> routine and the following Remarks section. This member is defined starting with Windows Vista.

### -field ResultObject

A pointer to a location that receives the address of the key object that represents the created registry key. For more information about this member, see Remarks. This member is defined starting with Windows Vista.

### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined starting with Windows Vista.

### -field RootObjectContext

A pointer to a driver-defined context information that the driver has associated with the root of the path for the registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined starting with Windows Vista.

### -field Transaction

A pointer to a transaction object that the operation is attempted on. If this member is <b>NULL</b>, the operation is being performed in non-transactional context. This member is defined starting with Windows Vista.

### -field Reserved

Starting with Windows Vista, if this member is 1, then it is safe to cast this structure to type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information_v1">REG_CREATE_KEY_INFORMATION_V1</a>, which contains additional parameters.

In versions of Windows before Windows Vista, this member is always 0.

## -remarks

The configuration manager passes this structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a thread attempts to create a key—for example, when a user-mode thread calls <b>RegCreateKey</b> or <b>RegCreateKeyEx</b> or when a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>.

If the driver's <i>RegistryCallback</i> routine returns STATUS_CALLBACK_BYPASS for a <b>RegNtPreCreateKeyEx</b> notification, the driver must supply the <b>GrantedAccess</b>, <b>Disposition</b>, and <b>ResultObject</b> values.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information_v1">REG_CREATE_KEY_INFORMATION_V1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_post_operation_information">REG_POST_OPERATION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>

