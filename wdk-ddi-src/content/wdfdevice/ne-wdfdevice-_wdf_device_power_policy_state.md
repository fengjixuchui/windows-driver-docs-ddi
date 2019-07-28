---
UID: NE:wdfdevice._WDF_DEVICE_POWER_POLICY_STATE
title: _WDF_DEVICE_POWER_POLICY_STATE (wdfdevice.h)
description: The WDF_DEVICE_POWER_POLICY_STATE enumeration identifies all of the states that the framework's power policy state machine can enter.
old-location: wdf\wdf_device_power_policy_state.htm
tech.root: wdf
ms.assetid: 87fa78f7-417a-4720-9520-0eb90486630a
ms.date: 02/26/2018
ms.keywords: "*PWDF_DEVICE_POWER_POLICY_STATE, DFDeviceObjectGeneralRef_c80b69a2-86ba-4826-a48b-0ea80b47be01.xml, PWDF_DEVICE_POWER_POLICY_STATE, PWDF_DEVICE_POWER_POLICY_STATE enumeration pointer, WDF_DEVICE_POWER_POLICY_STATE, WDF_DEVICE_POWER_POLICY_STATE enumeration, WdfDevStatePwrPolCancelUsbSS, WdfDevStatePwrPolCancelingUsbSSForSystemSleep, WdfDevStatePwrPolCancelingWakeForSystemSleep, WdfDevStatePwrPolCancelingWakeForSystemSleepWakeCanceled, WdfDevStatePwrPolCheckPowerPageable, WdfDevStatePwrPolDeviceD0PowerRequestFailed, WdfDevStatePwrPolDeviceIdleReturnToActive, WdfDevStatePwrPolDeviceIdleSleeping, WdfDevStatePwrPolDeviceIdleStopping, WdfDevStatePwrPolDevicePowerRequestFailed, WdfDevStatePwrPolDisarmingWakeForSystemSleepCompletePowerUp, WdfDevStatePwrPolDx, WdfDevStatePwrPolFinal, WdfDevStatePwrPolGotoD0, WdfDevStatePwrPolGotoD0InD0, WdfDevStatePwrPolGotoDx, WdfDevStatePwrPolGotoDxInDx, WdfDevStatePwrPolIdleCapableDeviceIdle, WdfDevStatePwrPolInvalid, WdfDevStatePwrPolIoPresentArmed, WdfDevStatePwrPolIoPresentArmedWakeCanceled, WdfDevStatePwrPolNull, WdfDevStatePwrPolObjectCreated, WdfDevStatePwrPolPowerUpForSystemSleepFailed, WdfDevStatePwrPolPowerUpForSystemSleepNotSeen, WdfDevStatePwrPolRemoved, WdfDevStatePwrPolRestarting, WdfDevStatePwrPolRestartingFailed, WdfDevStatePwrPolS0NoWakeCompletePowerUp, WdfDevStatePwrPolS0NoWakePowerUp, WdfDevStatePwrPolS0WakeCompletePowerUp, WdfDevStatePwrPolS0WakeDisarm, WdfDevStatePwrPolSleeping, WdfDevStatePwrPolSleepingNoWakeCompletePowerDown, WdfDevStatePwrPolSleepingNoWakeDxRequestFailed, WdfDevStatePwrPolSleepingNoWakePowerDown, WdfDevStatePwrPolSleepingPowerDownNotProcessed, WdfDevStatePwrPolSleepingSendWake, WdfDevStatePwrPolSleepingWakePowerDown, WdfDevStatePwrPolSleepingWakePowerDownFailed, WdfDevStatePwrPolSleepingWakePowerDownFailedWakeCanceled, WdfDevStatePwrPolSleepingWakeRevertArmWake, WdfDevStatePwrPolSleepingWakeRevertArmWakeNP, WdfDevStatePwrPolSleepingWakeWakeArrived, WdfDevStatePwrPolSleepingWakeWakeArrivedNP, WdfDevStatePwrPolStarted, WdfDevStatePwrPolStartedCancelTimer, WdfDevStatePwrPolStartedIdleCapable, WdfDevStatePwrPolStartedIdleCapableCancelTimerForSleep, WdfDevStatePwrPolStartedIdleCapableWaitForIdleTimeout, WdfDevStatePwrPolStartedWaitForIdleTimeout, WdfDevStatePwrPolStartedWakeCapable, WdfDevStatePwrPolStartedWakeCapableCancelTimerForSleep, WdfDevStatePwrPolStartedWakeCapableSleepingUsbSS, WdfDevStatePwrPolStartedWakeCapableWaitForIdleTimeout, WdfDevStatePwrPolStarting, WdfDevStatePwrPolStartingDecideS0Wake, WdfDevStatePwrPolStartingFailed, WdfDevStatePwrPolStartingPoweredUp, WdfDevStatePwrPolStartingPoweredUpFailed, WdfDevStatePwrPolStartingSucceeded, WdfDevStatePwrPolStopped, WdfDevStatePwrPolStoppedRemoving, WdfDevStatePwrPolStopping, WdfDevStatePwrPolStoppingCancelTimer, WdfDevStatePwrPolStoppingCancelUsbSS, WdfDevStatePwrPolStoppingCancelWake, WdfDevStatePwrPolStoppingD0, WdfDevStatePwrPolStoppingD0CancelUsbSS, WdfDevStatePwrPolStoppingD0Failed, WdfDevStatePwrPolStoppingDisarmWake, WdfDevStatePwrPolStoppingDisarmWakeCancelWake, WdfDevStatePwrPolStoppingDisarmWakeWakeCanceled, WdfDevStatePwrPolStoppingFailed, WdfDevStatePwrPolStoppingPoweringDown, WdfDevStatePwrPolStoppingPoweringUp, WdfDevStatePwrPolStoppingResetDevice, WdfDevStatePwrPolStoppingResetDeviceCompletePowerUp, WdfDevStatePwrPolStoppingResetDeviceFailed, WdfDevStatePwrPolStoppingSendStatus, WdfDevStatePwrPolStoppingWaitForIdleTimeout, WdfDevStatePwrPolStoppingWaitForUsbSSCompletion, WdfDevStatePwrPolStoppingWaitingForImplicitPowerDown, WdfDevStatePwrPolSystemAsleepNoWake, WdfDevStatePwrPolSystemAsleepWakeArmed, WdfDevStatePwrPolSystemAsleepWakeArmedNP, WdfDevStatePwrPolSystemSleepFromDeviceWaitingUnarmed, WdfDevStatePwrPolSystemSleepNeedWake, WdfDevStatePwrPolSystemSleepNeedWakeCompletePowerUp, WdfDevStatePwrPolSystemSleepPowerRequestFailed, WdfDevStatePwrPolSystemWakeDeviceToD0, WdfDevStatePwrPolSystemWakeDeviceToD0CompletePowerUp, WdfDevStatePwrPolSystemWakeDeviceWakeCompletePowerUp, WdfDevStatePwrPolSystemWakeDeviceWakeDisabled, WdfDevStatePwrPolSystemWakeDeviceWakeDisarm, WdfDevStatePwrPolSystemWakeDeviceWakeDisarmNP, WdfDevStatePwrPolSystemWakeDeviceWakeEnabled, WdfDevStatePwrPolSystemWakeDeviceWakeEnabledNP, WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceled, WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceledNP, WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFired, WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFiredNP, WdfDevStatePwrPolSystemWakeDeviceWakeTriggered, WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredNP, WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0, WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0NP, WdfDevStatePwrPolSystemWakeDeviceWokeDisarm, WdfDevStatePwrPolSystemWakeDeviceWokeDisarmNP, WdfDevStatePwrPolSystemWakeQueryIdle, WdfDevStatePwrPolTimerExpiredDecideUsbSS, WdfDevStatePwrPolTimerExpiredNoWake, WdfDevStatePwrPolTimerExpiredNoWakeCompletePowerDown, WdfDevStatePwrPolTimerExpiredNoWakePowerDownNotProcessed, WdfDevStatePwrPolTimerExpiredNoWakePoweredDownDisableIdleTimer, WdfDevStatePwrPolTimerExpiredNoWakeReturnToActive, WdfDevStatePwrPolTimerExpiredNoWakeUndoPowerDown, WdfDevStatePwrPolTimerExpiredWakeCapableCancelWake, WdfDevStatePwrPolTimerExpiredWakeCapableCleanup, WdfDevStatePwrPolTimerExpiredWakeCapableDxAllocFailed, WdfDevStatePwrPolTimerExpiredWakeCapablePowerDown, WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedCancelWake, WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedUsbSS, WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeCanceled, WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeInterruptArrived, WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownNotProcessed, WdfDevStatePwrPolTimerExpiredWakeCapableSendWake, WdfDevStatePwrPolTimerExpiredWakeCapableUndoPowerDown, WdfDevStatePwrPolTimerExpiredWakeCapableUsbSS, WdfDevStatePwrPolTimerExpiredWakeCapableWakeArrived, WdfDevStatePwrPolTimerExpiredWakeCapableWakeCanceled, WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailed, WdfDevStatePwrPolTimerExpiredWakeCapableWakeInterruptArrived, WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceeded, WdfDevStatePwrPolTimerExpiredWakeCompletedDisarm, WdfDevStatePwrPolTimerExpiredWakeCompletedHardwareStarted, WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDown, WdfDevStatePwrPolTimerExpiredWakeCompletedPowerUp, WdfDevStatePwrPolTimerExpiredWakeSucceeded, WdfDevStatePwrPolWaitingArmed, WdfDevStatePwrPolWaitingArmedIoPresentCancelUsbSS, WdfDevStatePwrPolWaitingArmedQueryIdle, WdfDevStatePwrPolWaitingArmedStoppingCancelUsbSS, WdfDevStatePwrPolWaitingArmedUsbSS, WdfDevStatePwrPolWaitingArmedWakeFailedCancelUsbSS, WdfDevStatePwrPolWaitingArmedWakeInterruptFired, WdfDevStatePwrPolWaitingArmedWakeInterruptFiredDuringPowerDown, WdfDevStatePwrPolWaitingArmedWakeSucceededCancelUsbSS, WdfDevStatePwrPolWaitingUnarmed, WdfDevStatePwrPolWaitingUnarmedQueryIdle, WdfDevStatePwrPolWakeCapableDeviceIdle, WdfDevStatePwrPolWakeCapableUsbSSCompleted, WdfDevStatePwrPolWakeFailedUsbSS, WdfDevStatePwrPolWokeFromS0, WdfDevStatePwrPolWokeFromS0NotifyDriver, WdfDevStatePwrPolWokeFromS0UsbSS, _WDF_DEVICE_POWER_POLICY_STATE, kmdf.wdf_device_power_policy_state, wdf.wdf_device_power_policy_state, wdfdevice/PWDF_DEVICE_POWER_POLICY_STATE, wdfdevice/WDF_DEVICE_POWER_POLICY_STATE, wdfdevice/WdfDevStatePwrPolCancelUsbSS, wdfdevice/WdfDevStatePwrPolCancelingUsbSSForSystemSleep, wdfdevice/WdfDevStatePwrPolCancelingWakeForSystemSleep, wdfdevice/WdfDevStatePwrPolCancelingWakeForSystemSleepWakeCanceled, wdfdevice/WdfDevStatePwrPolCheckPowerPageable, wdfdevice/WdfDevStatePwrPolDeviceD0PowerRequestFailed, wdfdevice/WdfDevStatePwrPolDeviceIdleReturnToActive, wdfdevice/WdfDevStatePwrPolDeviceIdleSleeping, wdfdevice/WdfDevStatePwrPolDeviceIdleStopping, wdfdevice/WdfDevStatePwrPolDevicePowerRequestFailed, wdfdevice/WdfDevStatePwrPolDisarmingWakeForSystemSleepCompletePowerUp, wdfdevice/WdfDevStatePwrPolDx, wdfdevice/WdfDevStatePwrPolFinal, wdfdevice/WdfDevStatePwrPolGotoD0, wdfdevice/WdfDevStatePwrPolGotoD0InD0, wdfdevice/WdfDevStatePwrPolGotoDx, wdfdevice/WdfDevStatePwrPolGotoDxInDx, wdfdevice/WdfDevStatePwrPolIdleCapableDeviceIdle, wdfdevice/WdfDevStatePwrPolInvalid, wdfdevice/WdfDevStatePwrPolIoPresentArmed, wdfdevice/WdfDevStatePwrPolIoPresentArmedWakeCanceled, wdfdevice/WdfDevStatePwrPolNull, wdfdevice/WdfDevStatePwrPolObjectCreated, wdfdevice/WdfDevStatePwrPolPowerUpForSystemSleepFailed, wdfdevice/WdfDevStatePwrPolPowerUpForSystemSleepNotSeen, wdfdevice/WdfDevStatePwrPolRemoved, wdfdevice/WdfDevStatePwrPolRestarting, wdfdevice/WdfDevStatePwrPolRestartingFailed, wdfdevice/WdfDevStatePwrPolS0NoWakeCompletePowerUp, wdfdevice/WdfDevStatePwrPolS0NoWakePowerUp, wdfdevice/WdfDevStatePwrPolS0WakeCompletePowerUp, wdfdevice/WdfDevStatePwrPolS0WakeDisarm, wdfdevice/WdfDevStatePwrPolSleeping, wdfdevice/WdfDevStatePwrPolSleepingNoWakeCompletePowerDown, wdfdevice/WdfDevStatePwrPolSleepingNoWakeDxRequestFailed, wdfdevice/WdfDevStatePwrPolSleepingNoWakePowerDown, wdfdevice/WdfDevStatePwrPolSleepingPowerDownNotProcessed, wdfdevice/WdfDevStatePwrPolSleepingSendWake, wdfdevice/WdfDevStatePwrPolSleepingWakePowerDown, wdfdevice/WdfDevStatePwrPolSleepingWakePowerDownFailed, wdfdevice/WdfDevStatePwrPolSleepingWakePowerDownFailedWakeCanceled, wdfdevice/WdfDevStatePwrPolSleepingWakeRevertArmWake, wdfdevice/WdfDevStatePwrPolSleepingWakeRevertArmWakeNP, wdfdevice/WdfDevStatePwrPolSleepingWakeWakeArrived, wdfdevice/WdfDevStatePwrPolSleepingWakeWakeArrivedNP, wdfdevice/WdfDevStatePwrPolStarted, wdfdevice/WdfDevStatePwrPolStartedCancelTimer, wdfdevice/WdfDevStatePwrPolStartedIdleCapable, wdfdevice/WdfDevStatePwrPolStartedIdleCapableCancelTimerForSleep, wdfdevice/WdfDevStatePwrPolStartedIdleCapableWaitForIdleTimeout, wdfdevice/WdfDevStatePwrPolStartedWaitForIdleTimeout, wdfdevice/WdfDevStatePwrPolStartedWakeCapable, wdfdevice/WdfDevStatePwrPolStartedWakeCapableCancelTimerForSleep, wdfdevice/WdfDevStatePwrPolStartedWakeCapableSleepingUsbSS, wdfdevice/WdfDevStatePwrPolStartedWakeCapableWaitForIdleTimeout, wdfdevice/WdfDevStatePwrPolStarting, wdfdevice/WdfDevStatePwrPolStartingDecideS0Wake, wdfdevice/WdfDevStatePwrPolStartingFailed, wdfdevice/WdfDevStatePwrPolStartingPoweredUp, wdfdevice/WdfDevStatePwrPolStartingPoweredUpFailed, wdfdevice/WdfDevStatePwrPolStartingSucceeded, wdfdevice/WdfDevStatePwrPolStopped, wdfdevice/WdfDevStatePwrPolStoppedRemoving, wdfdevice/WdfDevStatePwrPolStopping, wdfdevice/WdfDevStatePwrPolStoppingCancelTimer, wdfdevice/WdfDevStatePwrPolStoppingCancelUsbSS, wdfdevice/WdfDevStatePwrPolStoppingCancelWake, wdfdevice/WdfDevStatePwrPolStoppingD0, wdfdevice/WdfDevStatePwrPolStoppingD0CancelUsbSS, wdfdevice/WdfDevStatePwrPolStoppingD0Failed, wdfdevice/WdfDevStatePwrPolStoppingDisarmWake, wdfdevice/WdfDevStatePwrPolStoppingDisarmWakeCancelWake, wdfdevice/WdfDevStatePwrPolStoppingDisarmWakeWakeCanceled, wdfdevice/WdfDevStatePwrPolStoppingFailed, wdfdevice/WdfDevStatePwrPolStoppingPoweringDown, wdfdevice/WdfDevStatePwrPolStoppingPoweringUp, wdfdevice/WdfDevStatePwrPolStoppingResetDevice, wdfdevice/WdfDevStatePwrPolStoppingResetDeviceCompletePowerUp, wdfdevice/WdfDevStatePwrPolStoppingResetDeviceFailed, wdfdevice/WdfDevStatePwrPolStoppingSendStatus, wdfdevice/WdfDevStatePwrPolStoppingWaitForIdleTimeout, wdfdevice/WdfDevStatePwrPolStoppingWaitForUsbSSCompletion, wdfdevice/WdfDevStatePwrPolStoppingWaitingForImplicitPowerDown, wdfdevice/WdfDevStatePwrPolSystemAsleepNoWake, wdfdevice/WdfDevStatePwrPolSystemAsleepWakeArmed, wdfdevice/WdfDevStatePwrPolSystemAsleepWakeArmedNP, wdfdevice/WdfDevStatePwrPolSystemSleepFromDeviceWaitingUnarmed, wdfdevice/WdfDevStatePwrPolSystemSleepNeedWake, wdfdevice/WdfDevStatePwrPolSystemSleepNeedWakeCompletePowerUp, wdfdevice/WdfDevStatePwrPolSystemSleepPowerRequestFailed, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceToD0, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceToD0CompletePowerUp, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeCompletePowerUp, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeDisabled, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeDisarm, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeDisarmNP, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeEnabled, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeEnabledNP, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceled, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceledNP, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFired, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFiredNP, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeTriggered, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredNP, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0NP, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWokeDisarm, wdfdevice/WdfDevStatePwrPolSystemWakeDeviceWokeDisarmNP, wdfdevice/WdfDevStatePwrPolSystemWakeQueryIdle, wdfdevice/WdfDevStatePwrPolTimerExpiredDecideUsbSS, wdfdevice/WdfDevStatePwrPolTimerExpiredNoWake, wdfdevice/WdfDevStatePwrPolTimerExpiredNoWakeCompletePowerDown, wdfdevice/WdfDevStatePwrPolTimerExpiredNoWakePowerDownNotProcessed, wdfdevice/WdfDevStatePwrPolTimerExpiredNoWakePoweredDownDisableIdleTimer, wdfdevice/WdfDevStatePwrPolTimerExpiredNoWakeReturnToActive, wdfdevice/WdfDevStatePwrPolTimerExpiredNoWakeUndoPowerDown, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableCancelWake, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableCleanup, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableDxAllocFailed, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapablePowerDown, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedCancelWake, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedUsbSS, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeCanceled, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeInterruptArrived, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownNotProcessed, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableSendWake, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableUndoPowerDown, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableUsbSS, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableWakeArrived, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableWakeCanceled, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailed, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableWakeInterruptArrived, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceeded, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCompletedDisarm, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCompletedHardwareStarted, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDown, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeCompletedPowerUp, wdfdevice/WdfDevStatePwrPolTimerExpiredWakeSucceeded, wdfdevice/WdfDevStatePwrPolWaitingArmed, wdfdevice/WdfDevStatePwrPolWaitingArmedIoPresentCancelUsbSS, wdfdevice/WdfDevStatePwrPolWaitingArmedQueryIdle, wdfdevice/WdfDevStatePwrPolWaitingArmedStoppingCancelUsbSS, wdfdevice/WdfDevStatePwrPolWaitingArmedUsbSS, wdfdevice/WdfDevStatePwrPolWaitingArmedWakeFailedCancelUsbSS, wdfdevice/WdfDevStatePwrPolWaitingArmedWakeInterruptFired, wdfdevice/WdfDevStatePwrPolWaitingArmedWakeInterruptFiredDuringPowerDown, wdfdevice/WdfDevStatePwrPolWaitingArmedWakeSucceededCancelUsbSS, wdfdevice/WdfDevStatePwrPolWaitingUnarmed, wdfdevice/WdfDevStatePwrPolWaitingUnarmedQueryIdle, wdfdevice/WdfDevStatePwrPolWakeCapableDeviceIdle, wdfdevice/WdfDevStatePwrPolWakeCapableUsbSSCompleted, wdfdevice/WdfDevStatePwrPolWakeFailedUsbSS, wdfdevice/WdfDevStatePwrPolWokeFromS0, wdfdevice/WdfDevStatePwrPolWokeFromS0NotifyDriver, wdfdevice/WdfDevStatePwrPolWokeFromS0UsbSS"
ms.topic: enum
f1_keywords:
 - "wdfdevice/WDF_DEVICE_POWER_POLICY_STATE"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_DEVICE_POWER_POLICY_STATE
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_POWER_POLICY_STATE, *PWDF_DEVICE_POWER_POLICY_STATE
---

# _WDF_DEVICE_POWER_POLICY_STATE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The WDF_DEVICE_POWER_POLICY_STATE enumeration identifies all of the states that the framework's power policy state machine can enter.


## -enum-fields




### -field WdfDevStatePwrPolInvalid


### -field WdfDevStatePwrPolObjectCreated


### -field WdfDevStatePwrPolStarting


### -field WdfDevStatePwrPolStartingSucceeded


### -field WdfDevStatePwrPolStartingFailed


### -field WdfDevStatePwrPolStartingDecideS0Wake


### -field WdfDevStatePwrPolStartedIdleCapable


### -field WdfDevStatePwrPolTimerExpiredNoWake


### -field WdfDevStatePwrPolTimerExpiredNoWakeCompletePowerDown


### -field WdfDevStatePwrPolWaitingUnarmed


### -field WdfDevStatePwrPolWaitingUnarmedQueryIdle


### -field WdfDevStatePwrPolS0NoWakePowerUp


### -field WdfDevStatePwrPolS0NoWakeCompletePowerUp


### -field WdfDevStatePwrPolSystemSleepFromDeviceWaitingUnarmed


### -field WdfDevStatePwrPolSystemSleepNeedWake


### -field WdfDevStatePwrPolSystemSleepNeedWakeCompletePowerUp


### -field WdfDevStatePwrPolSystemSleepPowerRequestFailed


### -field WdfDevStatePwrPolCheckPowerPageable


### -field WdfDevStatePwrPolSleepingWakeWakeArrived


### -field WdfDevStatePwrPolSleepingWakeRevertArmWake


### -field WdfDevStatePwrPolSystemAsleepWakeArmed


### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabled


### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceled


### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisarm


### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggered


### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0


### -field WdfDevStatePwrPolSystemWakeDeviceWokeDisarm


### -field WdfDevStatePwrPolSleepingWakeWakeArrivedNP


### -field WdfDevStatePwrPolSleepingWakeRevertArmWakeNP


### -field WdfDevStatePwrPolSleepingWakePowerDownFailed


### -field WdfDevStatePwrPolSleepingWakePowerDownFailedWakeCanceled


### -field WdfDevStatePwrPolSystemAsleepWakeArmedNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceledNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisarmNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0NP


### -field WdfDevStatePwrPolSystemWakeDeviceWokeDisarmNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeCompletePowerUp


### -field WdfDevStatePwrPolSleeping


### -field WdfDevStatePwrPolSleepingNoWakePowerDown


### -field WdfDevStatePwrPolSleepingNoWakeCompletePowerDown


### -field WdfDevStatePwrPolSleepingNoWakeDxRequestFailed


### -field WdfDevStatePwrPolSleepingWakePowerDown


### -field WdfDevStatePwrPolSleepingSendWake


### -field WdfDevStatePwrPolSystemAsleepNoWake


### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisabled


### -field WdfDevStatePwrPolSystemWakeDeviceToD0


### -field WdfDevStatePwrPolSystemWakeDeviceToD0CompletePowerUp


### -field WdfDevStatePwrPolSystemWakeQueryIdle


### -field WdfDevStatePwrPolStartedWakeCapable


### -field WdfDevStatePwrPolTimerExpiredDecideUsbSS


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDown


### -field WdfDevStatePwrPolTimerExpiredWakeCapableSendWake


### -field WdfDevStatePwrPolTimerExpiredWakeCapableUsbSS


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeArrived


### -field WdfDevStatePwrPolTimerExpiredWakeCapableCancelWake


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeCanceled


### -field WdfDevStatePwrPolTimerExpiredWakeCapableCleanup


### -field WdfDevStatePwrPolTimerExpiredWakeCapableDxAllocFailed


### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDown


### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerUp


### -field WdfDevStatePwrPolWaitingArmedUsbSS


### -field WdfDevStatePwrPolWaitingArmed


### -field WdfDevStatePwrPolWaitingArmedQueryIdle


### -field WdfDevStatePwrPolIoPresentArmed


### -field WdfDevStatePwrPolIoPresentArmedWakeCanceled


### -field WdfDevStatePwrPolS0WakeDisarm


### -field WdfDevStatePwrPolS0WakeCompletePowerUp


### -field WdfDevStatePwrPolTimerExpiredWakeSucceeded


### -field WdfDevStatePwrPolTimerExpiredWakeCompletedDisarm


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceeded


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailed


### -field WdfDevStatePwrPolWakeFailedUsbSS


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedCancelWake


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeCanceled


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedUsbSS


### -field WdfDevStatePwrPolCancelingWakeForSystemSleep


### -field WdfDevStatePwrPolCancelingWakeForSystemSleepWakeCanceled


### -field WdfDevStatePwrPolDisarmingWakeForSystemSleepCompletePowerUp


### -field WdfDevStatePwrPolPowerUpForSystemSleepFailed


### -field WdfDevStatePwrPolWokeFromS0UsbSS


### -field WdfDevStatePwrPolWokeFromS0


### -field WdfDevStatePwrPolWokeFromS0NotifyDriver


### -field WdfDevStatePwrPolStoppingResetDevice


### -field WdfDevStatePwrPolStoppingResetDeviceCompletePowerUp


### -field WdfDevStatePwrPolStoppingResetDeviceFailed


### -field WdfDevStatePwrPolStoppingD0


### -field WdfDevStatePwrPolStoppingD0Failed


### -field WdfDevStatePwrPolStoppingDisarmWake


### -field WdfDevStatePwrPolStoppingDisarmWakeCancelWake


### -field WdfDevStatePwrPolStoppingDisarmWakeWakeCanceled


### -field WdfDevStatePwrPolStopping


### -field WdfDevStatePwrPolStoppingFailed


### -field WdfDevStatePwrPolStoppingSendStatus


### -field WdfDevStatePwrPolStoppingCancelTimer


### -field WdfDevStatePwrPolStoppingWaitForIdleTimeout


### -field WdfDevStatePwrPolStoppingCancelUsbSS


### -field WdfDevStatePwrPolStoppingWaitForUsbSSCompletion


### -field WdfDevStatePwrPolStoppingCancelWake


### -field WdfDevStatePwrPolStopped


### -field WdfDevStatePwrPolCancelUsbSS


### -field WdfDevStatePwrPolStarted


### -field WdfDevStatePwrPolStartedCancelTimer


### -field WdfDevStatePwrPolStartedWaitForIdleTimeout


### -field WdfDevStatePwrPolStartedWakeCapableCancelTimerForSleep


### -field WdfDevStatePwrPolStartedWakeCapableWaitForIdleTimeout


### -field WdfDevStatePwrPolStartedWakeCapableSleepingUsbSS


### -field WdfDevStatePwrPolStartedIdleCapableCancelTimerForSleep


### -field WdfDevStatePwrPolStartedIdleCapableWaitForIdleTimeout


### -field WdfDevStatePwrPolDeviceD0PowerRequestFailed


### -field WdfDevStatePwrPolDevicePowerRequestFailed


### -field WdfDevStatePwrPolGotoDx


### -field WdfDevStatePwrPolGotoDxInDx


### -field WdfDevStatePwrPolDx


### -field WdfDevStatePwrPolGotoD0


### -field WdfDevStatePwrPolGotoD0InD0


### -field WdfDevStatePwrPolFinal


### -field WdfDevStatePwrPolSleepingPowerDownNotProcessed


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownNotProcessed


### -field WdfDevStatePwrPolTimerExpiredNoWakePowerDownNotProcessed


### -field WdfDevStatePwrPolTimerExpiredNoWakePoweredDownDisableIdleTimer


### -field WdfDevStatePwrPolStoppingWaitingForImplicitPowerDown


### -field WdfDevStatePwrPolStoppingPoweringUp


### -field WdfDevStatePwrPolStoppingPoweringDown


### -field WdfDevStatePwrPolPowerUpForSystemSleepNotSeen


### -field WdfDevStatePwrPolWaitingArmedStoppingCancelUsbSS


### -field WdfDevStatePwrPolWaitingArmedWakeFailedCancelUsbSS


### -field WdfDevStatePwrPolWaitingArmedIoPresentCancelUsbSS


### -field WdfDevStatePwrPolWaitingArmedWakeSucceededCancelUsbSS


### -field WdfDevStatePwrPolCancelingUsbSSForSystemSleep


### -field WdfDevStatePwrPolStoppingD0CancelUsbSS


### -field WdfDevStatePwrPolStartingPoweredUp


### -field WdfDevStatePwrPolIdleCapableDeviceIdle


### -field WdfDevStatePwrPolDeviceIdleReturnToActive


### -field WdfDevStatePwrPolDeviceIdleSleeping


### -field WdfDevStatePwrPolDeviceIdleStopping


### -field WdfDevStatePwrPolTimerExpiredNoWakeUndoPowerDown


### -field WdfDevStatePwrPolWakeCapableDeviceIdle


### -field WdfDevStatePwrPolWakeCapableUsbSSCompleted


### -field WdfDevStatePwrPolTimerExpiredWakeCapableUndoPowerDown


### -field WdfDevStatePwrPolTimerExpiredWakeCompletedHardwareStarted


### -field WdfDevStatePwrPolStoppedRemoving


### -field WdfDevStatePwrPolRemoved


### -field WdfDevStatePwrPolRestarting


### -field WdfDevStatePwrPolRestartingFailed


### -field WdfDevStatePwrPolStartingPoweredUpFailed


### -field WdfDevStatePwrPolTimerExpiredNoWakeReturnToActive


### -field WdfDevStatePwrPolWaitingArmedWakeInterruptFired


### -field WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFired


### -field WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFiredNP


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeInterruptArrived


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeInterruptArrived


### -field WdfDevStatePwrPolWaitingArmedWakeInterruptFiredDuringPowerDown


### -field WdfDevStatePwrPolNull


## -remarks



The WDF_DEVICE_POWER_POLICY_STATE enumeration is used as a member type in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_notification_data">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a> structure and as the return type for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerpolicystate">WdfDeviceGetDevicePowerPolicyState</a> method.



