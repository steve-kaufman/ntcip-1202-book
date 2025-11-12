# Detector Parameters (Section 5.3)

## 5.3.1 Maximum Vehicle Detectors

**Object**: maxVehicleDetectors  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of vehicle detectors supported by the controller.

## 5.3.2 Vehicle Detector Parameter Table

Configuration parameters for vehicle detectors.

### 5.3.2.1 Vehicle Detector Number
**Object**: vehicleDetectorNumber  
**Type**: INTEGER (1..maxVehicleDetectors)  
**Access**: not-accessible  

Index into the vehicle detector table.

### 5.3.2.2 Vehicle Detector Options Parameter
**Object**: vehicleDetectorOptions  
**Type**: BITS  
**Access**: read-write  

Bit field defining detector operating options:
- **detectorLocking (0)**: Detector locks on until phase gap-out
- **detectorNonLocking (1)**: Detector does not lock
- **detectorDelayedCall (2)**: Call is delayed by detector delay parameter
- **detectorExtendedCall (3)**: Call is extended by detector extend parameter
- **detectorStopTimeCall (4)**: Calls phase when ring is in stop time

### 5.3.2.3 Vehicle Detector Call Phase Parameter
**Object**: vehicleDetectorCallPhase  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Phase number that receives the call from this detector. A value of 0 means no call is placed.

### 5.3.2.4 Vehicle Detector Switch Phase Parameter
**Object**: vehicleDetectorSwitchPhase  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Phase number that detector switches to when switch phase option is enabled.

### 5.3.2.5 Vehicle Detector Delay Parameter
**Object**: vehicleDetectorDelay  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time delay before detector actuation results in a call. Used to filter brief actuations.

### 5.3.2.6 Vehicle Detector Extend Parameter
**Object**: vehicleDetectorExtend  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time that detector call is extended after detector actuation ends. Provides memory.

### 5.3.2.7 Vehicle Detector Queue Limit
**Object**: vehicleDetectorQueueLimit  
**Type**: INTEGER (0..255)  
**Units**: vehicle actuations  
**Access**: read-write  

Maximum number of vehicle actuations to be queued. When exceeded, additional actuations are ignored.

### 5.3.2.8 Vehicle Detector No Activity Parameter
**Object**: vehicleDetectorNoActivity  
**Type**: INTEGER (0..255)  
**Units**: minutes  
**Access**: read-write  

Time without detector activity before "no activity" alarm is generated. Detects failed detectors.

### 5.3.2.9 Vehicle Detector Maximum Presence Parameter
**Object**: vehicleDetectorMaxPresence  
**Type**: INTEGER (0..255)  
**Units**: minutes  
**Access**: read-write  

Maximum time detector can be continuously active before "max presence" alarm is generated. Detects stuck-on detectors.

### 5.3.2.10 Vehicle Detector Erratic Counts Parameter
**Object**: vehicleDetectorErraticCounts  
**Type**: INTEGER (0..255)  
**Units**: actuations per minute  
**Access**: read-write  

Maximum number of detector actuations per minute before "erratic output" alarm is generated.

### 5.3.2.11 Vehicle Detector Fail Time Parameter
**Object**: vehicleDetectorFailTime  
**Type**: INTEGER (0..255)  
**Units**: seconds  
**Access**: read-write  

Time a detector alarm must persist before being reported as failed.

### 5.3.2.12 Vehicle Detector Alarms
**Object**: vehicleDetectorAlarms  
**Type**: BITS  
**Access**: read-only  

Current alarm status for this detector:
- **detectorOpenLoopFault (0)**: Open loop detected
- **detectorShortedLoopFault (1)**: Shorted loop detected
- **detectorExcessiveChangeFault (2)**: Excessive frequency change
- **detectorWatchdogFault (3)**: Detector watchdog fault
- **detectorOtherFault (4)**: Other detector fault
- **detectorNoActivity (5)**: No activity alarm
- **detectorMaxPresence (6)**: Maximum presence alarm
- **detectorErraticOutput (7)**: Erratic output alarm

### 5.3.2.13 Vehicle Detector Reported Alarms
**Object**: vehicleDetectorReportedAlarms  
**Type**: BITS  
**Access**: read-only  

Alarms that have been active long enough to be reported (persisted beyond fail time).

### 5.3.2.14 Vehicle Detector Reset
**Object**: vehicleDetectorReset  
**Type**: INTEGER  
**Access**: read-write  

Writing to this object resets the detector and clears alarms:
- **noReset (1)**: No action
- **resetDetector (2)**: Reset this detector

### 5.3.2.15 Vehicle Detector Options 2
**Object**: vehicleDetectorOptions2  
**Type**: BITS  
**Access**: read-write  

Additional detector options:
- **detectorRecallOn (0)**: Detector provides recall (continuous call)
- **detectorRedLockingOn (1)**: Detector locks during red
- **detectorYellowLockingOn (2)**: Detector locks during yellow

### 5.3.2.16 Vehicle Detector Paired Detector
**Object**: vehicleDetectorPairedDetector  
**Type**: INTEGER (0..maxVehicleDetectors)  
**Access**: read-write  

Detector number of the paired detector for speed calculation. 0 means no pairing.

### 5.3.2.17 Vehicle Detector Paired Detector Spacing
**Object**: vehicleDetectorPairedDetectorSpacing  
**Type**: INTEGER (0..65535)  
**Units**: feet  
**Access**: read-write  

Distance between this detector and its paired detector for speed calculation.

### 5.3.2.18 Vehicle Detector Average Vehicle Length
**Object**: vehicleDetectorAverageVehicleLength  
**Type**: INTEGER (0..255)  
**Units**: feet  
**Access**: read-write  

Average vehicle length used for occupancy calculations and vehicle count estimation.

### 5.3.2.19 Vehicle Detector Length Parameter
**Object**: vehicleDetectorLength  
**Type**: INTEGER (0..1000)  
**Units**: feet  
**Access**: read-write  

Physical length of the detector zone.

### 5.3.2.20 Vehicle Detector Travel Mode
**Object**: vehicleDetectorTravelMode  
**Type**: INTEGER  
**Access**: read-write  

Type of traffic using this detector:
- **other (1)**: Other or unknown
- **vehicle (2)**: Motor vehicles
- **bicycle (3)**: Bicycles
- **pedestrian (4)**: Pedestrians
- **transit (5)**: Transit vehicles
- **emergencyVehicle (6)**: Emergency vehicles

## 5.3.3 Maximum Vehicle Detector Status Groups

**Object**: maxVehicleDetectorStatusGroups  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of vehicle detector status groups.

## 5.3.4 Vehicle Detector Status Group Table

Provides efficient access to multiple detector statuses.

### 5.3.4.1 Detector Status Group Number
**Object**: detectorStatusGroupNumber  
**Type**: INTEGER (1..maxVehicleDetectorStatusGroups)  
**Access**: not-accessible  

Index for detector status group.

### 5.3.4.2 Detector Status Group Active
**Object**: detectorStatusGroupActive  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which detectors are currently active (vehicle present).

### 5.3.4.3 Detector Alarm Status
**Object**: detectorAlarmStatus  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which detectors have active alarms.

## 5.3.5 Volume / Occupancy Report

Provides traffic data collection and reporting.

### 5.3.5.1 Volume / Occupancy Sequence
**Object**: volumeOccupancySequence  
**Type**: INTEGER  
**Access**: read-only  

Sequence number incremented each time volume/occupancy data is updated. Used to detect new data.

### 5.3.5.2 Volume / Occupancy Period
**Object**: volumeOccupancyPeriod  
**Type**: INTEGER (0..65535)  
**Units**: seconds  
**Access**: read-write  

Time period over which volume and occupancy are accumulated. 0 disables reporting.

### 5.3.5.3 Active Volume / Occupancy Detectors
**Object**: activeVolumeOccupancyDetectors  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which detectors are included in volume/occupancy reporting.

### 5.3.5.4 Volume / Occupancy Table

#### 5.3.5.4.1 Volume Data
**Object**: volumeData  
**Type**: INTEGER (0..65535)  
**Units**: vehicle actuations  
**Access**: read-only  

Number of vehicle actuations during the sampling period.

#### 5.3.5.4.2 Occupancy Data
**Object**: occupancyData  
**Type**: INTEGER (0..2000)  
**Units**: tenths of percent (0-200.0%)  
**Access**: read-only  

Percentage of time detector was occupied during sampling period.

#### 5.3.5.4.3 Speed Data
**Object**: speedData  
**Type**: INTEGER (0..255)  
**Units**: miles per hour  
**Access**: read-only  

Average speed calculated from paired detectors. 0 means not available or no vehicles detected.

### 5.3.5.5 Volume / Occupancy Period—Version 3
**Object**: volumeOccupancyPeriodV3  
**Type**: INTEGER (0..4294967295)  
**Units**: milliseconds  
**Access**: read-write  

Enhanced period with millisecond resolution for high-resolution data logging.

### 5.3.5.6 Volume / Occupancy Sample Time
**Object**: volumeOccupancySampleTime  
**Type**: INTEGER  
**Units**: seconds since epoch  
**Access**: read-only  

Timestamp when the current sample period started.

### 5.3.5.7 Volume / Occupancy Sample Duration
**Object**: volumeOccupancySampleDuration  
**Type**: INTEGER  
**Units**: milliseconds  
**Access**: read-only  

Actual duration of the completed sample period.

## 5.3.6 Maximum Pedestrian Detectors

**Object**: maxPedestrianDetectors  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of pedestrian detectors supported.

## 5.3.7 Pedestrian Detector Parameter Table

Configuration for pedestrian detectors (push buttons, video detection, etc.).

### 5.3.7.1 Pedestrian Detector Number
**Object**: pedestrianDetectorNumber  
**Type**: INTEGER (1..maxPedestrianDetectors)  
**Access**: not-accessible  

Index into pedestrian detector table.

### 5.3.7.2 Pedestrian Detector Call Phase Parameter
**Object**: pedestrianDetectorCallPhase  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Phase that receives pedestrian call from this detector.

### 5.3.7.3 Pedestrian Detector No Activity Parameter
**Object**: pedestrianDetectorNoActivity  
**Type**: INTEGER (0..255)  
**Units**: hours  
**Access**: read-write  

Time without activity before no-activity alarm. Used to detect failed push buttons.

### 5.3.7.4 Pedestrian Detector Maximum Presence Parameter
**Object**: pedestrianDetectorMaxPresence  
**Type**: INTEGER (0..255)  
**Units**: seconds  
**Access**: read-write  

Maximum continuous activation time before max presence alarm.

### 5.3.7.5 Pedestrian Detector Erratic Counts Parameter
**Object**: pedestrianDetectorErraticCounts  
**Type**: INTEGER (0..255)  
**Units**: actuations per hour  
**Access**: read-write  

Maximum actuations per hour before erratic alarm.

### 5.3.7.6 Pedestrian Detector Alarms
**Object**: pedestrianDetectorAlarms  
**Type**: BITS  
**Access**: read-only  

Current alarm status:
- **pedDetectorNoActivity (0)**: No activity alarm
- **pedDetectorMaxPresence (1)**: Max presence alarm
- **pedDetectorErraticOutput (2)**: Erratic output alarm
- **pedDetectorOtherFault (3)**: Other fault

### 5.3.7.7 Pedestrian Detector Reset
**Object**: pedestrianDetectorReset  
**Type**: INTEGER  
**Access**: read-write  

Reset detector and clear alarms:
- **noReset (1)**
- **resetDetector (2)**

### 5.3.7.8 Pedestrian Pushbutton Duration Parameter
**Object**: pedPushbuttonDuration  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Minimum time pushbutton must be pressed to register. Filters noise.

### 5.3.7.9 Pedestrian Detector Options
**Object**: pedestrianDetectorOptions  
**Type**: BITS  
**Access**: read-write  

Operating options:
- **pedDetectorRecallOn (0)**: Continuous recall
- **pedDetectorExtendedCall (1)**: Extended call mode

## 5.3.8 Maximum Pedestrian Detector Groups

**Object**: maxPedestrianDetectorGroups  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of pedestrian detector status groups.

## 5.3.9 Pedestrian Detector Status Group Table

### 5.3.9.1 Pedestrian Detector Status Group Number
**Object**: pedestrianDetectorStatusGroupNumber  
**Type**: INTEGER (1..maxPedestrianDetectorGroups)  
**Access**: not-accessible  

### 5.3.9.2 Pedestrian Detector Status Group Active
**Object**: pedestrianDetectorStatusGroupActive  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string of active pedestrian detectors.

### 5.3.9.3 Pedestrian Detector Alarm Status
**Object**: pedestrianDetectorAlarmStatus  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string of pedestrian detectors with alarms.

## 5.3.10 Pedestrian Detector Report

Provides pedestrian activity statistics.

### 5.3.10.1 Pedestrian Sample Sequence
**Object**: pedestrianSampleSequence  
**Type**: INTEGER  
**Access**: read-only  

Sequence number for pedestrian sample data.

### 5.3.10.2 Pedestrian Sample Period
**Object**: pedestrianSamplePeriod  
**Type**: INTEGER (0..65535)  
**Units**: seconds  
**Access**: read-write  

Sampling period for pedestrian data.

### 5.3.10.3 Active Pedestrian Sample Detectors
**Object**: activePedestrianSampleDetectors  
**Type**: OCTET STRING  
**Access**: read-only  

Detectors included in sampling.

### 5.3.10.4 Pedestrian Sample Table

#### 5.3.10.4.1 Pedestrian Sample Volume
**Object**: pedestrianSampleVolume  
**Type**: INTEGER (0..65535)  
**Access**: read-only  

Number of pedestrian actuations during sample period.

#### 5.3.10.4.2 Pedestrian Sample Actuations
**Object**: pedestrianSampleActuations  
**Type**: INTEGER (0..65535)  
**Access**: read-only  

Number of individual button presses.

#### 5.3.10.4.3 Pedestrian Sample Services
**Object**: pedestrianSampleServices  
**Type**: INTEGER (0..65535)  
**Access**: read-only  

Number of times pedestrian service was provided.

### 5.3.10.5 Pedestrian Volume / Actuation Sample Time
**Object**: pedestrianVolActSampleTime  
**Type**: INTEGER  
**Units**: seconds since epoch  
**Access**: read-only  

Timestamp of sample.

### 5.3.10.6 Pedestrian Volume / Actuation Sample Duration
**Object**: pedestrianVolActSampleDuration  
**Type**: INTEGER  
**Units**: milliseconds  
**Access**: read-only  

Actual sample duration.

## 5.3.11 Maximum Vehicle Detector Control Groups

**Object**: maxVehicleDetectorControlGroups  
**Type**: INTEGER (1..255)  
**Access**: read-only  

### 5.3.11.1 Vehicle Detector Control Group Table

### 5.3.11.2 Vehicle Detector Control Group Number
**Object**: vehicleDetectorControlGroupNumber  
**Type**: INTEGER (1..maxVehicleDetectorControlGroups)  
**Access**: not-accessible  

### 5.3.11.3 Vehicle Detector Control Group Actuation
**Object**: vehicleDetectorControlGroupActuation  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string for remotely forcing detector actuations (for testing).

## 5.3.12 Pedestrian Detector Control Group Table

### 5.3.12.1 Pedestrian Detector Control Group Number
**Object**: pedestrianDetectorControlGroupNumber  
**Type**: INTEGER (1..maxPedestrianDetectorGroups)  
**Access**: not-accessible  

### 5.3.12.2 Pedestrian Detector Control Group Actuation
**Object**: pedestrianDetectorControlGroupActuation  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string for remotely forcing pedestrian detector actuations.

---

*© 2023 AASHTO / ITE / NEMA*
