---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY
title: IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY (ehstorbandmgmt.h)
description: The security properties of bands in a band-managed storage device are modified with the IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY request.
old-location: storage\ioctl_ehstor_bandmgmt_set_band_security.htm
tech.root: storage
ms.assetid: CBA94AF4-649D-47C9-879B-4B939DE32BE2
ms.date: 03/29/2018
keywords: ["IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY IOCTL"]
ms.keywords: IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY, IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY control, IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY, storage.ioctl_ehstor_bandmgmt_set_band_security
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
req.typenames: 
f1_keywords:
 - IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY
 - ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorBandMgmt.h
api_name:
 - IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY
---

# IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY IOCTL


## -description

The security properties of bands in a band-managed storage device are modified with the <b>IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY</b> request.

## -ioctlparameters

### -input-buffer

The buffer at <i>Irp->AssociatedIrp.SystemBuffer</i> must contain a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_set_band_security_parameters"> SET_BAND_SECURITY_PARAMETERS</a> structure followed by the <b>AUTH_KEY</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_security_info">BAND_SECURITY_INFO</a> structures. 

If the <b>AuthKeyOffset</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_set_band_security_parameters">SET_BAND_SECURITY_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure. Also, if a new authentication key is not given, no updated key structure is included.

### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SET_BAND_SECURITY_PARAMETERS)   + 2 * <b>sizeof</b>(AUTH_KEY) + <b>sizeof</b>(BAND_SECURITY_INFO) when all input structures are required.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

One of the following values can be returned in the <b>Status</b> field.

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>Security properties for the band were changed.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_REQUEST</td>
<td>The storage device does not support band management.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The input buffer size is invalid.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>Information in the input buffer is invalid.</td>
</tr>
<tr>
<td>STATUS_NOT_FOUND</td>
<td>A band was not found for the selection criteria provided.</td>
</tr>
<tr>
<td>STATUS_ACCESS_DENIED</td>
<td>The authentication key provided is not valid.</td>
</tr>
<tr>
<td>STATUS_IO_DEVICE_ERROR</td>
<td>Communication failed. The storage device might be incompatible with security protocols. </td>
</tr>
</table>

## -remarks

Read and write locking and unlocking for bands are set with this IOCTL in the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_security_info">BAND_SECURITY_INFO</a> structure included as input in the system buffer. 

Authentication key changes will not affect the lock state of the band. It is not necessary to unmount a volume to change an authentication key with this request.

When a band is unlocked, meaning either the  <b>Readlock</b> or <b>WriteLock</b> members of  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_security_info">BAND_SECURITY_INFO</a> are FALSE, the silo driver will cache the provided authentication key if <b>SETBANDSEC_AUTHKEY_CACHING_ENABLED</b> is set in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_set_band_security_parameters">SET_BAND_SECURITY_PARAMETERS</a>.

As a special case, this IOCTL can be used to notify the silo driver that a band was unlocked without the use of the locking members in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_security_info">BAND_SECURITY_INFO</a>. To do this, the <b>NewAuthKeyOffset</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_set_band_security_parameters">SET_BAND_SECURITY_PARAMETERS</a> is set to <b>CurrentAuthKeyOffset</b> with  <b>BandSecurityInfoOffset</b> set to 0. In this case, no security changes occur, but the key provided at <b>CurrentAuthKeyOffset</b> is cached in memory, provided that <b>SETBANDSEC_AUTHKEY_CACHING_ENABLED</b> is set in <b>Flags</b>.

The changes made to the band table by this request are committed to the device atomically before the IOCTL request completes. Therefore, it is guaranteed that the band is modified with all of its properties set or no properties set at all should a system or power failure occur.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_security_info">BAND_SECURITY_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_delete_band">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_set_band_security_parameters">SET_BAND_SECURITY_PARAMETERS</a>

