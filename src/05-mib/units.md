# Unit Parameters (Section 5.4)

## Overview
Unit parameters define controller-wide settings, status, and capabilities.

## 5.4.1 Startup Flash Parameter
**Object**: startupFlash  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Duration of startup flash mode after power-up or reset. Provides safe transition to normal operation.

## 5.4.2 Automatic Ped Clear Parameter
**Object**: autoPedClear  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Default pedestrian clearance time used when phase pedestrian clear parameter is 0.

## 5.4.3 Backup Time Parameter
**Object**: backupTime  
**Type**: INTEGER (0..255)  
**Units**: minutes  
**Access**: read-write  

Time without communication from management station before controller reverts to backup operation (e.g., time-based control).

## 5.4.4 Unit Red Revert Parameter
**Object**: unitRedRevert  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Default red revert time for all phases (overridden by phase-specific setting).

## 5.4.5 Unit Control Status
**Object**: unitControlStatus  
**Type**: BITS  
**Access**: read-only  

Controller-wide operational status:
- **unitFlash (0)**: Controller is in flash mode
- **unitAutomaticFlash (1)**: Automatic flash active
- **unitStartup (2)**: In startup mode
- **unitFreeCoordStatus (3)**: In free coordination
- **unitLocalFlash (4)**: Local flash active
- **unitIntervalAdvanceMode (5)**: Interval advance mode
- **unitExternalMinimumRecall (6)**: External minimum recall active
- **unitExternalMaximumRecall (7)**: External maximum recall active
- **unitExternalPedestrianRecall (8)**: External ped recall active
- **unitExternalNonLockingMemoryForDetectorInput (9)**: Non-locking detector memory
- **unitDimming (10)**: Signal dimming active
- **unitCentralControl (11)**: Under central control
- **unitCentralControlForceOff (12)**: Central force-off active

## 5.4.6 Unit Flash Status
**Object**: unitFlashStatus  
**Type**: INTEGER  
**Access**: read-only  

Reason for flash condition:
- **notFlash (1)**: Not flashing
- **automaticFlashSensor (2)**: Flash sensor activated
- **startupFlash (3)**: Startup flash in progress
- **freeCoordFlash (4)**: Free coordination flash
- **localManualFlash (5)**: Manual flash command
- **remoteManualFlash (6)**: Remote flash command
- **mmuFlash (7)**: MMU/CMU fault flash
- **powerFlash (8)**: Power-related flash
- **externalFlash (9)**: External flash input
- **other (10)**: Other reason

## 5.4.7 Unit Alarm Status 2
**Object**: unitAlarmStatus2  
**Type**: BITS  
**Access**: read-only  

Second set of alarm indicators:
- **coordinationAlarm (0)**: Coordination failure
- **localCycleError (1)**: Local cycle error
- **externalStart (2)**: External start signal
- **nvramErr (3)**: NVRAM error
- **configurationAlarm (4)**: Configuration problem
- **controllerVoltageLow (5)**: Low voltage detected
- **detectorPowerError (6)**: Detector power fault
- **port1Timeout (7)**: Port 1 timeout

## 5.4.8 Unit Alarm Status 1
**Object**: unitAlarmStatus1  
**Type**: BITS  
**Access**: read-only  

Primary alarm indicators:
- **localManualControlForFlash (0)**: Manual flash activated
- **localManualControlForFree (1)**: Manual free activated
- **externalMinRecallON (2)**: External min recall on
- **externalMaxRecallON (3)**: External max recall on
- **externalPedRecallON (4)**: External ped recall on
- **externalNonLockDetMemON (5)**: External non-lock detector memory
- **externalStart (6)**: External start
- **stop Time (7)**: Stop time active
- **redRevert (8)**: Red revert active
- **maximumVehicleRecallDefaultON (9)**: Max vehicle recall default on
- **pedestrianRecallDefaultON (10)**: Ped recall default on
- **cobaltManualFlash (11)**: Manual flash from front panel

## 5.4.9 Short Alarm Status
**Object**: shortAlarmStatus  
**Type**: OCTET STRING (SIZE(6))  
**Access**: read-only  

Condensed alarm status for compatibility with older protocols.

## 5.4.10 Unit Control
**Object**: unitControl  
**Type**: INTEGER  
**Access**: read-write  

Command the controller operational mode:
- **other (1)**: Other
- **systemAddressingFlash (2)**: Flash for addressing
- **systemCalibrationFlash (3)**: Flash for calibration
- **systemControllerFlash (4)**: Controller commanded flash
- **systemCallStandby (5)**: Standby mode
- **systemCallFree (6)**: Free mode
- **systemPatternControl (7)**: Pattern control
- **systemManualControl (8)**: Manual control
- **systemIntervalAdvance (9)**: Interval advance
- **systemStopTime (10)**: Stop time mode

## 5.4.11 Maximum Alarm Groups
**Object**: maxAlarmGroups  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of alarm groups.

## 5.4.12 Alarm Group Table

### 5.4.12.1 Alarm Group Number
**Object**: alarmGroupNumber  
**Type**: INTEGER (1..maxAlarmGroups)  
**Access**: not-accessible  

### 5.4.12.2 Alarm Group State
**Object**: alarmGroupState  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string of active alarms for all alarm inputs.

## 5.4.13 Maximum Special Function Outputs
**Object**: maxSpecialFunctionOutputs  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of special function outputs (auxiliary outputs for beacons, signs, etc.).

## 5.4.14 Special Function Output Table

### 5.4.14.1 Special Function Output Number
**Object**: specialFunctionOutputNumber  
**Type**: INTEGER (1..maxSpecialFunctionOutputs)  
**Access**: not-accessible  

### 5.4.14.2 Special Function Output State
**Object**: specialFunctionOutputState  
**Type**: INTEGER  
**Access**: read-only  

Current state of the output:
- **outputInactive (1)**: Not active
- **outputActive (2)**: Active

### 5.4.14.3 Special Function Output Control
**Object**: specialFunctionOutputControl  
**Type**: INTEGER  
**Access**: read-write  

Command the output:
- **outputControlOther (1)**: Other
- **outputControlOff (2)**: Turn off
- **outputControlOn (3)**: Turn on

### 5.4.14.4 Special Function Output Status
**Object**: specialFunctionOutputStatus  
**Type**: BITS  
**Access**: read-only  

Output status flags:
- **outputDriver (0)**: Driver is active
- **outputTimeBase (1)**: Activated by time base
- **outputExternal (2)**: Activated externally
- **outputLocal (3)**: Activated locally
- **outputRemote (4)**: Activated remotely

## 5.4.15 Remote Manual Control Timer
**Object**: remoteManualControlTimer  
**Type**: INTEGER (0..65535)  
**Units**: seconds  
**Access**: read-write  

Time remaining in remote manual control mode. Writing a value activates remote manual mode.

## 5.4.16 Remote Manual Control Advance Command
**Object**: remoteManualControlAdvanceCommand  
**Type**: INTEGER  
**Access**: read-write  

Advance to next phase or interval:
- **other (1)**
- **advanceToNextPhase (2)**
- **advanceToNextInterval (3)**

## 5.4.17 ASC Elevation—Antenna Offset
**Object**: ascElevationAntennaOffset  
**Type**: INTEGER (-100000..100000)  
**Units**: centimeters  
**Access**: read-write  

Elevation offset from GPS antenna to intersection reference point.

## 5.4.18 Startup Flash Mode
**Object**: startupFlashMode  
**Type**: INTEGER  
**Access**: read-write  

Type of startup flash to use:
- **startupFlashModeOther (1)**
- **startupFlashModeNone (2)**: No startup flash
- **startupFlashModeFlash (3)**: Flash mode
- **startupFlashModeRed (4)**: All red

## 5.4.19 Backup Timer Parameter—User Defined
**Object**: backupTimerUserDefined  
**Type**: INTEGER (0..65535)  
**Units**: minutes  
**Access**: read-write  

Enhanced backup timer with extended range.

## 5.4.20 Maximum Number of User Definable OIDs for Backup Timer
**Object**: maxBackupTimeUserDefinedOID  
**Type**: INTEGER (0..255)  
**Access**: read-only  

Maximum watchdog entries for backup timer.

## 5.4.21 Backup Time—User Defined Functions Table

### 5.4.21.1 Backup Time—User Defined Number
**Object**: backupTimeUserDefinedNumber  
**Type**: INTEGER (1..maxBackupTimeUserDefinedOID)  
**Access**: not-accessible  

### 5.4.21.2 Backup Time—User Defined OID
**Object**: backupTimeUserDefinedOID  
**Type**: OBJECT IDENTIFIER  
**Access**: read-write  

Object to monitor for backup timer watchdog.

### 5.4.21.3 Backup Time—User Defined Content Description
**Object**: backupTimeUserDefinedContentDescription  
**Type**: OCTET STRING  
**Access**: read-write  

Description of what is being monitored.

## 5.4.22 ASC Clock

### 5.4.22.1 Maximum Number of Time Sources
**Object**: maxTimeSources  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum time sources (GPS, NTP, etc.).

### 5.4.22.2 Unit Time Source Table

#### 5.4.22.2.1 Unit Time Source Index
**Object**: unitTimeSourceIndex  
**Type**: INTEGER (1..maxTimeSources)  
**Access**: not-accessible  

#### 5.4.22.2.2 Unit Time Source
**Object**: unitTimeSource  
**Type**: INTEGER  
**Access**: read-write  

Type of time source:
- **other (1)**
- **sntp (2)**: SNTP/NTP
- **gps (3)**: GPS
- **cdma (4)**: CDMA
- **wwvb (5)**: WWVB radio
- **ntcip1213 (6)**: NTCIP 1213 (central)

### 5.4.22.3 ASC Clock Source—Commanded
**Object**: ascClockSourceCommanded  
**Type**: INTEGER (0..maxTimeSources)  
**Access**: read-write  

Commanded time source (0 = controller decides).

### 5.4.22.4 ASC Clock Source—Current
**Object**: ascClockSourceCurrent  
**Type**: INTEGER (0..maxTimeSources)  
**Access**: read-only  

Currently active time source.

### 5.4.22.5 Unit Time Source Status
**Object**: unitTimeSourceStatus  
**Type**: BITS  
**Access**: read-only  

Status of each time source (bit per source):
- Bit = 1: Source is valid
- Bit = 0: Source is invalid

### 5.4.22.6 ASC Clock Non-Sequential Time Source
**Object**: ascClockNonSequentialTimeSource  
**Type**: INTEGER (0..maxTimeSources)  
**Access**: read-only  

Time source that last caused a non-sequential time change.

### 5.4.22.7 ASC Clock Non-Sequential Time Change
**Object**: ascClockNonSequentialTimeChange  
**Type**: INTEGER  
**Units**: seconds since epoch  
**Access**: read-only  

Timestamp of last non-sequential time change.

### 5.4.22.8 ASC Clock Non-Sequential Time Difference
**Object**: ascClockNonSequentialTimeDifference  
**Type**: INTEGER  
**Units**: milliseconds  
**Access**: read-only  

Magnitude of last non-sequential time change.

## 5.4.23 Communications

### 5.4.23.1 Maximum Communications Ports
**Object**: maxCommunicationsPorts  
**Type**: INTEGER (1..255)  
**Access**: read-only  

### 5.4.23.2 Communications Ports Table

#### 5.4.23.2.1 Communications Port Type
**Object**: communicationsPortType  
**Type**: INTEGER  
**Access**: read-only  

Port type:
- **other (1)**
- **ethernet (2)**
- **serial (3)**
- **usb (4)**

#### 5.4.23.2.2 Communications Port Type Number Parameter
**Object**: communicationsPortTypeNumber  
**Type**: INTEGER  
**Access**: not-accessible  

Port instance number.

#### 5.4.23.2.3 Communications Port Enable
**Object**: communicationsPortEnable  
**Type**: INTEGER  
**Access**: read-write  

Enable/disable port:
- **other (1)**
- **disabled (2)**
- **enabled (3)**

#### 5.4.23.2.4 Communications Port Protocol Supported
**Object**: communicationsPortProtocolSupported  
**Type**: BITS  
**Access**: read-only  

Supported protocols:
- **ntcip2301 (0)**: SNMP
- **ntcip2201 (1)**: FTP
- **ntcip1103 (2)**: TFTP
- **other protocols...**

#### 5.4.23.2.5 Communications Port Protocol
**Object**: communicationsPortProtocol  
**Type**: INTEGER  
**Access**: read-write  

Active protocol for this port.

#### 5.4.23.2.6 Communications Port Diagnostics
**Object**: communicationsPortDiagnostics  
**Type**: BITS  
**Access**: read-only  

Port diagnostic status:
- **linkStatus (0)**: Link is up
- **txActivity (1)**: Transmit activity
- **rxActivity (2)**: Receive activity

### 5.4.23.3 Maximum Ethernet Ports
**Object**: maxEthernetPorts  
**Type**: INTEGER (0..255)  
**Access**: read-only  

### 5.4.23.4 Ethernet Port Configuration Table

#### 5.4.23.4.1 IP Address Parameter
**Object**: ipAddress  
**Type**: IpAddress  
**Access**: read-only  

Current IP address.

#### 5.4.23.4.2 Net Mask Parameter
**Object**: netMask  
**Type**: IpAddress  
**Access**: read-only  

Current subnet mask.

#### 5.4.23.4.3 Gateway Parameter
**Object**: gateway  
**Type**: IpAddress  
**Access**: read-only  

Current default gateway.

#### 5.4.23.4.4 Domain Name Server Parameter
**Object**: domainNameServer  
**Type**: IpAddress  
**Access**: read-only  

Current DNS server.

#### 5.4.23.4.5 Ethernet Configuration Mode Parameter
**Object**: ethernetConfigurationMode  
**Type**: INTEGER  
**Access**: read-write  

Configuration method:
- **other (1)**
- **static (2)**: Static IP
- **dhcp (3)**: DHCP

#### 5.4.23.4.6 DHCP Logical Name Parameter
**Object**: dhcpLogicalName  
**Type**: DisplayString  
**Access**: read-write  

Logical name for DHCP requests.

#### 5.4.23.4.7 Static IP Address Parameter
**Object**: staticIpAddress  
**Type**: IpAddress  
**Access**: read-write  

Configured static IP address.

#### 5.4.23.4.8 Static Net Mask Parameter
**Object**: staticNetMask  
**Type**: IpAddress  
**Access**: read-write  

Configured static subnet mask.

#### 5.4.23.4.9 Static Gateway Parameter
**Object**: staticGateway  
**Type**: IpAddress  
**Access**: read-write  

Configured static gateway.

#### 5.4.23.4.10 Static Domain Name Server Parameter
**Object**: staticDomainNameServer  
**Type**: IpAddress  
**Access**: read-write  

Configured static DNS server.

### 5.4.23.5 Ethernet Communications Ports
Bit string of Ethernet port availability.

### 5.4.23.6 Asynchronous RS-232 Communications Ports
Bit string of async serial port availability.

### 5.4.23.7 Synchronous RS-232 Communications Ports
Bit string of sync serial port availability.

### 5.4.23.8 Port 1 Timeout Fault
**Object**: port1TimeoutFault  
**Type**: INTEGER  
**Access**: read-only  

NEMA TS 2 Port 1 timeout status:
- **other (1)**
- **notFault (2)**
- **fault (3)**

### 5.4.23.9 Serial Bus 1 Fault
**Object**: serialBus1Fault  
**Type**: INTEGER  
**Access**: read-only  

ITS Cabinet Serial Bus 1 fault status.

## 5.4.24 Maximum Number of OIDs for Global Set ID Parameter
**Object**: maxGlobalSetIDParameter  
**Type**: INTEGER (0..255)  
**Access**: read-only  

Maximum global set IDs for multi-parameter updates.

## 5.4.25 Global Set ID Parameter Definition Table

### 5.4.25.1 Global Set ID Number
**Object**: globalSetIDNumber  
**Type**: INTEGER (1..maxGlobalSetIDParameter)  
**Access**: not-accessible  

### 5.4.25.2 Global Set ID Object Identifier
**Object**: globalSetIDObjectIdentifier  
**Type**: OBJECT IDENTIFIER  
**Access**: read-write  

OID included in global set operation.

## 5.4.26 Unit Alarm Status 3
**Object**: unitAlarmStatus3  
**Type**: BITS  
**Access**: read-only  

Additional alarm indicators.

## 5.4.27 Unit Alarm Status 4
**Object**: unitAlarmStatus4  
**Type**: BITS  
**Access**: read-only  

Additional alarm indicators.

---

*© 2023 AASHTO / ITE / NEMA*
