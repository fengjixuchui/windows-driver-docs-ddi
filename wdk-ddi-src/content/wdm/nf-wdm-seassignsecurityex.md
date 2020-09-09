---
UID: NF:wdm.SeAssignSecurityEx
title: SeAssignSecurityEx function (wdm.h)
description: The SeAssignSecurityEx routine builds a self-relative security descriptor for a new object given the following optional parameters:\_a security descriptor of the object's parent directory, an explicit security descriptor for the object, and the object type.
old-location: kernel\seassignsecurityex.htm
tech.root: kernel
ms.assetid: 94f6d3a3-7f0d-4f57-8240-3c4a10cf4488
ms.date: 04/30/2018
keywords: ["SeAssignSecurityEx function"]
ms.keywords: SeAssignSecurityEx, SeAssignSecurityEx routine [Kernel-Mode Driver Architecture], k110_e014ad32-3cbd-47e6-908b-65357203ee59.xml, kernel.seassignsecurityex, wdm/SeAssignSecurityEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SeAssignSecurityEx
 - wdm/SeAssignSecurityEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeAssignSecurityEx
---

# SeAssignSecurityEx function


## -description

The 
   <b>SeAssignSecurityEx</b> routine builds a self-relative security descriptor for a new object given the following optional parameters: a security descriptor of the object's parent directory, an explicit security descriptor for the object, and the object type.

## -parameters

### -param ParentDescriptor 

[in, optional]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> of the parent object that contains the new object being created. <i>ParentDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> system access control list (<a href="https://docs.microsoft.com/windows-hardware/drivers/">SACL</a>) or a <b>NULL</b> discretionary access control list (<a href="https://docs.microsoft.com/windows-hardware/drivers/">DACL</a>).

### -param ExplicitDescriptor 

[in, optional]
Pointer to an explicit <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> that is applied to the new object. <i>ExplicitDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> SACL or a <b>NULL</b> DACL.

### -param NewDescriptor 

[out]
Receives a pointer to the returned <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>.  <b>SeAssignSecurityEx</b> allocates the buffer from the paged memory pool.

### -param ObjectType 

[in, optional]
Pointer to a GUID for the type of object being created. If the object does not have a GUID, <i>ObjectType</i> must be set to <b>NULL</b>.

### -param IsDirectoryObject 

[in]
Specifies whether the new object is a directory object. If <i>IsDirectoryObject</i> is set to <b>TRUE</b>, the new object is a directory object, otherwise the new object is not a directory object.

### -param AutoInheritFlags 

[in]
Specifies the type of automatic inheritance that is applied to access control entries (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>) in the access control lists (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>) specified by <i>ParentDescriptor</i>. <i>AutoInheritFlags</i> also controls privilege checking, owner checking, and setting a default owner and group for <i>NewDescriptor</i>. <i>AutoInheritFlags</i> must be set to a logical OR of one or more of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SEF_DACL_AUTO_INHERIT

</td>
<td>
ACEs in the DACL of <i>ParentDescriptor</i> are inherited by <i>NewDescripto</i>r, in addition to explicit ACEs specified by <i>ExplicitDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_SACL_AUTO_INHERIT

</td>
<td>
ACEs in the SACL of <i>ParentDescriptor</i> are inherited by <i>NewDescriptor</i>, in addition to explicit ACEs specified by <i>ExplicitDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT

</td>
<td>
<i>ExplicitDescriptor</i> is the default descriptor for the object type specified by <i>ObjectType</i>. <i>ExplicitDescriptor</i> is not used if ACEs are inherited from <i>ParentDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_AVOID_PRIVILEGE_CHECK

</td>
<td>
Privilege checking is not done. This flag is useful with automatic inheritance because it avoids privilege checking on each child that needs to be updated. 

</td>
</tr>
<tr>
<td>
SEF_AVOID_OWNER_CHECK

</td>
<td>
Owner checking is not done.

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_OWNER_FROM_PARENT

</td>
<td>
If an owner is specified by <i>ExplicitDescriptor</i>, this flag is not used, and the owner of <i>NewDescriptor</i> is set to the owner specified by <i>ExplictDescriptor</i>.

If an owner is not specified by <i>ExplicitDescriptor</i>, this flag is used in the following way: If the flag is set, the owner of <i>NewDescriptor</i> is set to the owner of <i>ParentDescriptor</i>. Otherwise, the owner of <i>NewDescriptor</i> is set to the owner specified by the <i>SubjectContext.</i>

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_GROUP_FROM_PARENT

</td>
<td>
If a group is specified by <i>ExplicitDescriptor</i>, this flag is not used, and the group of <i>NewDescriptor</i> is set to the group specified by <i>ExplictDescriptor</i>.

If a group is not specified by <i>ExplicitDescriptor</i>, this flag is used in the following way: If the flag is set, the group of <i>NewDescriptor</i> is set to the group of <i>ParentDescriptor</i>. Otherwise, the group of <i>NewDescriptor</i> is set to the group specified by the <i>SubjectContext.</i>

</td>
</tr>
</table>
 

The assignment of system and discretionary ACLs is described in the following table:

<table>
<tr>
<th></th>
<th>Nondefault explicit descriptor(1)</th>
<th>Default explicit descriptor(2)</th>
<th><b>NULL</b> Explicit descriptor</th>
</tr>
<tr>
<td>
ACL is inherited from parent descriptor(3).

</td>
<td>
Assign both inherited and explicit ACLs(5)(6).

</td>
<td>
Assign inherited ACL.

</td>
<td>
Assign inherited ACL.

</td>
</tr>
<tr>
<td>
ACL is not inherited from parent descriptor(4).

</td>
<td>
Assign nondefault ACL.

</td>
<td>
Assign default ACL.

</td>
<td>
Assign no ACL.

</td>
</tr>
</table>
 

<b>Assignment Notes</b>

<ol>
<li>
The SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT flag is not specified.

</li>
<li>
The SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT flag is specified.

</li>
<li>
The auto inherit flag for an ACL is specified (SEF_DACL_AUTO_INHERIT or SEF_SACL_AUTO_INHERIT).

</li>
<li>
The automatic inherit flag for an ACL is not specified.

</li>
<li>
ACEs with the INHERITED_ACE bit set in their <b>AceFlags</b> member are <u>not</u> copied to the assigned security descriptor. 

</li>
<li>
ACEs that are inherited from the parent descriptor are appended after the ACEs specified by the explicit descriptor.

</li>
</ol>

### -param SubjectContext 

[in]
Pointer to a security context of the subject that is creating the object. <i>SubjectContext</i> is used to retrieve default security information for the new object, including the default owner, the primary group, and discretionary access control.

### -param GenericMapping 

[in]
Pointer to an array of access mask values that specify the mapping between each generic rights to object-specific rights.

### -param PoolType 

[in]
This parameter is unused.  The buffer to hold the new security descriptor is always allocated from paged pool.

## -returns

<b>SeAssignSecurityEx</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The assignment was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_OWNER</b></dt>
</dl>
</td>
<td width="60%">
The SID provided as the owner of the new security descriptor is not a SID that the caller is authorized to assign as the owner of an object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have the privilege (<b>SeSecurityPrivilege</b>) necessary to explicitly assign the specified SACL.

</td>
</tr>
</table>

## -remarks

<b>SeAssignSecurityEx</b> extends the basic operation of <b>SeAssignSecurity</b> in the following ways:

<ul>
<li>
<i>ObjectType</i> optionally specifies an object type. Object-specific inheritance is controlled by the following members of an object-specific ACE: <b>Flags</b>, <b>InheritedObjectType</b>, and <b>Header.AceFlags</b>.

</li>
<li>
<i>AutoInheritFlags </i>specifies the type of automatic inheritance of ACEs that is used. AutoInheritFlags also controls privilege checking, owner checking, and setting a default owner and group for <i>NewDescriptor</i>.

</li>
</ul>
For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_generic_mapping">GENERIC_MAPPING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-seassignsecurity">SeAssignSecurity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-sedeassignsecurity">SeDeassignSecurity</a>

