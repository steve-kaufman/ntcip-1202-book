# Preempt Parameters (Section 5.7)

## Overview
Preemption allows special vehicles (emergency vehicles, trains) to interrupt normal signal operations for safety and priority service.

## 5.7.1 Maximum Preempts
**Object**: maxPreempts  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of preempt inputs supported. Common values: 6-10.

## 5.7.2 Preempt Table

Configuration for each preempt input.

### 5.7.2.1 Preempt Number
**Object**: preemptNumber  
**Type**: INTEGER (1..maxPreempts)  
**Access**: not-accessible  

Index into the preempt table.

### 5.7.2.2 Preempt Control Parameter
**Object**: preemptControl  
**Type**: INTEGER  
**Access**: read-write  

Operating mode for this preempt:
- **other (1)**
- **notEnabled (2)**: Preempt disabled
- **preemptHighPriority (3)**: High priority preemption
- **preemptLowPriority (4)**: Low priority (signal priority)

### 5.7.2.3 Preempt Link Parameter
**Object**: preemptLink  
**Type**: INTEGER (0..maxPreempts)  
**Access**: read-write  

Preempt number to link with (for coordinated preemption). **0** = no link.

**Use case**: Railroad preemption may link entrance and exit gates.

### 5.7.2.4 Preempt Delay Parameter
**Object**: preemptDelay  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Delay time before preempt service begins after input activation. Provides filtering and coordination time.

### 5.7.2.5 Preempt Duration Parameter
**Object**: preemptDuration  
**Type**: INTEGER (0..65535)  
**Units**: tenths of seconds  
**Access**: read-write  

Maximum time allowed for preempt service. Controller returns to normal operation after this duration, even if input still active.

**Special values**:
- **0**: No duration limit

### 5.7.2.6 Preempt Minimum Green Parameter
**Object**: preemptMinGreen  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Minimum green time for phases during track clearance (before entering dwell). Ensures safe clearance of intersection.

### 5.7.2.7 Preempt Minimum Walk Parameter
**Object**: preemptMinWalk  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Minimum walk time during preempt entry. Ensures pedestrians get adequate walk indication.

### 5.7.2.8 Preempt Enter Pedestrian Clear Parameter
**Object**: preemptEnterPedClear  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Pedestrian clearance time during preempt entry phase.

### 5.7.2.9 Preempt Track Green Parameter
**Object**: preemptTrackGreen  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Minimum green time for track clearance phases. Ensures vehicles clear tracks before train arrives.

### 5.7.2.10 Preempt Minimum Dwell Parameter
**Object**: preemptMinDwell  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Minimum time in dwell (service) phase. This is when emergency vehicle or train has right-of-way.

### 5.7.2.11 Preempt Maximum Presence Parameter
**Object**: preemptMaxPresence  
**Type**: INTEGER (0..65535)  
**Units**: tenths of seconds  
**Access**: read-write  

Maximum time preempt input can be active before alarm is generated.

### 5.7.2.12 Preempt Track Phase Parameter
**Object**: preemptTrackPhase  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of phases to serve during track clearance interval (clearing intersection before preempt vehicle arrives).

### 5.7.2.13 Preempt Dwell Phase Parameter
**Object**: preemptDwellPhase  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of phases to serve during dwell interval (when preempt vehicle is serviced).

### 5.7.2.14 Preempt Dwell Ped Parameter
**Object**: preemptDwellPed  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of pedestrian phases to serve during dwell.

### 5.7.2.15 Preempt Exit Phase Parameter
**Object**: preemptExitPhase  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of phases to serve during preempt exit (transition back to normal operation).

### 5.7.2.16 Preempt State
**Object**: preemptState  
**Type**: INTEGER  
**Access**: read-only  

Current state of preempt sequence:
- **notActive (1)**: Preempt not active
- **active (2)**: Preempt sequence active
- **entryStarted (3)**: Entry phase started
- **trackClearance (4)**: Clearing tracks
- **dwellService (5)**: In dwell
- **linkActive (6)**: Linked preempt active
- **maxPresenceExceeded (7)**: Max presence alarm
- **dwellServiceExit (8)**: Exiting dwell
- **exitStarted (9)**: Exit phase started

### 5.7.2.17 Preempt Track Overlap Parameter
**Object**: preemptTrackOverlap  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of overlaps to serve during track clearance.

### 5.7.2.18 Preempt Dwell Overlap Parameter
**Object**: preemptDwellOverlap  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of overlaps to serve during dwell.

### 5.7.2.19 Preempt Cycling Phase Parameter
**Object**: preemptCyclingPhase  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of phases allowed to cycle during extended dwell period.

### 5.7.2.20 Preempt Cycling Ped Parameter
**Object**: preemptCyclingPed  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of pedestrian phases allowed to cycle during dwell.

### 5.7.2.21 Preempt Cycling Overlap Parameter
**Object**: preemptCyclingOverlap  
**Type**: OCTET STRING  
**Access**: read-write  

Bit string of overlaps allowed to cycle during dwell.

### 5.7.2.22 Preempt Enter Yellow Change Parameter
**Object**: preemptEnterYellowChange  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Yellow change interval during preempt entry.

### 5.7.2.23 Preempt Enter Red Clear Parameter
**Object**: preemptEnterRedClear  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Red clearance interval during preempt entry.

### 5.7.2.24 Preempt Track Yellow Change Parameter
**Object**: preemptTrackYellowChange  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Yellow change interval during track clearance.

### 5.7.2.25 Preempt Track Red Clear Parameter
**Object**: preemptTrackRedClear  
**Type**: INTEGER (0..255)  
**Units**: tenths of seconds  
**Access**: read-write  

Red clearance interval during track clearance.

### 5.7.2.26 Preempt Sequence Number
**Object**: preemptSequenceNumber  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Priority level for this preempt. Higher number = higher priority. Used when multiple preempts are active simultaneously.

### 5.7.2.27 Preempt Exit Type
**Object**: preemptExitType  
**Type**: INTEGER  
**Access**: read-write  

Method for exiting preempt:
- **other (1)**
- **dwellPhaseOff (2)**: Turn off dwell phase
- **callToNonDwellPhase (3)**: Call non-dwell phases
- **maximumRecall (4)**: Maximum recall

## 5.7.3 Preempt Control Table

Allows manual activation of preempts.

### 5.7.3.1 Preempt Control Number
**Object**: preemptControlNumber  
**Type**: INTEGER (1..maxPreempts)  
**Access**: not-accessible  

### 5.7.3.2 Preempt Control State
**Object**: preemptControlState  
**Type**: INTEGER  
**Access**: read-write  

Command preempt activation:
- **other (1)**
- **notActive (2)**: Deactivate
- **activeVehicle (3)**: Activate as vehicle preempt
- **activeFixedClearanceTime (4)**: Activate with fixed clearance
- **activeAdaptiveClearanceTime (5)**: Activate with adaptive clearance

## 5.7.4 Preempt Status
**Object**: preemptStatus  
**Type**: OCTET STRING  
**Access**: read-only  

Overall preempt system status (bit string of active preempts).

## 5.7.5 Maximum Preempt Groups
**Object**: maxPreemptGroups  
**Type**: INTEGER (1..255)  
**Access**: read-only  

Maximum number of preempt status groups.

## 5.7.6 Preempt Status Table

### 5.7.6.1 Preempt Status Group Number
**Object**: preemptStatusGroupNumber  
**Type**: INTEGER (1..maxPreemptGroups)  
**Access**: not-accessible  

### 5.7.6.2 Preempt Status Group
**Object**: preemptStatusGroup  
**Type**: OCTET STRING  
**Access**: read-only  

Detailed status of each preempt in the group:

**Bit meanings** (repeating pattern for each preempt):
- **Bit 0**: Preempt input active
- **Bit 1**: Preempt delay timing
- **Bit 2**: Track clearance active
- **Bit 3**: Dwell service active
- **Bit 4**: Linked to another preempt
- **Bit 5**: Exit interval active
- **Bit 6**: Max presence exceeded

## 5.7.7 Preempt Queue Delay Table

Configures priority queue weighting when multiple preempts are active.

### 5.7.7.1 Preempt Detector Weight
**Object**: preemptDetectorWeight  
**Type**: INTEGER (0..255)  
**Access**: read-write  

Weight/priority for queue ordering. Higher values = higher priority in queue.

## 5.7.8 Maximum Preemption Gates
**Object**: maxPreemptionGates  
**Type**: INTEGER (0..255)  
**Access**: read-only  

Maximum number of preemption gate controls. Gates allow conditional preemption based on external factors.

## 5.7.9 Preempt Gate Table

### 5.7.9.1 Preempt Gate Number
**Object**: preemptGateNumber  
**Type**: INTEGER (1..maxPreemptionGates)  
**Access**: not-accessible  

### 5.7.9.2 Preempt Gate Status
**Object**: preemptGateStatus  
**Type**: INTEGER  
**Access**: read-write  

Control gate state:
- **other (1)**
- **gateClosed (2)**: Gate closed (preempt blocked)
- **gateOpen (3)**: Gate open (preempt allowed)

**Use case**: Time-of-day gating or conditional preemption based on traffic conditions.

### 5.7.9.3 Preempt Gate Description
**Object**: preemptGateDescription  
**Type**: DisplayString  
**Access**: read-write  

Descriptive name for this gate.

---

*© 2023 AASHTO / ITE / NEMA*
