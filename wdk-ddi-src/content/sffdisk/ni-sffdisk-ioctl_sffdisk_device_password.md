---
UID: NI:sffdisk.IOCTL_SFFDISK_DEVICE_PASSWORD
title: IOCTL_SFFDISK_DEVICE_PASSWORD (sffdisk.h)
description: User-mode applications use this IOCTL to perform basic operations on a Secure Digital (SD) card, such as setting the password on the card, resetting the card, or locking and unlocking the card.
old-location: sd\ioctl_sffdisk_device_password.htm
tech.root: SD
ms.assetid: 76b65ada-06b8-411e-83e9-62088f697f02
ms.date: 02/15/2018
keywords: ["IOCTL_SFFDISK_DEVICE_PASSWORD IOCTL"]
ms.keywords: IOCTL_SFFDISK_DEVICE_PASSWORD, IOCTL_SFFDISK_DEVICE_PASSWORD control, IOCTL_SFFDISK_DEVICE_PASSWORD control code [Buses], SD.ioctl_sffdisk_device_password, sd-ioctls_409f2592-46a6-4658-bc4f-d15c10452007.xml, sffdisk/IOCTL_SFFDISK_DEVICE_PASSWORD
f1_keywords:
 - "sffdisk/IOCTL_SFFDISK_DEVICE_PASSWORD"
req.header: sffdisk.h
req.include-header: Sffdisk.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- sffdisk.h
api_name:
- IOCTL_SFFDISK_DEVICE_PASSWORD
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SFFDISK_DEVICE_PASSWORD IOCTL


## -description


User-mode applications use this IOCTL to perform basic operations on a Secure Digital (SD) card, such as setting the password on the card, resetting the card, or locking and unlocking the card. For a description of this command, see the <i>Secure Digital I/O (SDIO)</i> specification.

To perform this operation, call the <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> function (described in the Microsoft Windows SDK documentation) using the following parameters.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>bRet = DeviceIoControl (
    (HANDLE)  hDevice, 
    (DWORD)  dwIoControlCode, 
    (PUCHAR)  lpInBuffer,
    (DWORD)  nInBufferSize, 
    (PUCHAR)  lpOutBuffer,
    (DWORD)  nOutBufferSize, 
    (LPDWORD)  lpBytesReturned,
    (LPOVERLAPPED)  lpOverlapped 
  );</pre>
</td>
</tr>
</table></span></div>
Parameters


<dl>
<dt><a id="hDevice"></a><a id="hdevice"></a><a id="HDEVICE"></a><i>hDevice</i></dt>
<dd>
The handle to a volume in the SD stack.

</dd>
<dt><a id="dwIoControlCode"></a><a id="dwiocontrolcode"></a><a id="DWIOCONTROLCODE"></a><i>dwIoControlCode</i></dt>
<dd>
The control code for the operation. This value identifies the specific operation to be performed and the type of device on which to perform it. Use IOCTL_SFFDISK_DEVICE_PASSWORD for this operation.

</dd>
<dt><a id="lpInBuffer"></a><a id="lpinbuffer"></a><a id="LPINBUFFER"></a><i>lpInBuffer</i></dt>
<dd>
Pointer to the input buffer. Caller must initialize a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff538136(v=vs.85)">SFFDISK_DEVICE_PASSWORD_DATA</a> structure and store it at the beginning of the buffer. Immediately following the SFFDISK_DEVICE_PASSWORD_DATA structure, caller must pass in NULL terminated strings for the old and the new password. The current (old) password is first, and it is immediately followed by the new password. 

</dd>
<dt><a id="nInBufferSize"></a><a id="ninbuffersize"></a><a id="NINBUFFERSIZE"></a><i>nInBufferSize</i></dt>
<dd>
Indicates the size in bytes of the input buffer pointed to by the <i>lpInBuffer</i> parameter. The size of the input buffer should be the sum of <b>sizeof</b>(SFFDISK_DEVICE_PASSWORD_DATA) and the size, in bytes, of the password information that follow it.

</dd>
<dt><a id="lpOutBuffer"></a><a id="lpoutbuffer"></a><a id="LPOUTBUFFER"></a><i>lpOutBuffer</i></dt>
<dd>
Pointer to the output buffer that contains the results of the operation. If the operation fails and <b>GetLastError</b> returns the error code STATUS_BUFFER_TOO_SMALL, the output buffer was not large enough to hold the results data. 

</dd>
<dt><a id="nOutBufferSize"></a><a id="noutbuffersize"></a><a id="NOUTBUFFERSIZE"></a><i>nOutBufferSize</i></dt>
<dd>
Contains the size, in bytes, of the output buffer pointed to by the <i>lpOutBuffer</i> parameter.

</dd>
<dt><a id="lpBytesReturned"></a><a id="lpbytesreturned"></a><a id="LPBYTESRETURNED"></a><i>lpBytesReturned</i></dt>
<dd>
Pointer to a variable that receives the size, in bytes, of the results data stored in the buffer pointed to by <i>lpOutBuffer</i>. 

If the output buffer is too small to hold the return data then it will contain a value of zero on output, the call will fail, and <b>GetLastError</b> will return the error code ERROR_INSUFFICIENT_BUFFER. In case. 

If <i>lpOverlapped</i> is <b>NULL</b> (nonoverlapped I/O), caller cannot assign a <b>NULL</b> to <i>lpBytesReturned</i> parameter on input. If <i>lpOverlapped</i> is not <b>NULL</b> (overlapped I/O), caller can assign a <b>NULL</b> to the <i>lpBytesReturned</i> parameter. 

If this is an overlapped operation, you can retrieve the number of bytes returned by calling the <b>GetOverlappedResult</b> function. If <i>hDevice</i> is associated with an I/O completion port, you can get the number of bytes returned by calling the <b>GetQueuedCompletionStatus</b> function. For a description of the <b>GetOverlappedResult</b> and <b>GetQueuedCompletionStatus</b> functions see the Windows SDK documentation.

</dd>
<dt><a id="lpOverlapped"></a><a id="lpoverlapped"></a><a id="LPOVERLAPPED"></a><i>lpOverlapped</i></dt>
<dd>
Pointer to an OVERLAPPED structure, as described in the Windows SDK documentation. 

If the caller opened the device with the FILE_FLAG_OVERLAPPED flag, <i>lpOverlapped</i> must point to a valid OVERLAPPED structure. In this case, the system executes <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> as an overlapped, asynchronous operation. If the caller opened the device with the FILE_FLAG_OVERLAPPED flag, and <i>lpOverlapped</i> is <b>NULL</b>, the function fails in unpredictable ways.

If the caller opened the device without specifying the FILE_FLAG_OVERLAPPED flag, the system ignores the value in <i>lpOverlapped</i>, and the <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> function does not return until the operation has been completed, or until an error occurs.

</dd>
</dl>

## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the operation succeeds, <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> returns a nonzero value.

If the operation fails, <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> returns zero. To get extended error information, call <b>GetLastError</b>.

