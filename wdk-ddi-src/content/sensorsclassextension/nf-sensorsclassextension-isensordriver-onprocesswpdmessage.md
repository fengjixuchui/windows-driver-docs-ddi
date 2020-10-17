---
UID: NF:sensorsclassextension.ISensorDriver.OnProcessWpdMessage
title: ISensorDriver::OnProcessWpdMessage (sensorsclassextension.h)
description: The ISensorDriver::OnProcessWpdMessage method handles Windows Portable Device (WPD) commands that the ISensorClassExtension::ProcessIoControl method does not handle internally.
old-location: sensors\isensordriver_onprocesswpdmessage.htm
tech.root: sensors
ms.assetid: 4780d0ea-a54a-4125-b3b6-2210a14eff71
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnProcessWpdMessage"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnProcessWpdMessage method, ISensorDriver.OnProcessWpdMessage, ISensorDriver::OnProcessWpdMessage, OnProcessWpdMessage, OnProcessWpdMessage method [Sensor Devices], OnProcessWpdMessage method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_onprocesswpdmessage, sensorsclassextension/ISensorDriver::OnProcessWpdMessage
req.header: sensorsclassextension.h
req.include-header: 
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ISensorDriver::OnProcessWpdMessage
 - sensorsclassextension/ISensorDriver::OnProcessWpdMessage
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - SensorsClassExtension.lib
 - SensorsClassExtension.dll
api_name:
 - OnProcessWpdMessage
---

# ISensorDriver::OnProcessWpdMessage


## -description

The <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onprocesswpdmessage">ISensorDriver::OnProcessWpdMessage</a> method handles Windows Portable Device (WPD) commands that the <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensorclassextension-processiocontrol">ISensorClassExtension::ProcessIoControl</a> method does not handle internally.

## -parameters

### -param pUnkPortableDeviceValuesParams

A pointer to the IUnknown interface that supports the IPortableDeviceValues interface. The object that is associated with this IUnknown interface contains the parameters for the WPD command. For more information, see IPortableDeviceValues in Windows Portable Devices.

### -param pUnkPortableDeviceValuesResults

A pointer to the IUnknown interface that supports the IPortableDeviceValues interface. The object that is associated with this IUnknown interface stores the results for the WPD command.

## -returns

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -remarks

This method enables you to extend the WPD commands and interfaces in a device-specific way.

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>