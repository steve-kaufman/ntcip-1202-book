# Coordination Parameters (Section 5.5)

## 5.5.1 Coord Operational Mode Parameter
**Object**: coordOperationalMode  
**Type**: BITS  
**Access**: read-write  

Bit field defining allowed coordination operational modes:
- **coordFree (0)**: Free mode allowed
- **coordOther (1)**: Other coordination modes
- **coordFlash (2)**: Flash coordination allowed
- **coordStandby (3)**: Standby mode allowed

## 5.5.2 Coord Correction Mode Parameters
**Object**: coordCorrectionMode  
**Type**: BITS  
**Access**: read-write  

Bit field defining allowed coordination correction modes:
- **coordDwell (0)**: Dwell correction allowed
- **coordSubtract (1)**: Subtract correction allowed
- **coordAdd (2)**: Add correction allowed

**Correction modes** determine how the controller adjusts to achieve synchronization:
- **Dwell**: Hold current phase until sync point
- **Subtract**: Shorten phase time to catch up
- **Add**: Extend phase time to wait for sync

## 5.5.3 Coord Maximum Mode Parameter
**Object**: coordMaximumMode  
**Type**: BITS  
**Access**: read-write  

Bit field defining allowed maximum timing modes:
- **coordMaxMode1 (0)**: Max mode 1 allowed
- **coordMaxMode2 (1)**: Max mode 2 allowed
- **coordMaxMode3 (2)**: Max mode 3 allowed

**Maximum modes** control how phases terminate:
- **Max 1**: Typically used in free operation
- **Max 2**: Force-off for coordination
- **Max 3**: Extended maximum for special conditions

## 5.5.4 Coord Force Mode Parameter
**Object**: coordForceMode  
**Type**: BITS  
**Access**: read-write  

Bit field defining allowed force modes:
- **coordFloating (0)**: Floating force-off allowed
- **coordFixed (1)**: Fixed force-off allowed

**Force modes** determine when phases are forced to terminate:
- **Floating**: Force-off based on calls and detector activity
- **Fixed**: Force-off at fixed point in cycle

## 5.5.5 Maximum Patterns Parameter
**Object**: maxPatterns  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of coordination patterns supported. Common values: 250-253.

## 5.5.6 Pattern Table Type
**Object**: patternTableType  
**Type**: INTEGER  
**Access**: read-only  

Type of pattern table implementation:
- **other (1)**
- **patternTableBasic (2)**: Basic pattern table
- **patternTableEnhanced (3)**: Enhanced with additional features

## 5.5.7 Pattern Table

Each pattern defines a complete coordination plan.

### 5.5.7.1 Pattern Number Entry
**Object**: patternNumber  
**Type**: INTEGER (1..maxPatterns)  
**Access**: not-accessible  

Index into the pattern table.

### 5.5.7.2 Pattern Cycle Time
**Object**: patternCycleTime  
**Type**: INTEGER (0..65535)  
**Units**: tenths of seconds  
**Access**: read-write  

Duration of one complete signal cycle for this pattern. Common range: 40-180 seconds (400-1800 tenths).

**Special values**:
- **0**: Pattern not defined or free operation

### 5.5.7.3 Pattern Offset Time Parameter
**Object**: patternOffsetTime  
**Type**: INTEGER (0..65535)  
**Units**: tenths of seconds  
**Access**: read-write  

Offset time from system reference point to local sync point. Determines when coordinated phase begins green.

**Calculation**: Offset determines the phase relationship between intersections along a corridor.

### 5.5.7.4 Pattern Split Number Parameter
**Object**: patternSplitNumber  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Split table entry to use with this pattern (see Section 5.5.9).

**Special values**:
- **0**: No split assignment (use default or omit)

### 5.5.7.5 Pattern Sequence Number Parameter
**Object**: patternSequenceNumber  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Sequence table entry to use with this pattern (see Section 5.8.3).

**Special values**:
- **0**: Use default sequence

### 5.5.7.6 Pattern Coordination Sync Point
**Object**: patternCoordinationSyncPoint  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Phase number whose sync point is used as the pattern's coordination reference point. Typically the main street through phase.

### 5.5.7.7 Pattern Options
**Object**: patternOptions  
**Type**: BITS  
**Access**: read-write  

Bit field defining pattern operating options:
- **patternYieldMode (0)**: Yield mode enabled
- **patternCoordinationLagPhase (1)**: Use lag phase for coordination
- **patternSimultaneousGapout (2)**: Simultaneous gap-out enabled
- **patternOther (3-7)**: Reserved for future use

### 5.5.7.8 Pattern Enabled Lanes
**Object**: patternEnabledLanes  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string specifying which MAP lanes are enabled for this pattern. Used for connected vehicle SPaT broadcasting.

## 5.5.8 Maximum Splits
**Object**: maxSplits  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of split tables supported. Common value: 255.

## 5.5.9 Split Table

Splits define how the cycle time is divided among phases.

### 5.5.9.1 Split Number
**Object**: splitNumber  
**Type**: INTEGER (1..maxSplits)  
**Access**: not-accessible  

Index into the split table.

### 5.5.9.2 Split Phase Number
**Object**: splitPhaseNumber  
**Type**: INTEGER (1..40)  
**Access**: not-accessible  

Phase position within this split (typically 1-8 or 1-16).

### 5.5.9.3 Split Time Parameter
**Object**: splitTime  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Allocated time for this phase in the split. The sum of all split times should equal the cycle length.

**Special values**:
- **0**: Phase not included in this split

### 5.5.9.4 Split Mode Parameter
**Object**: splitMode  
**Type**: INTEGER  
**Access**: read-write  

Mode controlling how split is used:
- **other (1)**
- **splitModeMinimumVehicleRecall (2)**: Min recall, rest = split time
- **splitModeMaximumVehicleRecall (3)**: Max recall, split = force-off point
- **splitModeFixedSplit (4)**: Fixed split, non-actuated
- **splitModeSoftRecall (5)**: Soft recall
- **splitModeMaximumLimitingRecall (6)**: Max with limiting

### 5.5.9.5 Split Coordinated Phase
**Object**: splitCoordinatedPhase  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Phase number designated as the coordinated phase for this split.

### 5.5.9.6 Split Options
**Object**: splitOptions  
**Type**: BITS  
**Access**: read-write  

Additional split options:
- **splitInhibitMaxTermination (0)**: Inhibit max termination
- **splitPermitSlideableSplit (1)**: Allow split to slide
- **splitOther (2-7)**: Reserved

## 5.5.10 Coordination Pattern Status
**Object**: coordinationPatternStatus  
**Type**: INTEGER (0..maxPatterns)  
**Access**: read-only  

Currently active coordination pattern number.

**Special values**:
- **0**: No pattern active (free operation)
- **254**: Flash
- **255**: Unknown

## 5.5.11 Local Free Status
**Object**: localFreeStatus  
**Type**: INTEGER  
**Access**: read-only  

Indicates if controller is in local free mode:
- **notFree (1)**: Coordinated
- **commandFree (2)**: Commanded to free
- **transitionFree (3)**: Transitioning to free
- **inputFree (4)**: Free due to input
- **coordinationFree (5)**: Coordination free
- **badPlan (6)**: Invalid plan
- **badCycleTime (7)**: Invalid cycle time
- **splitOverrun (8)**: Split exceeds cycle
- **invalidOffset (9)**: Invalid offset
- **other (10)**: Other reason

## 5.5.12 Coordination Cycle Status
**Object**: coordinationCycleStatus  
**Type**: INTEGER (0..65535)  
**Units**: tenths of seconds  
**Access**: read-only  

Current position in the coordination cycle (time since last sync point).

## 5.5.13 Coordination Sync Status
**Object**: coordinationSyncStatus  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-only  

Time until next coordination sync point.

## 5.5.14 System Pattern Control
**Object**: systemPatternControl  
**Type**: INTEGER (0..maxPatterns)  
**Access**: read-write  

Command a specific pattern to run.

**Special values**:
- **0**: No command (controller selects pattern)
- **254**: Command flash
- **255**: Other

## 5.5.15 System Sync Control
**Object**: systemSyncControl  
**Type**: INTEGER (0..65535)  
**Units**: tenths of seconds  
**Access**: read-write  

Command the system sync point (time reference). Writing to this establishes coordination timing across multiple controllers.

## 5.5.16 Unit Coordination Sync Point
**Object**: unitCoordinationSyncPoint  
**Type**: INTEGER  
**Access**: read-write  

Point within the coordinated phase used for synchronization:
- **other (1)**
- **beginningGreen (2)**: Start of green
- **endGreen (3)**: End of green
- **forceOff (4)**: Force-off point
- **yield (5)**: Yield point

---

# Time Base Parameters (Section 5.6)

## 5.6.1 Time Base Pattern Sync Parameter
**Object**: timeBasePatternSync  
**Type**: INTEGER  
**Access**: read-write  

Determines if time-based pattern changes are synchronized:
- **other (1)**
- **free (2)**: Change immediately
- **coordinatedBeginOfCycle (3)**: Change at cycle boundary
- **coordinatedZero (4)**: Change at zero offset point

## 5.6.2 Maximum Time Base Actions
**Object**: maxTimeBaseActions  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of time base action entries. Common value: 255.

## 5.6.3 Time Base ASC Action Table

Defines actions to be taken at scheduled times.

### 5.6.3.1 Time Base Action Number
**Object**: timeBaseActionNumber  
**Type**: INTEGER (1..maxTimeBaseActions)  
**Access**: not-accessible  

Index into the time base action table.

### 5.6.3.2 Time Base Action Pattern Parameter
**Object**: timeBaseActionPattern  
**Type**: INTEGER (0..maxPatterns)  
**Access**: read-write  

Pattern to activate when this action is triggered.

**Special values**:
- **0**: No pattern change
- **254**: Flash
- **255**: Free

### 5.6.3.3 Time Base Action Auxiliary Function Parameter
**Object**: timeBaseActionAuxFunction  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of auxiliary functions to activate with this action (log settings, detector options, etc.).

### 5.6.3.4 Time Base Action Special Function Parameter
**Object**: timeBaseActionSpecialFunction  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of special function outputs to activate with this action.

### 5.6.3.5 Time Base Action Enabled Lane
**Object**: timeBaseActionEnabledLane  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of MAP lanes to enable when this action is triggered.

## 5.6.4 Time Base ASC Action Status
**Object**: timeBaseAscActionStatus  
**Type**: INTEGER (0..maxTimeBaseActions)  
**Access**: read-only  

Currently active time base action number.

**Special values**:
- **0**: No time base action active

## 5.6.5 Action Plan Command
**Object**: actionPlanCommand  
**Type**: INTEGER (0..maxTimeBaseActions)  
**Access**: read-write  

Command a time base action to execute immediately (manual override).

**Special values**:
- **0**: No command

---

*© 2023 AASHTO / ITE / NEMA*
