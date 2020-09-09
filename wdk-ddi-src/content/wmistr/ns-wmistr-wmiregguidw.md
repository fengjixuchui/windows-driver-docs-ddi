---
UID: NS:wmistr.__unnamed_struct_1
title: WMIREGGUIDW (wmistr.h)
description: The WMIREGGUID structure contains new or updated registration information for a data block or event block.
old-location: kernel\wmiregguid.htm
tech.root: kernel
ms.assetid: f9f240ea-5689-4d33-8da7-b1cb7e66bc5b
ms.date: 04/30/2018
keywords: ["WMIREGGUIDW structure"]
ms.keywords: "*PWMIREGGUIDW, PWMIREGGUID, PWMIREGGUID structure pointer [Kernel-Mode Driver Architecture], WMIREGGUID, WMIREGGUID structure [Kernel-Mode Driver Architecture], WMIREGGUIDW, WMIREGGUIDW structure [Kernel-Mode Driver Architecture], kernel.wmiregguid, kstruct_d_1e7b2ada-5e56-42ed-bd0a-ec9bf25796f2.xml, wmistr/PWMIREGGUID, wmistr/WMIREGGUID"
req.header: wmistr.h
req.include-header: Wmistr.h
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
targetos: Windows
req.typenames: WMIREGGUIDW, *PWMIREGGUIDW
f1_keywords:
 - PWMIREGGUIDW
 - wmistr/PWMIREGGUIDW
 - WMIREGGUIDW
 - wmistr/WMIREGGUIDW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wmistr.h
api_name:
 - WMIREGGUID
---

# WMIREGGUIDW structure


## -description

The <b>WMIREGGUID</b> structure contains new or updated registration information for a data block or event block.

## -struct-fields

### -field Guid

Specifies the GUID that represents the block to register or update.

### -field Flags

Indicates characteristics of the block to register or update. 

If a block is being registered with static instance names, a driver sets one of the following flags:





#### WMIREG_FLAG_INSTANCE_LIST

Indicates that the driver provides static instance names for this block in a static list following the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-wmireginfow">WMIREGINFO</a> structure in the buffer at <b>IrpStack->Parameters.WMI.Buffer</b>. If this flag is set, <b>InstanceNameList</b> is the offset in bytes from the beginning of the <b>WMIREGINFO</b> structure that contains this <b>WMIREGGUID</b> to a contiguous series of <b>InstanceCount</b> counted Unicode strings.



#### WMIREG_FLAG_INSTANCE_BASENAME

Requests WMI to generate static instance names from a base name provided by the driver following the <b>WMIREGINFO</b> structure in the buffer at <b>IrpStack->Parameters.WMI.Buffer</b>. WMI generates instance names by appending a counter to the base name. If this flag is set, <b>BaseNameOffset</b> is the offset in bytes from the beginning of the <b>WMIREGINFO</b> structure that contains this <b>WMIREGGUID</b> to a single counted Unicode string that serves as the base name.



#### WMIREG_FLAG_INSTANCE_PDO

Requests WMI to generate static instance names from the device instance ID for the PDO. If this flag is set, <b>InstanceInfo</b> points to the PDO passed to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine. WMI generates instance names from the device instance path of the PDO. Using the device instance path as a base for static instance names is efficient because such names are guaranteed to be unique. WMI automatically supplies a "friendly" name for the instance as an item in a data block that can be queried by data consumers.

If a block is being registered with dynamic instance names, WMIREG_FLAG_INSTANCE_LIST, WMIREG_FLAG_INSTANCE_BASENAME, and WMIREG_FLAG_INSTANCE_PDO must be clear.

A driver might also set one or more of the following flags:





#### WMIREG_FLAG_EVENT_ONLY_GUID

The block can be enabled or disabled as an event only, and cannot be queried or set. If this flag is clear, the block can also be queried or set.



#### WMIREG_FLAG_EXPENSIVE

Requests WMI to send an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-enable-collection">IRP_MN_ENABLE_COLLECTION</a> request the first time a data consumer opens the data block and an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-disable-collection">IRP_MN_DISABLE_COLLECTION</a> request when the last data consumer closes the data block. This is recommended if collecting such data affects performance, because a driver need not collect the data until a data consumer explicitly requests it by opening the block.



#### WMIREG_FLAG_REMOVE_GUID

Requests WMI to remove support for this block. This flag is valid only in response to a request to update registration information (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a> with <b>Parameters.WMI.DataPath </b>set to WMIUPDATE).



#### WMIREG_FLAG_TRACED_GUID

The block can be written only to a log file and can be accessed only through user-mode routines declared in evntrace.h. Only NT kernel-mode data providers set this flag.



#### WMIREG_FLAG_TRACE_CONTROL_GUID

The GUID acts as the control GUID for enabling or disabling the trace GUIDs associated with it in the MOF file. This flag is valid only if WMIREG_FLAG_TRACED_GUID is also set. Only NT kernel-mode data providers set this flag.

### -field InstanceCount

Specifies the number of static instance names to be defined for this block. If the block is being registered with dynamic instance names, WMI ignores <b>InstanceCount</b>.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.InstanceNameList

Indicates the offset in bytes from the beginning of the <b>WMIREGINFO</b> structure that contains this <b>WMIREGGUID</b> to a contiguous series of <b>InstanceCount</b> counted Unicode strings. This member is valid only if WMIREG_FLAG_INSTANCE_LIST is set in <b>Flags</b>. If the block is being registered with dynamic instance names, WMI ignores <b>InstanceNameList</b>.

### -field DUMMYUNIONNAME.BaseNameOffset

Indicates the offset in bytes from the beginning of the <b>WMIREGINFO</b> structure that contains this <b>WMIREGGUID</b> to a single counted Unicode string that serves as a base for WMI to generate static instance names. This member is valid only if WMIREG_FLAG_INSTANCE_BASENAME is set in <b>Flags</b>. If the block is being registered with dynamic instance names, WMI ignores <b>BaseNameOffset</b>.

### -field DUMMYUNIONNAME.Pdo

Pointer to the physical device object (PDO) passed to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine. WMI uses the device instance path of this PDO as a base from which to generate static instance names. This member is valid only if WMIREG_FLAG_INSTANCE_PDO is set in <b>Flags</b>. If the block is being registered with dynamic instance names, WMI ignores <b>Pdo</b>.

### -field DUMMYUNIONNAME.InstanceInfo

Reserved for use by WMI.

## -remarks

A driver builds one or more <b>WMIREGGUID</b> structures in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a> request to register or update its blocks. The driver passes an array of such structures at the <b>WmiRegGuid </b>member of a <b>WMIREGINFO</b> structure, which the driver writes to the buffer at <b>IrpStack->Parameters.WMI.Buffer</b>.

A driver can register or update a block with either static or dynamic instance names. Static instance names provide best performance; however, dynamic instance names are preferred for data blocks if the number of instances or instance names change frequently. For more information about instance names, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/defining-wmi-instance-names">Defining WMI Instance Names</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-wmireginfow">WMIREGINFO</a>

