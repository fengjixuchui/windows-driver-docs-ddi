---
UID: NS:ntifs.MARK_HANDLE_INFO32
title: MARK_HANDLE_INFO32 (ntifs.h)
description: Contains information that is used to mark a specified file or directory, and its update sequence number (USN) change journal record with data about changes.
old-location: ifsk\mark_handle_info32.htm
tech.root: ifsk
ms.assetid: BAC97D72-23C4-49A6-A13D-0F011113DB32
ms.date: 04/16/2018
ms.keywords: "*PMARK_HANDLE_INFO32, MARK_HANDLE_INFO32, MARK_HANDLE_INFO32 structure [Installable File System Drivers], MARK_HANDLE_NOT_REALTIME, MARK_HANDLE_NOT_TXF_SYSTEM_LOG, MARK_HANDLE_PROTECT_CLUSTERS, MARK_HANDLE_REALTIME, MARK_HANDLE_TXF_SYSTEM_LOG, PMARK_HANDLE_INFO32, PMARK_HANDLE_INFO32 structure pointer [Installable File System Drivers], USN_SOURCE_AUXILIARY_DATA, USN_SOURCE_DATA_MANAGEMENT, USN_SOURCE_REPLICATION_MANAGEMENT, ifsk.mark_handle_info32, ntifs/MARK_HANDLE_INFO32, ntifs/PMARK_HANDLE_INFO32"
ms.topic: struct
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
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
- ntifs.h
api_name:
- MARK_HANDLE_INFO32
product:
- Windows
targetos: Windows
req.typenames: MARK_HANDLE_INFO32, *PMARK_HANDLE_INFO32
---

# MARK_HANDLE_INFO32 structure


## -description


Contains information that is used to mark a specified file or directory, and its update sequence 
    number (USN) change journal record with data about changes. This is only defined for 64-bit code and is used to 
    interpret input data formatted as a <a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ns-winioctl-mark_handle_info">MARK_HANDLE_INFO</a> structure sent from 32-bit 
    code. It is used with the <a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ni-winioctl-fsctl_mark_handle">FSCTL_MARK_HANDLE</a> 
    control code.


## -struct-fields




### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.UsnSourceInfo

The type of changes being made.

The operation does not modify the file or directory externally from the point of view of the application that 
       created it.

When a thread writes a new USN record, the source information flags in the prior record continues to be 
       present only if the thread also sets those flags. Therefore, the source information structure allows 
       applications to filter out USN records that are set only by a known source, such as an antivirus filter.

The following values are defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_DATA_MANAGEMENT"></a><a id="usn_source_data_management"></a><dl>
<dt><b>USN_SOURCE_DATA_MANAGEMENT</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
The operation provides information about a change to the file or directory made by the operating system.

A typical use is when Remote Storage moves data from external to local storage. Remote Storage is the 
         hierarchical storage management software. Such a move usually at a minimum adds the 
         <b>USN_REASON_DATA_OVERWRITE</b> flag to a USN record. However, the data has not changed 
         from the user point of view. By noting <b>USN_SOURCE_DATA_MANAGEMENT</b> in the 
         <b>SourceInfo</b> member of the 
         <a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ns-winioctl-usn_record_v2">USN_RECORD</a> structure that holds the record, you can 
         determine that although a write operation is performed on the item, data has not changed.

</td>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_AUXILIARY_DATA"></a><a id="usn_source_auxiliary_data"></a><dl>
<dt><b>USN_SOURCE_AUXILIARY_DATA</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The operation adds a private data stream to a file or directory.

An example might be a virus detector adding checksum information. As the virus detector modifies the item, 
         the system generates USN records. <b>USN_SOURCE_AUXILIARY_DATA</b> indicates that the 
         modifications did not change the application data.

</td>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_REPLICATION_MANAGEMENT"></a><a id="usn_source_replication_management"></a><dl>
<dt><b>USN_SOURCE_REPLICATION_MANAGEMENT</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
The operation creates or updates the contents of a replicated file.

For example, the file replication service sets this flag when it creates or updates a file in a replicated 
         directory.

</td>
</tr>
</table>
 

The type of changes being made.

The operation does not modify the file or directory externally from the point of view of the application that 
       created it.

When a thread writes a new USN record, the source information flags in the prior record continues to be 
       present only if the thread also sets those flags. Therefore, the source information structure allows 
       applications to filter out USN records that are set only by a known source, such as an antivirus filter.

The following values are defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_DATA_MANAGEMENT"></a><a id="usn_source_data_management"></a><dl>
<dt><b>USN_SOURCE_DATA_MANAGEMENT</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
The operation provides information about a change to the file or directory made by the operating system.

A typical use is when Remote Storage moves data from external to local storage. Remote Storage is the 
         hierarchical storage management software. Such a move usually at a minimum adds the 
         <b>USN_REASON_DATA_OVERWRITE</b> flag to a USN record. However, the data has not changed 
         from the user point of view. By noting <b>USN_SOURCE_DATA_MANAGEMENT</b> in the 
         <b>SourceInfo</b> member of the 
         <a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ns-winioctl-usn_record_v2">USN_RECORD</a> structure that holds the record, you can 
         determine that although a write operation is performed on the item, data has not changed.

</td>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_AUXILIARY_DATA"></a><a id="usn_source_auxiliary_data"></a><dl>
<dt><b>USN_SOURCE_AUXILIARY_DATA</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The operation adds a private data stream to a file or directory.

An example might be a virus detector adding checksum information. As the virus detector modifies the item, 
         the system generates USN records. <b>USN_SOURCE_AUXILIARY_DATA</b> indicates that the 
         modifications did not change the application data.

</td>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_REPLICATION_MANAGEMENT"></a><a id="usn_source_replication_management"></a><dl>
<dt><b>USN_SOURCE_REPLICATION_MANAGEMENT</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
The operation creates or updates the contents of a replicated file.

For example, the file replication service sets this flag when it creates or updates a file in a replicated 
         directory.

</td>
</tr>
</table>
 


### -field DUMMYUNIONNAME.CopyNumber

The zero-based copy number to use for subsequent reads. This is for use on Storage Spaces and Streams on 
        NTFS and ReFS and non-integrity streams on ReFS (streams with integrity on ReFS handle this automatically.)

<b>Windows Server 2008 R2, Windows 7, Windows Server 2008, Windows Vista, Windows Server 2003 and Windows XP:  </b>This member is not supported before Windows 8 and Windows Server 2012.


### -field UsnSourceInfo

The type of changes being made.

The operation does not modify the file or directory externally from the point of view of the application that 
       created it.

When a thread writes a new USN record, the source information flags in the prior record continues to be 
       present only if the thread also sets those flags. Therefore, the source information structure allows 
       applications to filter out USN records that are set only by a known source, such as an antivirus filter.

The following values are defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_DATA_MANAGEMENT"></a><a id="usn_source_data_management"></a><dl>
<dt><b>USN_SOURCE_DATA_MANAGEMENT</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
The operation provides information about a change to the file or directory made by the operating system.

A typical use is when Remote Storage moves data from external to local storage. Remote Storage is the 
         hierarchical storage management software. Such a move usually at a minimum adds the 
         <b>USN_REASON_DATA_OVERWRITE</b> flag to a USN record. However, the data has not changed 
         from the user point of view. By noting <b>USN_SOURCE_DATA_MANAGEMENT</b> in the 
         <b>SourceInfo</b> member of the 
         <a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ns-winioctl-usn_record_v2">USN_RECORD</a> structure that holds the record, you can 
         determine that although a write operation is performed on the item, data has not changed.

</td>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_AUXILIARY_DATA"></a><a id="usn_source_auxiliary_data"></a><dl>
<dt><b>USN_SOURCE_AUXILIARY_DATA</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The operation adds a private data stream to a file or directory.

An example might be a virus detector adding checksum information. As the virus detector modifies the item, 
         the system generates USN records. <b>USN_SOURCE_AUXILIARY_DATA</b> indicates that the 
         modifications did not change the application data.

</td>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_REPLICATION_MANAGEMENT"></a><a id="usn_source_replication_management"></a><dl>
<dt><b>USN_SOURCE_REPLICATION_MANAGEMENT</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
The operation creates or updates the contents of a replicated file.

For example, the file replication service sets this flag when it creates or updates a file in a replicated 
         directory.

</td>
</tr>
</table>
 

The type of changes being made.

The operation does not modify the file or directory externally from the point of view of the application that 
       created it.

When a thread writes a new USN record, the source information flags in the prior record continues to be 
       present only if the thread also sets those flags. Therefore, the source information structure allows 
       applications to filter out USN records that are set only by a known source, such as an antivirus filter.

The following values are defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_DATA_MANAGEMENT"></a><a id="usn_source_data_management"></a><dl>
<dt><b>USN_SOURCE_DATA_MANAGEMENT</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
The operation provides information about a change to the file or directory made by the operating system.

A typical use is when Remote Storage moves data from external to local storage. Remote Storage is the 
         hierarchical storage management software. Such a move usually at a minimum adds the 
         <b>USN_REASON_DATA_OVERWRITE</b> flag to a USN record. However, the data has not changed 
         from the user point of view. By noting <b>USN_SOURCE_DATA_MANAGEMENT</b> in the 
         <b>SourceInfo</b> member of the 
         <a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ns-winioctl-usn_record_v2">USN_RECORD</a> structure that holds the record, you can 
         determine that although a write operation is performed on the item, data has not changed.

</td>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_AUXILIARY_DATA"></a><a id="usn_source_auxiliary_data"></a><dl>
<dt><b>USN_SOURCE_AUXILIARY_DATA</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The operation adds a private data stream to a file or directory.

An example might be a virus detector adding checksum information. As the virus detector modifies the item, 
         the system generates USN records. <b>USN_SOURCE_AUXILIARY_DATA</b> indicates that the 
         modifications did not change the application data.

</td>
</tr>
<tr>
<td width="40%"><a id="USN_SOURCE_REPLICATION_MANAGEMENT"></a><a id="usn_source_replication_management"></a><dl>
<dt><b>USN_SOURCE_REPLICATION_MANAGEMENT</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
The operation creates or updates the contents of a replicated file.

For example, the file replication service sets this flag when it creates or updates a file in a replicated 
         directory.

</td>
</tr>
</table>
 


### -field VolumeHandle

The volume handle to the volume where the file or directory resides. For more information on obtaining a 
        volume handle, see the Remarks section.

This handle is required to check the privileges for this operation.

The caller must have the <b>SE_MANAGE_VOLUME_NAME</b> privilege. For more information, 
        see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/privileges">Privileges</a>.


### -field HandleInfo

The flag that specifies additional information about the file or directory identified by the handle value 
       in the <b>VolumeHandle</b> member.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="MARK_HANDLE_PROTECT_CLUSTERS"></a><a id="mark_handle_protect_clusters"></a><dl>
<dt><b>MARK_HANDLE_PROTECT_CLUSTERS</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
The file is marked as unable to be defragmented until the handle is closed.

</td>
</tr>
<tr>
<td width="40%"><a id="MARK_HANDLE_TXF_SYSTEM_LOG"></a><a id="mark_handle_txf_system_log"></a><dl>
<dt><b>MARK_HANDLE_TXF_SYSTEM_LOG</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
The file is marked as unable to be defragmented until the handle is closed.

</td>
</tr>
<tr>
<td width="40%"><a id="MARK_HANDLE_NOT_TXF_SYSTEM_LOG"></a><a id="mark_handle_not_txf_system_log"></a><dl>
<dt><b>MARK_HANDLE_NOT_TXF_SYSTEM_LOG</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
The file is marked as unable to be defragmented until the handle is closed.

</td>
</tr>
<tr>
<td width="40%"><a id="MARK_HANDLE_REALTIME"></a><a id="mark_handle_realtime"></a><dl>
<dt><b>MARK_HANDLE_REALTIME</b></dt>
<dt>0x00000020</dt>
</dl>
</td>
<td width="60%">
The file is marked for real-time read behavior regardless of the actual file type. Files marked with 
         this flag must be opened for <a href="https://docs.microsoft.com/windows/desktop/FileIO/file-buffering">unbuffered I/O</a>.

</td>
</tr>
<tr>
<td width="40%"><a id="MARK_HANDLE_NOT_REALTIME"></a><a id="mark_handle_not_realtime"></a><dl>
<dt><b>MARK_HANDLE_NOT_REALTIME</b></dt>
<dt>0x00000040</dt>
</dl>
</td>
<td width="60%">
The file previously marked for real-time read behavior using the 
         <b>MARK_HANDLE_REALTIME</b> flag can be unmarked using this flag, removing the real-time 
         behavior. Files marked with this flag must be opened for 
         <a href="https://docs.microsoft.com/windows/desktop/FileIO/file-buffering">unbuffered I/O</a>.

</td>
</tr>
</table>
 


## -remarks



When running on a 64-bit system, file system minifilters must interpret the input data sent by a 32-bit process in the system buffer for the <a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ni-winioctl-fsctl_mark_handle">FSCTL_MARK_HANDLE</a> control code as a <b>MARK_HANDLE_INFO32</b> structure. A minifilter may check the process word length by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltis32bitprocess">FltIs32bitProcess</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ni-winioctl-fsctl_mark_handle">FSCTL_MARK_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltis32bitprocess">FltIs32bitProcess</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winioctl/ns-winioctl-mark_handle_info">MARK_HANDLE_INFO</a>
 

 

