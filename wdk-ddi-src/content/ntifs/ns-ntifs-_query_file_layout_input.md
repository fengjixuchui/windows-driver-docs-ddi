---
UID: NS:ntifs._QUERY_FILE_LAYOUT_INPUT
title: _QUERY_FILE_LAYOUT_INPUT (ntifs.h)
description: The QUERY_FILE_LAYOUT_INPUT structure selects which file layout entries are returned from a FSCTL_QUERY_FILE_LAYOUT request.
old-location: ifsk\query_file_layout_input.htm
tech.root: ifsk
ms.assetid: 7404BFC3-8942-4927-9F5B-9FA860F9F95F
ms.date: 04/16/2018
ms.keywords: "*PQUERY_FILE_LAYOUT_INPUT, PQUERY_FILE_LAYOUT_INPUT, PQUERY_FILE_LAYOUT_INPUT structure pointer [Installable File System Drivers], QUERY_FILE_LAYOUT_FILTER_TYPE_CLUSTERS, QUERY_FILE_LAYOUT_FILTER_TYPE_FILEID, QUERY_FILE_LAYOUT_FILTER_TYPE_NONE, QUERY_FILE_LAYOUT_INCLUDE_EXTENTS, QUERY_FILE_LAYOUT_INCLUDE_EXTRA_INFO, QUERY_FILE_LAYOUT_INCLUDE_NAMES, QUERY_FILE_LAYOUT_INCLUDE_STREAMS, QUERY_FILE_LAYOUT_INCLUDE_STREAMS_WITH_NO_CLUSTERS_ALLOCATED, QUERY_FILE_LAYOUT_INPUT, QUERY_FILE_LAYOUT_INPUT structure [Installable File System Drivers], QUERY_FILE_LAYOUT_RESTART, _QUERY_FILE_LAYOUT_INPUT, ifsk.query_file_layout_input, ntifs/PQUERY_FILE_LAYOUT_INPUT, ntifs/QUERY_FILE_LAYOUT_INPUT"
ms.topic: struct
f1_keywords:
 - "ntifs/QUERY_FILE_LAYOUT_INPUT"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting in Windows 8.
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
- Ntifs.h
api_name:
- QUERY_FILE_LAYOUT_INPUT
product:
- Windows
targetos: Windows
req.typenames: QUERY_FILE_LAYOUT_INPUT, *PQUERY_FILE_LAYOUT_INPUT
---

# _QUERY_FILE_LAYOUT_INPUT structure


## -description


The <b>QUERY_FILE_LAYOUT_INPUT</b> structure selects which file layout entries are returned from a <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-query-file-layout">FSCTL_QUERY_FILE_LAYOUT</a> request.


## -struct-fields




### -field NumberOfPairs

The number of filter ranges present in the <b>Filter</b> array.


### -field Flags

Indicates which file layout entries are included in the query results. <b>Flags</b> is set to a valid combination of these values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_INCLUDE_EXTENTS"></a><a id="query_file_layout_include_extents"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_INCLUDE_EXTENTS</b></dt>
</dl>
</td>
<td width="60%">
Stream extent entries are included in the query results. To use this flag, the <b>QUERY_FILE_LAYOUT_INCLUDE_STREAMS</b> flag must also be set.

</td>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_INCLUDE_EXTRA_INFO"></a><a id="query_file_layout_include_extra_info"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_INCLUDE_EXTRA_INFO</b></dt>
</dl>
</td>
<td width="60%">
Extra file information name entries are included in the query results.

</td>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_INCLUDE_NAMES"></a><a id="query_file_layout_include_names"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_INCLUDE_NAMES</b></dt>
</dl>
</td>
<td width="60%">
File name entries are included in the query results.

</td>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_INCLUDE_STREAMS"></a><a id="query_file_layout_include_streams"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_INCLUDE_STREAMS</b></dt>
</dl>
</td>
<td width="60%">
File stream entries are included in the query results.

</td>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_RESTART"></a><a id="query_file_layout_restart"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_RESTART</b></dt>
</dl>
</td>
<td width="60%">
Reset the file  layout entry iterator to the beginning of the volume.

</td>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_INCLUDE_STREAMS_WITH_NO_CLUSTERS_ALLOCATED"></a><a id="query_file_layout_include_streams_with_no_clusters_allocated"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_INCLUDE_STREAMS_WITH_NO_CLUSTERS_ALLOCATED</b></dt>
</dl>
</td>
<td width="60%">
Include entries for resident streams and unallocated attributes. To use this flag, the <b>QUERY_FILE_LAYOUT_INCLUDE_STREAMS</b> flag must also be set.

</td>
</tr>
</table>
 


### -field FilterType

Specifies a filtering method to restrict returned layout information. May be one of these values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_FILTER_TYPE_NONE"></a><a id="query_file_layout_filter_type_none"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_FILTER_TYPE_NONE</b></dt>
</dl>
</td>
<td width="60%">
Perform no filtering and return all information. When using this type, <i>NumberOfPairs</i> must be 0.

</td>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_FILTER_TYPE_CLUSTERS"></a><a id="query_file_layout_filter_type_clusters"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_FILTER_TYPE_CLUSTERS</b></dt>
</dl>
</td>
<td width="60%">
Restrict filter layout information to the ranges in <b>Filter.ClusterRanges</b>.

</td>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_FILTER_TYPE_FILEID"></a><a id="query_file_layout_filter_type_fileid"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_FILTER_TYPE_FILEID</b></dt>
</dl>
</td>
<td width="60%">
Restrict filter layout information to the ranges in <b>Filter.FileReferenceRanges</b>.

</td>
</tr>
</table>
 


### -field Reserved

Reserved for system use.


### -field Filter

An array of filter structures used to select specific layout information. These contain either cluster or file reference ranges. The array length is specified by the <b>NumberOfPairs</b> member. Each range must be distinct and cannot overlap with any other range.

This member is ignored if <b>QUERY_FILE_LAYOUT_FILTER_TYPE_NONE</b> is specified in <b>FilterType</b>.


### -field Filter.ClusterRanges

Specifies a set of cluster ranges to filter layout information. The range structure has the following format.


<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _CLUSTER_RANGE {
    LARGE_INTEGER    StartingCluster;
    LARGE_INTEGER    ClusterCount;
} CLUSTER_RANGE, *PCLUSTER_RANGE;</pre>
</td>
</tr>
</table></span></div>



### -field Filter.FileReferenceRanges

Specifies a set of file reference ranges to filter layout information. The range structure has the following format.


<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _FILE_REFERENCE_RANGE {
    LARGE_INTEGER    StartingFileReference;
    LARGE_INTEGER    EndingReferenceNumber;
} FILE_REFERENCE_RANGE, *PFILE_REFERENCE_RANGE;</pre>
</td>
</tr>
</table></span></div>



## -remarks



The <b>QUERY_FILE_LAYOUT_RESTART</b> flag is set on the first <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-query-file-layout">FSCTL_QUERY_FILE_LAYOUT</a> request. If filter ranges are included in the request, they are cached when <b>QUERY_FILE_LAYOUT_RESTART</b> is set. Further requests will return layout file entries until the end of the volume or until filter ranges are exhausted.

If <b>QUERY_FILE_LAYOUT_RESTART</b> is set again for the same volume, the file layout position is reset to the beginning of the volume. Additionally, the filter ranges are re-cached and their  evaluation order is reset to the first range. 

The file layout entries are returned in the output buffer following a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_query_file_layout_output">QUERY_FILE_LAYOUT_OUTPUT</a> structure.

When <b>FilterType</b> is <b>QUERY_FILE_LAYOUT_FILTER_TYPE_CLUSTERS</b>, the <b>ClusterRanges</b> member of the <b>Filter</b> union is used for range filtering. Otherwise, if <b>FilterType</b> is <b>QUERY_FILE_LAYOUT_FILTER_TYPE_FILEID</b>, the <b>FileReferenceRanges</b> member is used for range filtering.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-query-file-layout">FSCTL_QUERY_FILE_LAYOUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_query_file_layout_output">QUERY_FILE_LAYOUT_OUTPUT</a>
 

 

