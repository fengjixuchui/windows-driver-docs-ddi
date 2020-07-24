---
UID: NF:wdfinstaller.WdfPostDeviceRemove
title: WdfPostDeviceRemove function (wdfinstaller.h)
description: The co-installer's WdfPostDeviceRemove function performs any operations that the co-installer might require after a non-Plug and Play (PnP) driver's installer has deleted the driver's kernel-mode service.
old-location: wdf\wdfpostdeviceremove.htm
tech.root: wdf
ms.assetid: f29579de-ba5d-4b7a-9aeb-558be03d7eef
ms.date: 02/26/2018
keywords: ["WdfPostDeviceRemove function"]
ms.keywords: DFCoinstallerRef_82480a49-b7ac-4e1d-b942-93d1eb8a5c34.xml, WdfPostDeviceRemove, WdfPostDeviceRemove function, kmdf.wdfpostdeviceremove, wdf.wdfpostdeviceremove, wdfinstaller/WdfPostDeviceRemove
f1_keywords:
 - "wdfinstaller/WdfPostDeviceRemove"
 - "WdfPostDeviceRemove"
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see Using the KMDF Co-installer.)
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- N/A
- N/A.dll
api_name:
- WdfPostDeviceRemove
targetos: Windows
req.typenames: 
---

# WdfPostDeviceRemove function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The co-installer's <b>WdfPostDeviceRemove</b> function performs any operations that the co-installer might require after a non-Plug and Play (PnP) driver's installer has deleted the driver's kernel-mode service. 


## -parameters




### -param InfPath [in]

A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <b>GetCurrentDirectory</b>, which is described in the Microsoft Windows SDK.


### -param InfSectionName [in, optional]

A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/installing-the-framework-s-co-installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.


## -returns



<b>WdfPostDeviceRemove</b> returns ERROR_SUCCESS if the operation succeeds. Otherwise, the function returns one of the additional ERROR_<i>XXX</i> values that are defined in <i>Winerror.h</i>.




## -remarks



The installer for the framework-based drivers of a non-PnP device must call <b>WdfPostDeviceRemove</b> after the installer calls <b>DeleteService</b>.

To obtain the address of the co-installer's <b>WdfPostDeviceRemove</b> function, the installer must call <b>GetProcAddress</b> after the installer has called <b>LoadLibrary</b> to load the co-installer.

For more information about the <b>WdfPostDeviceRemove</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/installing-a-non-pnp-driver">Installing a Non-PnP Driver</a>. For more information about <b>DeleteService</b>, <b>GetProcAddress</b>, and <b>LoadLibrary</b>, see the Microsoft Windows SDK documentation.


#### Examples

For a code example that uses the <b>WdfPostDeviceRemove</b> function, see the installer for the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">NONPNP</a> sample.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinstaller/nf-wdfinstaller-wdfpredeviceremove">WdfPreDeviceRemove</a>
 

 

