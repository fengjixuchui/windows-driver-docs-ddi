---
UID: NF:sensorsclassextension.ISensorDriver.OnClientUnsubscribeFromEvents
title: ISensorDriver::OnClientUnsubscribeFromEvents (sensorsclassextension.h)
description: The ISensorDriver::OnClientUnsubscribeFromEvents method notifies the sensor driver that a client application no longer requests event notifications.
old-location: sensors\isensordriver_onclientunsubscribefromevents.htm
tech.root: sensors
ms.assetid: f51f1091-232f-4e41-9cc2-9938870aeef8
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnClientUnsubscribeFromEvents"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnClientUnsubscribeFromEvents method, ISensorDriver.OnClientUnsubscribeFromEvents, ISensorDriver::OnClientUnsubscribeFromEvents, OnClientUnsubscribeFromEvents, OnClientUnsubscribeFromEvents method [Sensor Devices], OnClientUnsubscribeFromEvents method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_onclientunsubscribefromevents, sensorsclassextension/ISensorDriver::OnClientUnsubscribeFromEvents
f1_keywords:
 - "sensorsclassextension/OnClientUnsubscribeFromEvents"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- SensorsClassExtension.lib
- SensorsClassExtension.dll
api_name:
- OnClientUnsubscribeFromEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorDriver::OnClientUnsubscribeFromEvents


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientunsubscribefromevents">ISensorDriver::OnClientUnsubscribeFromEvents</a> method notifies the sensor driver that a client application no longer requests event notifications.


## -parameters




### -param pClientFile

 Pointer to an IWDFFile interface that represents the file object for the application requesting cancellation of event notifications.


### -param pwszSensorID

LPWSTR that contains the ID for the sensor from which the client application is requesting cancellation of event notifications.


## -returns



If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



The sensor class extension calls this method in the following instances:

<ul>
<li>
An application unsubscribes from events.

</li>
<li>
An application closes normally.

</li>
<li>
The user revokes permission for an application to access the device that contains the specified sensor.

</li>
<li>
The sensor class extension is shutting down.

</li>
<li>
The cleanup work from a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensorclassextension-cleanupfile">ISensorClassExtension::CleanupFile</a> has completed.

</li>
</ul>
You can use this call as a signal to update the reference count of applications requesting events for the specified sensor.

For more information about how to use this method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/sensors/filtering-data">Filtering data</a>.

The ClientData structure is defined as follows.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>
 

 

