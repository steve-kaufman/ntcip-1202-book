# Section 2: Concept of Operations [Normative]

## Overview

Section 2 defines the user needs that subsequent sections within NTCIP 1202 v03 address. This concept of operations provides the reader with:

- A detailed description of the scope of NTCIP 1202 v03
- An explanation of how an ASC is expected to fit into the larger context of an ITS network
- A starting point in the agency procurement process
- An understanding of the perspective of the designers of NTCIP 1202 v03

**Intended Audience:**
- Transportation system managers
- Transportation operations personnel
- Transportation engineers
- System integrators
- Device manufacturers

## 2.1 Tutorial [Informative]

A concept of operations describes a proposed system from the users' perspective. Within the context of NTCIP standards, a concept of operations documents the intent of each feature for which NTCIP 1202 v03 supports a communications interface.

The concept of operations then documents key aspects about the proposed system, including:

1. **Reference Physical Architecture**: Defines the overall context of the proposed system and which specific interfaces are addressed by NTCIP 1202 v03
2. **Architectural Needs**: Discusses the issues and needs relative to the system architecture that have a direct impact on NTCIP 1202 v03
3. **Features**: Identify and describe the various functions that users may want components of an ASC system to perform

## 2.2 Current Situation and Problem Statement [Informative]

Transportation system managers use ASCs to control traffic operations on a roadway. ASCs allow different conflicting movements to travel across a roadway in a safe, orderly manner. Implemented correctly, ASCs can reduce:

- The number and severity of accidents
- Delays
- Stops
- Fuel consumption
- Emission of pollutants

### Travel Modes

Travel modes that have movements controllable by an ASC include:
- Vehicles
- Pedestrians
- Bicycles
- Special vehicles (emergency vehicles, transit vehicles, HOV)

### ASC Capabilities

- **Traffic Detection**: Use inputs from detectors to measure demand and improve mobility
- **Signal Preemption**: Allow emergency vehicles or railroad crossings to preempt the signal
- **Signal Priority**: Allow transit or fleet vehicles to request preferential treatment
- **Connected Vehicle Support**: Provide signal phasing and timing (SPaT) information to connected devices

## 2.3 Reference Physical Architecture [Informative]

### ASC System Components

#### a) Controller Unit (CU)
A host computing platform that manages traffic signals at an intersection. Responsible for ensuring proper signal indications and communicating with the Traffic Management System and other devices.

#### b) Management Station
Host computing platforms that manage one or more NTCIP field devices. Responsible for configuring, monitoring, and controlling the ASC.

#### c) Traffic Management System (TMC)
Typically located in a management center, acts as a management station with respect to the ASC.

#### d) Maintenance Laptop
A computer that field technicians use to access the ASC directly, typically plugging into the Controller Unit.

#### e) Roadside Unit (RSU)
A connected vehicle field device that supports secure communications with connected devices using V2X communications.

#### f) Detection Subsystems
Units that provide inputs for traffic-actuated control, surveillance, or data collection systems.

#### g) Cabinet Subsystems
The controller assembly consisting of electrical devices in the cabinet for controlling traffic signals.

### 2.3.1 ASC Characteristics—Cabinet Specifications

Five common transportation cabinet architectures in North America:

1. **Model 332 Cabinet** - Caltrans TEES specification
2. **NEMA TS 1 Cabinet** - Defined in NEMA TS 1
3. **NEMA TS 2 Type 2 Cabinet** - Defined in NEMA TS 2
4. **NEMA TS 2 Type 1 Cabinet** - Defined in NEMA TS 2
5. **ITS Cabinet** - Specification for ITS enclosures

#### Cabinet Subsystems Include:

- **Bus/Serial Interface Unit or Parallel IO**: Communications interface between CU and cabinet subsystem
- **Power Distribution**: Protected power distribution to components
- **Flashers**: Devices for fail-safe flashing operation
- **Load Switches**: Switch power to signal lamps/indications
- **Signal Monitoring Unit**: Performs signal monitoring functions (MMU or CMU)
- **Detector Units**: Support detection of travelers

### 2.3.2 ASC Characteristics—Controller Types

**Phase-based controller**: Implements non-conflicting signal indications in response to traffic conditions. Phases can be skipped if no traffic present. Green durations vary between min/max values.

**Interval-based controller**: Implements a sequence of defined discrete steps in a repeating cycle. Some sequences may be skipped based on traffic.

> **Note**: Only phase-based controllers are supported by NTCIP 1202 v03.

### 2.3.3 ASC Characteristics—Connected Vehicle Interface

NTCIP 1202 v03 addresses communications between an ASC and a Roadside Unit (RSU). The system includes two logical processes:

#### ASC Process
Traditional processes providing control of a signalized intersection, using inputs from detection subsystems or CV Roadside Process. Generates signal phase and timing information.

#### CV Roadside Process
Runs intersection CV applications, broadcasts SPaT and MAP messages, processes Basic Safety Messages (BSMs) and Personal Safety Messages (PSMs).

#### Two Physical Architectures Considered:

1. **Physical Architecture 1**: CV Roadside Process located in the RSU (separate device)
2. **Physical Architecture 2**: CV Roadside Process and ASC Process in same physical device (e.g., Advanced Traffic Controller)

## 2.4 Architectural Needs

The management station needs to:
- Monitor the status of the ASC
- Manage the database in the ASC
- Control the ASC
- Retrieve collected data

The CV Roadside Process needs:
- Current and future signal phasing and timing information
- Data to forward to connected devices

### 2.4.1 Provide Live Data
Management station monitors and controls the ASC by issuing requests. ASC responds with live data or success/failure notices.

### 2.4.2 Provide Dynamic Object Data
Groups sets of data together for efficient transmission over limited-capacity channels.

### 2.4.3 Provide Block Data
Pre-defined blocks of data addressing different functional areas, reducing upload/download times.

### 2.4.4 Provide for Log Data Local Storage and Retrieval
ASC provides logged data to management station for diagnostic purposes and for environments without always-on connections.

### 2.4.5 Provide for Database Management
ASC performs consistency checks on downloaded data. User can manage database by opening, verifying, and closing it.

### 2.4.6 Condition-Based Exception Reporting
ASC automatically transmits data to management station when certain conditions occur (e.g., cabinet door opened, error flash, phase activation).

## 2.5 Features

### 2.5.1 Manage the ASC Configuration

#### 2.5.1.1 Retrieve Device Identity
Manage basic information about the ASC: location, make, model, version, and unique identifier.

#### 2.5.1.2 Manage Communications
Enable/disable communications ports and configure port addresses.

#### 2.5.1.3 Monitor Cabinet Environment
Monitor cabinet door status, temperature, and fan operation.

#### 2.5.1.4 Monitor Power
Monitor power sources and determine if operating on alternate power.

#### 2.5.1.5 Retrieve Operational Performance Data
Retrieve high-resolution data for signal timing analysis (e.g., Indiana Traffic Signal Hi Resolution Data Logger).

#### 2.5.1.6 Manage Auxiliary External Inputs/Outputs
Monitor and control auxiliary external devices not related to signal control.

#### 2.5.1.7 Manage Database
Manage configuration and version of the database in the ASC.

### 2.5.2 Manage Signal Operations

#### 2.5.2.1 Manage Signal Configuration

**2.5.2.1.1 Manage Controller Startup Functions**
Configure startup capabilities, backup time, and minimum clearance times.

**2.5.2.1.2 Manage Phase Configurations**
Configure minimum/maximum durations, clearance times, concurrent phases, and phase options.

**2.5.2.1.3 Manage Coordination Configurations**
Configure coordination modes and coordination points.

**2.5.2.1.4 Manage Timing Patterns**
Configure cycle length, splits, offsets, and phase sequences.

**2.5.2.1.5 Manage Splits Configurations**
Configure phase assignment, coordinated phase, split time, and split mode.

**2.5.2.1.6 Manage Ring Configurations**
Configure sequence of phases for each ring.

**2.5.2.1.7 Manage Channel Configurations**
Configure control source, phase type, flash and dimming characteristics.

**2.5.2.1.8 Manage Overlap Configurations**
Configure overlap operation, included phases, modifier phases, extensions, and clearance times.

**2.5.2.1.9 Manage Preempt Configurations**
Configure minimum durations, phase settings, outputs, clearance times, entry/exit strategies, and priorities.

**2.5.2.1.10 Manage Timing Pattern Scheduler**
Configure scheduler to implement timing patterns based on calendar days, days of week, and times of day.

**2.5.2.1.11 Manage Action Scheduler**
Configure scheduler to perform functions or groups of functions based on time.

**2.5.2.1.12 Manage I/O Mapping**
Configure input/output mapping to reassign unused inputs or outputs.

**2.5.2.1.13 Manage Intra-Cabinet Communications Configuration**
Configure ASC's intra-cabinet communications port (NEMA TS 2 Port 1 or ITS Cabinet Serial Bus 1).

**2.5.2.1.14 Manage ADA Support**
Configure ASC to support Accessible Pedestrian Signals (APS).

#### 2.5.2.2 Monitor Signal Operations Status

Sub-features include:
- Determine Controller Health
- Determine Mode of Operation
- Monitor Signal Indication
- Monitor Phase Status
- Monitor Ring Status
- Monitor Channel Status
- Monitor Overlap Status
- Monitor Preempt Input State
- Monitor Preempt State
- Monitor Special Function Outputs
- Monitor Timebase Action Status
- Monitor Intra-Cabinet Communications Configuration

#### 2.5.2.3 Control Signal Operations

Sub-features include:
- Control ASC-Wide General Operations
- Command Timing Pattern
- Phase Requests (omit, hold, force off, place calls)
- Activate Preempt
- Control Ring Operations
- Activate Special Function Output
- Control Frame 40
- Activate Action Plan
- Remote Manual Control

---

*© 2023 AASHTO / ITE / NEMA*
