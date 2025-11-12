# Phase Parameters (Section 5.2)

## 5.2.1 Maximum Phases

**Object**: maxPhases  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of phases supported by the controller. Typical values are 8, 16, or 40 phases.

## 5.2.2 Phase Table

The phase table contains configuration parameters for each phase.

### 5.2.2.1 Phase Number
**Object**: phaseNumber  
**Type**: INTEGER (1..maxPhases)  
**Access**: not-accessible  

Index into the phase table. Identifies the phase number.

### 5.2.2.2 Phase Walk Parameter
**Object**: phaseWalk  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Duration of the pedestrian WALK interval for this phase. A value of 0 indicates pedestrian service is not provided for this phase.

### 5.2.2.3 Phase Pedestrian Clear Parameter
**Object**: phasePedClear  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Duration of the pedestrian clearance interval (flashing DON'T WALK). This is the time provided for pedestrians to clear the crosswalk.

### 5.2.2.4 Phase Minimum Green Parameter
**Object**: phaseMinGreen  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Minimum duration that the phase green indication will be displayed. This ensures sufficient time for pedestrians and vehicles that received the green indication.

### 5.2.2.5 Phase Passage Parameter
**Object**: phasePassage  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Vehicle extension time added to the green when a detector actuation occurs. Also known as "vehicle interval" or "extension time."

### 5.2.2.6 Phase Maximum Green 1 Parameter
**Object**: phaseMaxGreen1  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Maximum duration of green for this phase when operating in Max 1 mode (typically used during free operation).

### 5.2.2.7 Phase Maximum Green 2 Parameter
**Object**: phaseMaxGreen2  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Maximum duration of green for this phase when operating in Max 2 mode (typically used during coordination to force phase termination).

### 5.2.2.8 Phase Yellow Change Parameter
**Object**: phaseYellowChange  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Duration of the yellow change interval. This is the time between green and red to allow vehicles in the intersection to clear.

**Calculation**: Typically based on approach speed and intersection width using kinematic equations.

### 5.2.2.9 Phase Red Clear Parameter
**Object**: phaseRedClear  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Duration of the red clearance interval (all-red). This provides additional safety time between conflicting movements.

### 5.2.2.10 Phase Red Revert
**Object**: phaseRedRevert  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time the phase dwells in red before returning to the previous color after timing the red clearance interval. Used primarily for interval-based controllers.

### 5.2.2.11 Phase Added Initial Parameter
**Object**: phaseAddedInitial  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time added to the minimum green interval for the initial portion of the phase. Provides additional time for the first vehicle(s).

### 5.2.2.12 Phase Maximum Initial Parameter
**Object**: phaseMaxInitial  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Maximum time allowed for the initial portion before vehicles are required for extension.

### 5.2.2.13 Phase Time Before Reduction Parameter
**Object**: phaseTimeBeforeReduction  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time in green before gap reduction begins. Gap reduction gradually decreases the extension time to encourage phase termination.

### 5.2.2.14 Phase Cars Before Reduction Parameter
**Object**: phaseCarsBeforeReduction  
**Type**: INTEGER (0..255)  
**Units**: vehicle actuations  
**Access**: read-write  

Number of vehicle actuations before gap reduction begins. Alternative to time-based reduction.

### 5.2.2.15 Phase Time To Reduce Parameter
**Object**: phaseTimeToReduce  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time period over which gap reduction occurs, gradually reducing from full passage time to minimum gap.

### 5.2.2.16 Phase Reduce By
**Object**: phaseReduceBy  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Amount by which the passage time is reduced during gap reduction. Final gap = passage - reduceBy.

### 5.2.2.17 Phase Minimum Gap Parameter
**Object**: phaseMinGap  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Minimum allowable gap time after gap reduction is complete. This is the shortest extension time that will be used.

### 5.2.2.18 Phase Dynamic Max Limit
**Object**: phaseDynamicMaxLimit  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Upper limit for dynamic maximum green calculations. Dynamic max adjusts based on demand.

### 5.2.2.19 Phase Dynamic Max Step
**Object**: phaseDynamicMaxStep  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Amount by which dynamic maximum green increases per cycle when gap-out is not achieved.

### 5.2.2.20 Phase Startup
**Object**: phaseStartup  
**Type**: BITS  
**Access**: read-write  

Bit field defining phase behavior during controller startup:
- **phaseInStartupGreen (0)**: Phase will be green during startup flash
- **phaseInStartupWalk (1)**: Pedestrian will be in walk during startup

### 5.2.2.21 Phase Options
**Object**: phaseOptions  
**Type**: BITS  
**Access**: read-write  

Bit field defining various phase operating options:
- **phaseRecycleOff (0)**: Disable ped recall during pedestrian clearance
- **phaseRestInWalk (1)**: Rest in WALK instead of green ball
- **phaseNoRestInRed (2)**: Don't rest in red
- **phaseRedRest (3)**: Rest in red
- **phaseOmitRedClearance (4)**: Skip red clearance interval
- **phasePedCallsPhase (5)**: Pedestrian call also places vehicle call
- **phaseVehCallsPhase (6)**: Vehicle call also places pedestrian call
- **phaseCallReleaseOnMinGreen (7)**: Release call on min green completion
- **phaseReducedTimeBeforeReduction (8)**: Use reduced timing
- **phaseGuaranteedPassage (9)**: Guarantee passage time on last actuation

### 5.2.2.22 Phase Ring Parameter
**Object**: phaseRing  
**Type**: INTEGER (0..16)  
**Access**: read-write  

Ring number to which this phase is assigned. Ring 0 typically means phase is not assigned to any ring.

### 5.2.2.23 Phase Concurrency
**Object**: phaseConcurrency  
**Type**: OCTET STRING (SIZE(1..255))  
**Access**: read-write  

Bit string indicating which other phases can run concurrently (simultaneously) with this phase. Each bit represents a phase number.

### 5.2.2.24 Phase Maximum Green 3 Parameter
**Object**: phaseMaxGreen3  
**Type**: INTEGER (0..65535)  
**Units**: tenths of seconds  
**Access**: read-write  

Maximum green time when operating in Max 3 mode. Provides extended range for longer maximum greens.

### Pedestrian-Specific Parameters

### 5.2.2.25 Phase Yellow and Red Change Time Before End of Ped Clearance
**Object**: phaseYellowRedClearanceBeforePedClearance  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time before the end of pedestrian clearance when yellow and red clearance intervals begin. Allows yellow to start during ped clear.

### 5.2.2.26 Pedestrian Phase Walk Recycle Parameter
**Object**: pedWalkRecycle  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Minimum time before the WALK indication can be displayed again after the previous WALK interval.

### 5.2.2.27 Pedestrian Phase Don't Walk Revert Parameter
**Object**: pedDontWalkRevert  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time to dwell in solid DON'T WALK before reverting to previous indication.

### 5.2.2.28 Phase Alternate Pedestrian Clearance Time Parameter
**Object**: phaseAltPedClear  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Alternate pedestrian clearance time used under special conditions (e.g., protected-permissive operation).

### 5.2.2.29 Phase Alternate Pedestrian Walk Time Parameter
**Object**: phaseAltPedWalk  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Alternate pedestrian walk time used under special conditions.

### 5.2.2.30 Phase Pedestrian Advance Walk Time Parameter
**Object**: phasePedAdvanceWalk  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time that the pedestrian WALK starts before the vehicle green (leading pedestrian interval).

### 5.2.2.31 Phase Pedestrian Delay Walk Time Parameter
**Object**: phasePedDelayWalk  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time that the pedestrian WALK is delayed after vehicle green starts (lagging pedestrian interval).

### 5.2.2.32 Phase Advanced Green Indication Start Time Parameter
**Object**: phaseAdvancedGreenStartTime  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time before the normal green that an advance green indication (flashing green arrow) begins.

### 5.2.2.33 Phase Advanced Red Indication Start Time Parameter
**Object**: phaseAdvancedRedStartTime  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Time before yellow clearance that an advance red indication begins.

### 5.2.2.34 Phase Alternate Minimum Green Time During Transitions
**Object**: phaseAltMinGreen  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Alternate minimum green time used during certain transitions.

## 5.2.3 Maximum Phase Groups

**Object**: maxPhaseGroups  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of phase status groups supported. Status groups allow efficient retrieval of multiple phase statuses at once.

## 5.2.4 Phase Status Group Table

Groups of phase status values that can be retrieved together efficiently.

### 5.2.4.1 Phase Status Group Number
**Object**: phaseStatusGroupNumber  
**Type**: INTEGER (1..maxPhaseGroups)  
**Access**: not-accessible  

Index for the phase status group.

### 5.2.4.2 Phase Status Group Reds
**Object**: phaseStatusGroupReds  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string where each bit indicates if the corresponding phase is currently displaying RED.

### 5.2.4.3 Phase Status Group Yellows
**Object**: phaseStatusGroupYellows  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases are currently displaying YELLOW.

### 5.2.4.4 Phase Status Group Greens
**Object**: phaseStatusGroupGreens  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases are currently displaying GREEN.

### 5.2.4.5 Phase Status Group Don't Walks
**Object**: phaseStatusGroupDontWalks  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases have DON'T WALK displayed.

### 5.2.4.6 Phase Status Group Pedestrian Clears
**Object**: phaseStatusGroupPedClears  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases are in pedestrian clearance (flashing DON'T WALK).

### 5.2.4.7 Phase Status Group Walks
**Object**: phaseStatusGroupWalks  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases have WALK displayed.

### 5.2.4.8 Phase Status Group Vehicle Calls
**Object**: phaseStatusGroupVehCalls  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases have active vehicle calls.

### 5.2.4.9 Phase Status Group Pedestrian Calls
**Object**: phaseStatusGroupPedCalls  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases have active pedestrian calls.

### 5.2.4.10 Phase Status Group Phase Ons
**Object**: phaseStatusGroupPhaseOns  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases are currently ON (timing green, yellow, or clearance intervals).

### 5.2.4.11 Phase Status Group Phase Nexts
**Object**: phaseStatusGroupPhaseNexts  
**Type**: OCTET STRING  
**Access**: read-only  

Bit string indicating which phases are expected to become active next.

## 5.2.5 Phase Control Table

Allows external control of phase operations.

### 5.2.5.1 Phase Control Group Number
**Object**: phaseControlGroupNumber  
**Type**: INTEGER (1..maxPhaseGroups)  
**Access**: not-accessible  

Index for the phase control group.

### 5.2.5.2 Phase Omit Control
**Object**: phaseOmitControl  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string commanding which phases should be omitted (skipped) during the current cycle.

### 5.2.5.3 Pedestrian Omit Control
**Object**: pedOmitControl  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string commanding which pedestrian services should be omitted.

### 5.2.5.4 Phase Hold Control
**Object**: phaseHoldControl  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string commanding which phases should be held (remain green if active, or immediately become green).

### 5.2.5.5 Phase Force Off Control
**Object**: phaseForceOffControl  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string commanding which phases should be forced to terminate.

### 5.2.5.6 Vehicle Call Control
**Object**: vehCallControl  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string placing vehicle calls on specified phases.

### 5.2.5.7 Pedestrian Call Control
**Object**: pedCallControl  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string placing pedestrian calls on specified phases.

---

*© 2023 AASHTO / ITE / NEMA*
