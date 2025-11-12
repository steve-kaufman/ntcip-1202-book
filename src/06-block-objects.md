# Section 6: Block Object Definitions

## 6.1 Block Data Type and ID

Block data provides a mechanism to efficiently transfer groups of related data between management stations and ASCs. Each block type has:
- A unique block identifier
- A defined structure containing specific MIB objects
- A standard data format for serialization

Block data is particularly useful for:
- Reducing the number of messages needed for bulk configuration
- Minimizing bandwidth usage on limited-capacity channels
- Simplifying configuration management

## Block Types Overview

| Block Type | Description |
|------------|-------------|
| Phase Block | Phase timing and configuration parameters |
| Vehicle Detector Block | Vehicle detector configuration |
| Pedestrian Detector Block | Pedestrian detector configuration |
| Pattern Block | Coordination pattern definitions |
| Split Block | Split timing definitions |
| Time Base Block | Time-based scheduling |
| Preempt Block | Preemption configuration |
| Sequence Block | Phase sequence definitions |
| Channel Block | Channel output configuration |
| Overlap Block | Overlap phase configuration |
| Port 1 Block | NEMA TS 2 Port 1 configuration |
| Schedule Block | Event scheduling |
| Day Plan Block | Daily schedule plans |
| Event Log Config Block | Event logging configuration |
| Event Class Block | Event classification |
| Dynamic Object Config Block | Dynamic object configuration |
| Dynamic Object Owner Block | Dynamic object ownership |
| Dynamic Object Status Block | Dynamic object status |
| Miscellaneous ASC Block | General ASC parameters |

## 6.2 Phase Block Data

Contains all configuration parameters for a single phase including:
- Minimum and maximum green times
- Pedestrian walk and clearance times
- Yellow change and red clearance times
- Phase options and concurrency settings
- Ring assignment

### 6.2.1 Phase Block Example
Example data structure showing typical phase configuration values.

## 6.3 Vehicle Detector Block Data

Contains vehicle detector configuration including:
- Detector options (locking, delayed call, etc.)
- Call phase and switch phase assignments
- Delay and extend timers
- Fault detection parameters
- Queue limit settings

### 6.3.1 Vehicle Detector Block Example
Example showing vehicle detector configuration.

## 6.4 Pedestrian Detector Block Data

Contains pedestrian detector configuration including:
- Call phase assignment
- Pushbutton duration
- Fault detection parameters
- Detector options

### 6.4.1 Pedestrian Detector Block Example
Example pedestrian detector configuration.

## 6.5 Pattern Block Data

Contains coordination pattern parameters including:
- Cycle length
- Offset time
- Split assignment
- Sequence assignment
- Coordination sync point
- Enabled lanes for connected vehicle support

### 6.5.1 Pattern Block Example
Example coordination pattern configuration.

## 6.6 Split Block Data

Contains split definitions including:
- Phase assignments for each split position
- Split times
- Split mode (actuated or fixed)
- Coordinated phase designation

### 6.6.1 Split Block Example
Example split configuration.

## 6.7 Time Base Block Data

Contains time-based action configuration including:
- Pattern to activate
- Auxiliary function settings
- Special function outputs
- Enabled lane configuration

### 6.7.1 Time Base Block Example
Example time-based scheduling entry.

## 6.8 Preempt Block Data

Contains preempt configuration including:
- Control settings and priority
- Timing parameters (delay, duration, minimum green/walk)
- Phase assignments (track, dwell, exit)
- Entry and exit strategies
- Clearance times

### 6.8.1 Preempt Block Example
Example preemption configuration.

## 6.9 Sequence Block Data

Contains phase sequence definitions for each ring:
- Ring number
- Ordered list of phases in sequence
- Barrier definitions

### 6.9.1 Sequence Block Example
Example sequence configuration.

## 6.10 Channel Block Data

Contains channel output configuration including:
- Control source (phase, overlap, etc.)
- Control type (vehicle, pedestrian, bicycle)
- Flash and dimming settings
- Movement type for connected vehicle support

### 6.10.1 Channel Block Example
Example channel configuration.

## 6.11 Overlap Block Data

Contains overlap configuration including:
- Overlap type
- Included and modifier phases
- Trailing green/yellow/red times
- Pedestrian parameters
- Conflicting pedestrian phases

### 6.11.1 Overlap Block Example
Example overlap configuration.

## 6.12 Port 1 Block Data

Contains NEMA TS 2 Port 1 configuration for intra-cabinet communications.

### 6.12.1 Port 1 Block Example
Example Port 1 configuration.

## 6.13 Schedule Block Data

Contains scheduling information for when timing patterns should be activated based on calendar and time of day.

### 6.13.1 Schedule Block Example
Example schedule entry.

## 6.14 Day Plan Block Data

Contains daily schedule plan linking time-of-day to actions.

### 6.14.1 Day Plan Block Example
Example day plan.

## Additional Block Types

### 6.15 Event Log Config Block Data
Configuration for event logging functionality.

### 6.16 Event Class Block Data
Classification of events for logging and reporting.

### 6.17 Dynamic Object Config Block Data
Configuration of dynamic objects for efficient data polling.

### 6.18 Dynamic Object Owner Block Data
Ownership and access control for dynamic objects.

### 6.19 Dynamic Object Status Block Data
Status information for dynamic objects.

### 6.20 Miscellaneous ASC Block Data
General ASC parameters not covered in other blocks.

### Version 2 and Extended Blocks
Many block types have version 2 variants with additional fields or enhanced functionality:
- Phase 2 Block Data
- Vehicle Detector 2 Block Data
- Pedestrian Detector 2 Block Data
- Pattern 2 Block Data
- Split 2 Block Data
- Preempt 2 Block Data
- Channel 2 Block Data
- Overlap 2 Block Data

### Connected Vehicle Related Blocks
- CV Configuration ASC Block Data
- CV Logical RSU Ports Configuration Block Data
- CV SPaT Enabled Lanes Concurrency Configuration Block Data
- CV SPaT RSU Ports Configuration Block Data
- CV Detector Configuration Block Data
- CV Detection Zone Configuration
- CV Detection Report Block Data

### Additional Configuration Blocks
- Communications Port Definition Block Data
- Ethernet Comm Port Definition Block Data
- User-Defined Backup Timer Definition Block Data
- ASC Location Block Data
- Global Set ID Definition Block Data
- ASC Environmental Monitoring Block Data
- ASC I/O Input/Output Mapping and Status Block Data

---

*© 2023 AASHTO / ITE / NEMA*
