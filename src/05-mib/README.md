# Section 5: Management Information Base (MIB) [Normative]

## Overview

The Management Information Base (MIB) defines all data objects that can be accessed via NTCIP protocols for Actuated Signal Controllers. This section provides the detailed specifications for each parameter, including data types, valid ranges, and access permissions.

## 5.1 MIB Header

The MIB is organized using the SNMP Structure of Management Information (SMI) and follows NTCIP object identifier conventions.

## MIB Organization

The NTCIP 1202 MIB is organized into the following major sections:

### Core Functional Areas

1. **[Phase Parameters](phases.md)** (Section 5.2)
   - Phase timing parameters
   - Phase status and control
   - Phase concurrency and sequencing

2. **[Detector Parameters](detectors.md)** (Section 5.3)
   - Vehicle detector configuration
   - Pedestrian detector configuration
   - Volume/occupancy reporting
   - Detector status and control

3. **[Unit Parameters](units.md)** (Section 5.4)
   - Controller unit configuration
   - Communications settings
   - Alarm status and control
   - Clock and time synchronization
   - Special function outputs

4. **[Coordination Parameters](coordination.md)** (Section 5.5)
   - Coordination modes
   - Pattern definitions
   - Split configurations
   - Offset timing

5. **[Time Base Parameters](coordination.md#56-time-base-parameters)** (Section 5.6)
   - Time-based action scheduling
   - Pattern activation by time of day
   - Action plan commands

6. **[Preempt Parameters](preempts.md)** (Section 5.7)
   - Preemption configuration
   - Preempt status and control
   - Queue delay settings
   - Gate status

7. **Ring Parameters** (Section 5.8)
   - Ring sequences
   - Ring control
   - Ring status

8. **Channel Parameters** (Section 5.9)
   - Channel configuration
   - Channel status
   - Flash and dim settings

9. **Overlap Parameters** (Section 5.10)
   - Overlap type and configuration
   - Overlap status
   - Trailing times

10. **Additional Sections** (5.11 - 5.22)
    - Port parameters
    - Scheduler parameters
    - Overlaps
    - Database management
    - Event logging
    - Dynamic objects
    - I/O mapping
    - Environmental monitoring
    - Connected vehicle interface

## Data Access Conventions

### Access Types
- **read-only**: Parameter can only be read, not modified
- **read-write**: Parameter can be read and modified
- **read-create**: Parameter can be created, read, and modified
- **not-accessible**: Internal parameter not directly accessible

### Parameter Types
- **Configuration Parameters**: Define how the controller operates (typically read-write)
- **Status Parameters**: Report current state (typically read-only)
- **Control Parameters**: Allow external commands (typically read-write)

## Units and Data Types

Common data types used throughout the MIB:

- **INTEGER**: Whole numbers (may have enumerated values)
- **OCTET STRING**: String of bytes or text
- **BITS**: Bit field where each bit has specific meaning
- **Counter**: Monotonically increasing value
- **Gauge**: Value that can increase or decrease

### Time Units
- Most timing parameters are in **tenths of seconds** (0.1 second resolution)
- Some high-resolution parameters use **milliseconds**
- Timestamps typically use **seconds since epoch**

### Special Values
- **0**: Often means "disabled" or "not configured"
- **255** or **65535**: Often means "maximum" or "unlimited"

## Table Organization

Many MIB objects are organized in tables with:
- **Index**: Unique identifier for each table entry (e.g., phase number, detector number)
- **Parameters**: Configuration values for that entry
- **Status**: Current state of that entry

## Consistency Requirements

When modifying configuration parameters:
1. Open the database (set maxDatabaseEntries)
2. Modify parameters
3. Verify consistency (check databaseVerifyStatus)
4. Close the database (activate changes)

Failure to follow this sequence may result in rejected changes or inconsistent configuration.

## Block Objects

For efficient data transfer, related parameters can be accessed using block objects defined in Section 6. Block objects group multiple parameters into a single transfer unit.

---

*© 2023 AASHTO / ITE / NEMA*
