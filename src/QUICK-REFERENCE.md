# NTCIP 1202 Quick Reference Guide

## Common Object Lookups

### Phase Control
- **maxPhases** - Maximum number of phases supported
- **phaseMinGreen** - Minimum green time for vehicle phase
- **phasePassage** - Passage time (gap time)
- **phaseMaxGreen1/2/3** - Maximum green times
- **phaseYellow** - Yellow change interval
- **phaseRedClear** - Red clearance time
- **phaseWalk** - Pedestrian walk time
- **phasePedClear** - Pedestrian clearance time

### Phase Status  
- **phaseStatusGroupReds** - Current red phases (bitmap)
- **phaseStatusGroupYellows** - Current yellow phases (bitmap)
- **phaseStatusGroupGreens** - Current green phases (bitmap)
- **phaseStatusGroupPhaseOns** - Currently active phases (bitmap)
- **phaseStatusGroupPhaseNexts** - Next phases to be served (bitmap)

### Detector Configuration
- **maxVehicleDetectors** - Maximum vehicle detectors
- **vehicleDetectorCallPhase** - Phase to call on activation
- **vehicleDetectorOptions** - Detector operating modes (bitmap)
- **vehicleDetectorDelay** - Detection delay time
- **vehicleDetectorExtend** - Extension/passage time

### Detector Status
- **detectorStatusGroupActive** - Currently active detectors (bitmap)
- **volumeOccupancy** - Volume and occupancy data reports
- **maxPedestrianDetectors** - Maximum pedestrian detectors

### Unit Control
- **unitControlStatus** - Overall controller status (bitmap)
- **unitFlashStatus** - Flash mode status
- **unitAlarmStatus1/2** - Alarm conditions
- **shortAlarmStatus** - Critical alarm summary

### Coordination
- **coordinationPatternStatus** - Current pattern number
- **coordinationCycleStatus** - Position in cycle
- **patternCycleTime** - Cycle length
- **patternOffsetTime** - Offset from reference point
- **patternSplitNumber** - Split table assignment

### Preemption
- **maxPreempts** - Maximum preempts supported
- **preemptEnable** - Enable/disable preempt
- **preemptDelay** - Delay before activation
- **preemptMinDwell** - Minimum dwell time
- **preemptState** - Current preempt state

### Connected Vehicles (SPaT)
- **spatIntersectionID** - Intersection identifier
- **spatMovementEventList** - Current and predicted movement states
- **spatTimeChangeDetails** - Timing predictions for movements
- **enableSpatData** - Enable SPaT message generation

### Time Management
- **timebaseAscPatternSync** - Pattern synchronization time
- **timebaseAscActionTable** - Scheduled pattern/action table

## Common Operations

### Download Timing Pattern
1. Set consistency check parameters
2. Upload phase timings via phaseTable
3. Upload split timings via splitTable  
4. Upload pattern definitions via patternTable
5. Trigger consistency check
6. Verify no errors in consistency check results

### Activate Pattern
```
coordinationPatternControl = <pattern_number>
```

### Read Current Status
- Check **unitControlStatus** for operating mode
- Check **unitFlashStatus** for flash conditions
- Check **unitAlarmStatus1** and **unitAlarmStatus2** for alarms
- Read **phaseStatusGroup** tables for current indications

### Configure Detector
1. Set **vehicleDetectorCallPhase** to assign to phase
2. Configure **vehicleDetectorOptions** for operating modes
3. Set timing parameters (delay, extend, etc.)
4. Enable via bitmap if required

### Monitor Detector Health
- **vehicleDetectorAlarms** - Fault conditions (bitmap)
- **detectorStatusGroupActive** - Current activations
- **volumeOccupancySequence** - Data collection sequence number

## Key Bitmaps

### Phase Options (phaseOptions)
- Bit 0: pedRecall
- Bit 1: pedCallNonActuated2  
- Bit 2: pedCallNonActuated1
- Bit 3: minRecall
- Bit 4: maxRecall
- Bit 5: softRecall
- And more... (see phases.md for complete list)

### Unit Control Status
- Bit 0: otherCmuMmuFault
- Bit 1: other
- Bit 2: manual
- Bit 3: timebaseCoordinationInEffect
- Bit 4: transitioningToFree
- Bit 5: coordinationMode

### Detector Options
- Bit 0: detectorYellowLockCall
- Bit 1: detectorRedLockCall
- Bit 2: detectorPassage
- Bit 3: detectorAddedInitial
- Bit 4: detectorQueue
- Bit 5: detectorCall

## File Organization Map

| Topic | File Location |
|-------|---------------|
| Phase parameters | 05-mib/phases.md |
| Detector config | 05-mib/detectors.md |
| Unit status/control | 05-mib/units.md |
| Coordination/patterns | 05-mib/coordination.md |
| Preemption | 05-mib/preempts.md |
| Connected vehicles | 07-sae-ntcip-objects.md |
| Communication dialogs | 04-dialogs.md |
| User needs | 02-concept-of-operations.md |
| Requirements | 03-functional-requirements.md |

## SNMP Access Levels

- **read-only** - Can only be read, not modified
- **read-write** - Can be read and modified  
- **read-create** - Can be read, modified, and rows can be created/deleted
- **accessible-for-notify** - Only used in SNMP notifications/traps

## Common Units

- **Seconds** - Time values (1-255 seconds typical range)
- **Tenths of seconds** - Fine-grained timing (0-2550 = 0.0-255.0 seconds)
- **Integer** - Counts, indices, identifiers
- **Bitmap** - Bit flags (each bit represents on/off for numbered item)

## Value Conventions

- **0 or 255** - Often means "not used" or "disabled"
- **1-based indexing** - Most tables start at index 1, not 0
- **Bitmaps** - Bit 0 = LSB, represents item 1; Bit 1 = item 2, etc.
