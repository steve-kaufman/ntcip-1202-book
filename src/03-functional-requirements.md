# Section 3: Functional Requirements

## 3.1 Tutorial [Informative]

This section defines the functional requirements for NTCIP 1202 Actuated Signal Controller (ASC) systems. The requirements are organized hierarchically and use a standardized notation system for conformance.

## 3.2 Scope of the Interface [Informative]

The functional requirements define what an ASC implementation must support to be conformant with this standard. Requirements cover configuration, monitoring, and control of all ASC subsystems.

## 3.3 Protocol Requirements List (PRL)

### 3.3.1 Notation [Informative]

#### 3.3.1.1 Conformance Symbols

The PRL uses standardized symbols to indicate requirement status:
- **M** = Mandatory
- **O** = Optional
- **O.n** = Optional (numbered for reference)
- **C** = Conditional
- **X** = Prohibited

#### 3.3.1.2 Conditional Status Notation

Conditional requirements use the format "C.condition" where the condition specifies when the requirement applies.

#### 3.3.1.3 Support Column Symbols

The Support column in the PRL indicates implementation status for specific devices or systems.

### 3.3.2 Instructions for Completing the PRL [Informative]

#### 3.3.2.1 Conformance Definition

Implementers must complete the PRL to document which requirements their implementation supports. This creates a Protocol Implementation Conformance Statement (PICS).

### 3.3.3 Protocol Requirements List (PRL) Table

The complete PRL table is specified in the standard (pages 44-95) and contains detailed requirement IDs, descriptions, and conformance status for all objects and functions defined in this standard.

## 3.4 Architectural Requirements

### 3.4.1 Support Basic Communications Requirements

#### 3.4.1.1 Retrieve Data
ASC shall support retrieval of data via SNMP GET operations.

#### 3.4.1.2 Deliver Data
ASC shall support setting data via SNMP SET operations.

#### 3.4.1.3 Explore Data
ASC shall support discovery of supported objects via SNMP operations.

#### 3.4.1.4 SNMP Requirements

##### 3.4.1.4.1 Monitor SNMP Information
Ability to retrieve SNMP system information and statistics.

##### 3.4.1.4.2 Monitor Successful SNMP GET Requests
Track successful GET operation counts.

##### 3.4.1.4.3 Monitor Valid SNMP SET Requests
Track successful SET operation counts.

##### 3.4.1.4.4 Monitor SNMP Traps
Support for SNMP trap notifications.

##### 3.4.1.4.5 Enable Authentication Traps
Configure authentication failure trap generation.

### 3.4.2 Support Logged Data Requirements
Ability to log and retrieve operational performance data and events.

### 3.4.3 Support Exception Reporting Requirements
Generate and report exception conditions via traps or alarms.

### 3.4.4 Manage Access Requirements

#### 3.4.4.1 Configure Access
Set access control parameters for communications security.

#### 3.4.4.2 Determine Current Access Settings
Retrieve current access control configuration.

## 3.5 Data Exchange and Operational Environment Requirements

### 3.5.1 ASC Configuration Management Requirements

#### 3.5.1.1 Manage ASC Location Requirements

##### 3.5.1.1.1 Configure ASC Location
Set geographic coordinates and location data for the ASC.

##### 3.5.1.1.2 Configure ASC Location—Antenna Offset
Set elevation offset for GPS antenna placement.

#### 3.5.1.2 Manage Communications Requirements

##### 3.5.1.2.1 Configure Communications Requirements

###### 3.5.1.2.1.1 Enable/Disable Communications Port
Control availability of individual communication ports.

###### 3.5.1.2.1.2 Configure ASC Ethernet Ports
Configure IP addressing, subnet masks, gateways, and DNS for Ethernet interfaces.

###### 3.5.1.2.1.3 Configure ASC Asynchronous Serial Ports
Set baud rate, parity, and other serial port parameters for asynchronous communications.

###### 3.5.1.2.1.4 Configure ASC Synchronous Serial Ports
Configure synchronous serial communication parameters.

###### 3.5.1.2.1.5 Configure ASC Communications Protocol—Serial Ports
Select communication protocol for serial interfaces.

##### 3.5.1.2.2 Retrieve Communications Requirements

###### 3.5.1.2.2.1 Determine Number of ASC Communications Ports
Query available communication interfaces.

##### 3.5.1.2.3 Monitor Communications Requirements

###### 3.5.1.2.3.1 Monitor Response Timeout—Ethernet
Track Ethernet communication timeouts.

###### 3.5.1.2.3.2 Monitor Response Timeout—Serial
Track serial communication timeouts.

###### 3.5.1.2.3.3 Monitor Data Link Errors—Ethernet
Monitor Ethernet layer errors.

###### 3.5.1.2.3.4 Monitor Data Link Errors—Serial
Monitor serial communication errors.

###### 3.5.1.2.3.5 Monitor Polling Timeout—Port 1
Detect polling failures on primary port.

###### 3.5.1.2.3.6 Monitor Polling Timeout—Serial Bus
Detect serial bus polling failures.

##### 3.5.1.2.4 Perform Communications Diagnostics Requirements

###### 3.5.1.2.4.1 Set Communications Port to Loopback Mode
Enable loopback testing for diagnostics.

###### 3.5.1.2.4.2 Set Communications Port to Echo Mode
Enable echo mode for testing.

#### 3.5.1.3 Retrieve Cabinet Environment Requirements

##### 3.5.1.3.1 Monitor Cabinet Door Status
Detect cabinet door open/closed state.

##### 3.5.1.3.2 Monitor Cabinet Fan Status
Monitor fan operational status.

##### 3.5.1.3.3 Monitor Cabinet Heater Status
Monitor heater operational status.

##### 3.5.1.3.4 Monitor Cabinet Float Switch Status
Detect water intrusion via float switch.

##### 3.5.1.3.5 Monitor ASC Temperature
Read current cabinet temperature.

##### 3.5.1.3.6 Monitor ASC Humidity
Read current cabinet humidity level.

##### 3.5.1.3.7 Configure ASC Temperature Threshold
Set high/low temperature alarm thresholds.

##### 3.5.1.3.8 Configure ASC Humidity Thresholds
Set humidity alarm thresholds.

##### 3.5.1.3.9 Configure ATC Cabinet Device LEDs
Control LED indicators on cabinet devices.

#### 3.5.1.4 Monitor Power Requirements

##### 3.5.1.4.1 Determine Power Source
Identify current power source (AC, UPS, etc.).

##### 3.5.1.4.2 Monitor AC Power Status
Detect AC power presence and quality.

##### 3.5.1.4.3 Monitor UPS Battery Charge
Read UPS battery charge percentage.

##### 3.5.1.4.4 Monitor UPS Battery Voltage
Monitor battery voltage levels.

##### 3.5.1.4.5 Monitor UPS Battery Current
Monitor battery current draw.

#### 3.5.1.5 Manage Operational Performance Data Requirements

##### 3.5.1.5.1 Configure Operational Performance Data Requirements

###### 3.5.1.5.1.1 Enable/Disable Collection of Operational Performance Data
Turn data collection on/off.

###### 3.5.1.5.1.2 Start Collection of Operational Performance Data on Specific Date/Time
Schedule collection start.

###### 3.5.1.5.1.3 End Collection of Operational Performance Data on Specific Date/Time
Schedule collection end.

###### 3.5.1.5.1.4 Configure Collection of Operational Performance Data
Set data collection parameters.

##### 3.5.1.5.2 Retrieve Operational Performance Data Configuration Requirements

###### 3.5.1.5.2.1 Determine Collection of Operational Performance Data
Query current collection status.

###### 3.5.1.5.2.2 Determine Operational Performance Data Collection Capabilities
Query supported data types and storage capacity.

##### 3.5.1.5.3 Retrieve Operational Performance Data Requirements

###### 3.5.1.5.3.1 Monitor Operational Performance Data
Access current performance metrics.

###### 3.5.1.5.3.2 Retrieve Operational Performance Data
Download collected data.

###### 3.5.1.5.3.3 Retrieve Operational Performance Data—Time Range
Filter data by time period.

###### 3.5.1.5.3.4 Retrieve Operational Performance Data—Event Code
Filter data by event type.

##### 3.5.1.5.4 Clear Operational Performance Data Requirements

###### 3.5.1.5.4.1 Clear Operational Performance Data—All
Delete all collected data.

###### 3.5.1.5.4.2 Clear Operational Performance Data—Time Range
Delete data for specific time period.

###### 3.5.1.5.4.3 Clear Operational Performance Data—Event Code
Delete data for specific event types.

###### 3.5.1.5.4.4 Clear Operational Performance Data—Event Class
Delete data for event classes.

###### 3.5.1.5.4.5 Clear Operational Performance Data—Configuration
Reset collection configuration.

#### 3.5.1.6 Manage ASC Clock Requirements

##### 3.5.1.6.1 Configure ASC Clock Source
Select time source (GPS, NTP, local, etc.).

##### 3.5.1.6.2 Determine ASC Clock Status
Query clock synchronization status.

##### 3.5.1.6.3 Determine Current ASC Clock Source
Identify active time source.

##### 3.5.1.6.4 Determine Available ASC Clock Sources
List all available time sources.

### 3.5.2 Manage Signal Operations Management Requirements

#### 3.5.2.1 Manage Signal Configuration Requirements

##### 3.5.2.1.1 Manage Unit Configuration Requirements

###### 3.5.2.1.1.1 Manage Startup Requirements

- **3.5.2.1.1.1.1 Configure Startup All-Red Flash Mode** - Set flash pattern during startup
- **3.5.2.1.1.1.2 Configure Startup Flash Time** - Duration of startup flash
- **3.5.2.1.1.1.3 Enable/Disable Automatic Pedestrian Clearance Setting** - Auto-calculate ped clear times

###### 3.5.2.1.1.2 Configure Backup Time
Set time to maintain on battery backup.

###### 3.5.2.1.1.3 Configure Backup Time—User-Defined
Define custom backup time parameters.

###### 3.5.2.1.1.4 Configure Backup Time—User-Defined Functions
Specify functions to monitor during backup.

###### 3.5.2.1.1.5 Determine Maximum Number of Functions Supported for Backup Time
Query backup monitoring capabilities.

###### 3.5.2.1.1.6 Configure Parameters for Creation of an Alternate Device Configuration Identifier
Set alternate configuration ID parameters.

##### 3.5.2.1.2 Manage Phase Configuration Requirements

###### 3.5.2.1.2.1 Configure Phases Requirements

**Vehicle Phase Timing:**
- **3.5.2.1.2.1.1 Enable/Disable Phase**
- **3.5.2.1.2.1.2 Configure Vehicle Phase Minimum Green Time**
- **3.5.2.1.2.1.3 Configure Vehicle Phase Passage Time**
- **3.5.2.1.2.1.4 Configure Vehicle Phase Maximum Green Times** (Max 1, Max 2)
- **3.5.2.1.2.1.5 Configure Vehicle Phase Third Maximum Green Times** (Max 3)
- **3.5.2.1.2.1.6 Configure Phase Yellow Time**
- **3.5.2.1.2.1.7 Configure Red Clearance Time**
- **3.5.2.1.2.1.8 Configure Phase Red Revert Time**
- **3.5.2.1.2.1.9 Configure Unit Red Revert Time**

**Gap Reduction:**
- **3.5.2.1.2.1.10 Configure Added Initial Time**
- **3.5.2.1.2.1.11 Configure Maximum Initial Time**
- **3.5.2.1.2.1.12 Configure Time Before Reduction**
- **3.5.2.1.2.1.13 Configure Phase Time to Reduce**
- **3.5.2.1.2.1.14 Configure Cars Before Reduction**
- **3.5.2.1.2.1.15 Configure Phase Reduce By Time**
- **3.5.2.1.2.1.16 Configure Phase Minimum Gap Time**

**Dynamic Maximum:**
- **3.5.2.1.2.1.17 Configure Phase Dynamic Maximum Limit**
- **3.5.2.1.2.1.18 Configure Phase Dynamic Maximum Step**

**Phase Startup and Flash:**
- **3.5.2.1.2.1.19 Configure Phase Startup Requirements**
- **3.5.2.1.2.1.20 Configure Automatic Flash Entry Phase**
- **3.5.2.1.2.1.21 Configure Automatic Flash Exit Phase**

**Actuated Operation:**
- **3.5.2.1.2.1.22 Configure Call to Non-Actuated 1**
- **3.5.2.1.2.1.23 Configure Call to Non-Actuated 2**
- **3.5.2.1.2.1.24 Configure Non-Lock Detector Memory**
- **3.5.2.1.2.1.25 Configure Minimum Vehicle Recall**
- **3.5.2.1.2.1.26 Configure Maximum Vehicle Recall**
- **3.5.2.1.2.1.27 Configure Soft Vehicle Recall**

**Dual-Ring Features:**
- **3.5.2.1.2.1.28 Configure Dual Phase Entry**
- **3.5.2.1.2.1.29 Configure Simultaneous Gap Disable**
- **3.5.2.1.2.1.30 Configure Guaranteed Passage**
- **3.5.2.1.2.1.31 Configure Actuated Rest-in-Walk**
- **3.5.2.1.2.1.32 Configure Conditional Service Enable**
- **3.5.2.1.2.1.33 Configure Added Initial Calculation**
- **3.5.2.1.2.1.34 Configure Phase-to-Ring Association**
- **3.5.2.1.2.1.35 Configure Phase Concurrency**

**Pedestrian Phase Settings:**
- **3.5.2.1.2.1.36 Configure Yellow Change Time Before End of Ped Clearance**
- **3.5.2.1.2.1.37 Enable/Disable Ped-Only Phase**
- **3.5.2.1.2.1.38 Configure Pedestrian Green Time** (Walk)
- **3.5.2.1.2.1.39 Configure Pedestrian Clearance Time** (Flashing Don't Walk)
- **3.5.2.1.2.1.40 Configure Ped Phase Walk Recycle Time**
- **3.5.2.1.2.1.41 Configure Ped Phase Don't Walk Revert Time**
- **3.5.2.1.2.1.42 Configure Non-Lock Ped Detector Memory**
- **3.5.2.1.2.1.43 Configure Pedestrian Recall**
- **3.5.2.1.2.1.44 Configure Alternate Pedestrian Clearance Time**
- **3.5.2.1.2.1.45 Configure Alternate Pedestrian Walk Time**
- **3.5.2.1.2.1.46 Configure Vehicle Phase Walk Offset Time**

**Advanced Warning:**
- **3.5.2.1.2.1.47 Configure Advanced Green Warning—Associated Vehicle Phase**
- **3.5.2.1.2.1.48 Configure Advanced Green Warning—Start Delay Time**
- **3.5.2.1.2.1.49 Configure Advanced Red Warning—Associated Vehicle Phase**
- **3.5.2.1.2.1.50 Configure Red Indication Advanced Warning—Start Delay Time**

**Flashing Arrow:**
- **3.5.2.1.2.1.51 Configure Flashing Yellow Arrow Associated Vehicle Phase**
- **3.5.2.1.2.1.52 Configure Flashing Red Arrow Associated Vehicle Phase**

**Bicycle Phase Settings:**
- **3.5.2.1.2.1.53 Configure Bicycle Phase Minimum Green Time**
- **3.5.2.1.2.1.54 Configure Bicycle Phase Yellow Time**
- **3.5.2.1.2.1.55 Configure Bicycle Phase Red Clearance Time**
- **3.5.2.1.2.1.56 Configure Bicycle Phase Red Revert Time**
- **3.5.2.1.2.1.57 Enable/Disable Bicycle Phase**
- **3.5.2.1.2.1.58 Configure Non-Lock Bicycle Detector Memory**
- **3.5.2.1.2.1.59 Configure Bicycle Phase Recall**
- **3.5.2.1.2.1.60 Configure Soft Bicycle Phase Recall**
- **3.5.2.1.2.1.61 Configure Bicycle Phase-to-Ring Association**
- **3.5.2.1.2.1.62 Configure Bicycle Phase Concurrency**

**Transit Phase Settings:**
- **3.5.2.1.2.1.63 Configure Transit Phase Minimum Green Time**
- **3.5.2.1.2.1.64 Configure Transit Phase Maximum Green Time**
- **3.5.2.1.2.1.65 Configure Transit Phase Third Maximum Green Time**
- **3.5.2.1.2.1.66 Configure Transit Phase Yellow Time**
- **3.5.2.1.2.1.67 Configure Transit Phase Red Clearance Time**
- **3.5.2.1.2.1.68 Configure Transit Phase Red Revert Time**
- **3.5.2.1.2.1.69 Configure Transit Phase Added Initial Time**
- **3.5.2.1.2.1.70 Configure Transit Phase Maximum Initial Time**
- **3.5.2.1.2.1.71 Enable/Disable Transit Phase**
- **3.5.2.1.2.1.72 Configure Non-Lock Transit Detector Memory**
- **3.5.2.1.2.1.73 Configure Transit Phase Recall**
- **3.5.2.1.2.1.74 Configure Soft Transit Phase Recall**
- **3.5.2.1.2.1.75 Configure Dual Transit Phase Entry**
- **3.5.2.1.2.1.76 Configure Transit Phase-to-Ring Association**
- **3.5.2.1.2.1.77 Configure Transit Phase Concurrency**

**Phase Omit Features:**
- **3.5.2.1.2.1.78 Enable/Disable Vehicle Phase Omit**
- **3.5.2.1.2.1.79 Enable/Disable Vehicle Phase Omit During Transition**
- **3.5.2.1.2.1.80 Enable/Disable Ped-Only Phase Omit**
- **3.5.2.1.2.1.81 Enable/Disable Ped-Only Phase Omit During Transition**
- **3.5.2.1.2.1.82 Enable/Disable Bicycle-Only Phase Omit**
- **3.5.2.1.2.1.83 Enable/Disable Bicycle-Only Phase Omit During Transition**
- **3.5.2.1.2.1.84 Enable/Disable Transit Phase Omit**
- **3.5.2.1.2.1.85 Enable/Disable Transit Phase Omit During Transition**

**Transition Minimums:**
- **3.5.2.1.2.1.86 Configure Alternate Minimum Vehicle Green Time During Transition**
- **3.5.2.1.2.1.87 Configure Alternate Minimum Pedestrian Walk Time During Transition**
- **3.5.2.1.2.1.88 Configure Alternate Minimum Bicycle Green Time During Transition**
- **3.5.2.1.2.1.89 Configure Alternate Minimum Transit Green Time During Transition**
- **3.5.2.1.2.1.90 Configure Phase Force Mode for Coordination Requirements**

###### 3.5.2.1.2.2 Retrieve Phase Configuration Requirements

- **3.5.2.1.2.2.1 Determine Maximum Number of Phases** - Query phase capacity

##### 3.5.2.1.3 Manage Coordination Configuration Requirements

###### 3.5.2.1.3.1 Configure Operational Mode for Coordination Requirements

- **3.5.2.1.3.1.1 Configure Operational Mode for Coordination—Automatic**
- **3.5.2.1.3.1.2 Configure Operational Mode for Coordination—Manual Pattern**
- **3.5.2.1.3.1.3 Configure Operational Mode for Coordination—Manual Free**
- **3.5.2.1.3.1.4 Configure Operational Mode for Coordination—Manual Flash**

###### 3.5.2.1.3.2 Configure Correction Mode for Coordination Requirements

- **3.5.2.1.3.2.1 Configure Correction Mode for Coordination—Dwell**
- **3.5.2.1.3.2.2 Configure Correction Mode for Coordination—Shortway**
- **3.5.2.1.3.2.3 Configure Correction Mode for Coordination—AddOnly**
- **3.5.2.1.3.2.4 Configure Correction Mode for Coordination—SubtractOnly**

###### 3.5.2.1.3.3 Configure Maximum Mode for Coordination Requirements

- **3.5.2.1.3.3.1 Configure Correction Mode for Coordination—Maximum 1**
- **3.5.2.1.3.3.2 Configure Correction Mode for Coordination—Maximum 2**
- **3.5.2.1.3.3.3 Configure Correction Mode for Coordination—Maximum Inhibit**
- **3.5.2.1.3.3.4 Configure Correction Mode for Coordination—Maximum 3**

###### 3.5.2.1.3.4 Configure Unit-Level Force Mode for Coordination Requirements

- **3.5.2.1.3.4.1 Configure Unit-Level Force Mode for Coordination—Floating**
- **3.5.2.1.3.4.2 Configure Unit-Level Force Mode for Coordination—Fixed**

###### 3.5.2.1.3.5 Configure Unit Coordination Point Requirements

- **3.5.2.1.3.5.1 Configure Unit Coordination Point—First Phase Green Begin**
- **3.5.2.1.3.5.2 Configure Unit Coordination Point—Last Phase Green Begin**
- **3.5.2.1.3.5.3 Configure Unit Coordination Point—First Phase Green End**
- **3.5.2.1.3.5.4 Configure Unit Coordination Point—Last Phase Green End**
- **3.5.2.1.3.5.5 Configure Unit Coordination Point—First Phase Yellow End**
- **3.5.2.1.3.5.6 Configure Unit Coordination Point—Last Phase Yellow End**

###### 3.5.2.1.3.6 Configure Coordination Point Requirements

- **3.5.2.1.3.6.1 Configure Coordination Point—First Phase Green Begin**
- **3.5.2.1.3.6.2 Configure Coordination Point—Last Phase Green Begin**
- **3.5.2.1.3.6.3 Configure Coordination Point—First Phase Green End**
- **3.5.2.1.3.6.4 Configure Coordination Point—Last Phase Green End**
- **3.5.2.1.3.6.5 Configure Coordination Point—First Phase Yellow End**
- **3.5.2.1.3.6.6 Configure Coordination Point—Last Phase Yellow End**
- **3.5.2.1.3.6.7 Configure Coordination Point—Unit Coordination Point**

###### 3.5.2.1.3.7 Configure Omit Phases During Transitions
###### 3.5.2.1.3.8 Configure Minimum Green Times During Transitions
###### 3.5.2.1.3.9 Configure Minimum Pedestrian Times During Transitions

###### 3.5.2.1.3.10 Configure Transit Maximum Mode for Coordination Requirements

- **3.5.2.1.3.10.1 Configure Transit Correction Mode for Coordination—Maximum 1**
- **3.5.2.1.3.10.2 Configure Transit Correction Mode for Coordination—Maximum 2**
- **3.5.2.1.3.10.3 Configure Transit Correction Mode for Coordination—MaxInhibit**
- **3.5.2.1.3.10.4 Configure Transit Correction Mode for Coordination—Maximum 3**

##### 3.5.2.1.4 Manage Phase-Based Timing Patterns Requirements

###### 3.5.2.1.4.1 Configure Phase-Based Timing Patterns Requirements

- **3.5.2.1.4.1.1 Configure Pattern Cycle Time** - Total cycle length
- **3.5.2.1.4.1.2 Configure Pattern Offset Time** - Coordination offset
- **3.5.2.1.4.1.3 Configure Pattern Split Association** - Link to split table
- **3.5.2.1.4.1.4 Configure Pattern Sequence Association** - Link to ring sequence
- **3.5.2.1.4.1.5 Configure Pattern Maximum Mode** - Set max mode for pattern

###### 3.5.2.1.4.2 Retrieve Phase-Based Timing Patterns Requirements

- **3.5.2.1.4.2.1 Determine Maximum Number of Phase-Based Timing Pattern**
- **3.5.2.1.4.2.2 Determine Phase-Based Timing Pattern Type**

##### 3.5.2.1.5 Manage Splits Configuration Requirements

###### 3.5.2.1.5.1 Configure Split Requirements

- **3.5.2.1.5.1.1 Configure Phase Split Time** - Time allocated to each phase
- **3.5.2.1.5.1.2 Configure Phase Split Mode Requirements** - Actuated vs. pre-timed
- **3.5.2.1.5.1.3 Configure Split Coordination Phase** - Identify coordinated phase
- **3.5.2.1.5.1.4 Configure Pre-Timed Split** - Set fixed split times

###### 3.5.2.1.5.2 Retrieve Split Requirements

- **3.5.2.1.5.2.1 Determine Maximum Number of Phase Splits**

##### 3.5.2.1.6 Manage Ring Configuration Requirements

###### 3.5.2.1.6.1 Configure Ring Requirements

- **3.5.2.1.6.1.1 Configure Sequence Data** - Define phase sequences

###### 3.5.2.1.6.2 Retrieve Rings Requirements

- **3.5.2.1.6.2.1 Determine Maximum Number of Rings**
- **3.5.2.1.6.2.2 Determine Maximum Number of Sequences**

##### 3.5.2.1.7 Manage Channel Configuration Requirements

###### 3.5.2.1.7.1 Configure Channel Requirements

- **3.5.2.1.7.1.1 Configure Channel Control Source** - Phase, overlap, or other source
- **3.5.2.1.7.1.2 Configure Channel Control Type Requirements** - Red/Yellow/Green assignment
- **3.5.2.1.7.1.3 Configure Channel Flash Enable/Disable Requirements**
- **3.5.2.1.7.1.4 Configure Channel Dim Enable/Disable Requirements**

###### 3.5.2.1.7.2 Retrieve Channel Requirements

- **3.5.2.1.7.2.1 Determine Maximum Number of Channels**

##### 3.5.2.1.8 Manage Overlap Configuration Requirements

###### 3.5.2.1.8.1 Configure Overlap Requirements

- **3.5.2.1.8.1.1 Configure Overlap Type Requirements** - Movement type
- **3.5.2.1.8.1.2 Configure Overlap Included Phases** - Parent phases
- **3.5.2.1.8.1.3 Configure Overlap Modifier Phases** - Phases that modify overlap
- **3.5.2.1.8.1.4 Configure Pedestrian Modifier Phases**
- **3.5.2.1.8.1.5 Configure Overlap Trailing Green**
- **3.5.2.1.8.1.6 Configure Overlap Trailing Yellow**
- **3.5.2.1.8.1.7 Configure Overlap Trailing Red Clearance**
- **3.5.2.1.8.1.8 Configure Overlap Walk**
- **3.5.2.1.8.1.9 Configure Overlap Pedestrian Clearance**

###### 3.5.2.1.8.2 Retrieve Overlaps Requirements

- **3.5.2.1.8.2.1 Determine Maximum Number of Overlaps**

##### 3.5.2.1.9 Manage Preempt Configuration Requirements

###### 3.5.2.1.9.1 Configure Preempts for Phase-Based ASC Requirements

- **3.5.2.1.9.1.1 Enable/Disable Preempt Inputs**
- **3.5.2.1.9.1.2 Configure Preempt Control Requirements** - High/low priority
- **3.5.2.1.9.1.3 Configure Preempt Link** - Link multiple preempts
- **3.5.2.1.9.1.4 Configure Preempt Delay** - Delay before activation
- **3.5.2.1.9.1.5 Configure Preempt Minimum Duration**
- **3.5.2.1.9.1.6 Configure Preempt Enter Minimum Green Time**
- **3.5.2.1.9.1.7 Configure Preempt Enter Minimum Walk Time**
- **3.5.2.1.9.1.8 Configure Preempt Enter Pedestrian Clearance Time**
- **3.5.2.1.9.1.9 Configure Preempt Track Clearance Time** - Railroad track clear
- **3.5.2.1.9.1.10 Configure Preempt Minimum Dwell Time**
- **3.5.2.1.9.1.11 Configure Preempt Maximum Presence Time**
- **3.5.2.1.9.1.12 Configure Preempt Track Clearance Phases**
- **3.5.2.1.9.1.13 Configure Preempt Dwell Phases** - Phases during dwell
- **3.5.2.1.9.1.14 Configure Preempt Dwell Pedestrian Movements**
- **3.5.2.1.9.1.15 Configure Preempt Exit Phases**
- **3.5.2.1.9.1.16 Configure Preempt Exit Phase Strategy Requirements**
- **3.5.2.1.9.1.17 Configure Preempt Track Overlap**
- **3.5.2.1.9.1.18 Configure Preempt Dwell Overlap**
- **3.5.2.1.9.1.19 Configure Preempt Cycling Phases**
- **3.5.2.1.9.1.20 Configure Preempt Cycling Pedestrian Movements**
- **3.5.2.1.9.1.21 Configure Preempt Cycling Overlaps**
- **3.5.2.1.9.1.22 Configure Preempt Enter Yellow Change Time**
- **3.5.2.1.9.1.23 Configure Preempt Enter Red Clearance Time**
- **3.5.2.1.9.1.24 Configure Preempt Track Yellow Change Time**
- **3.5.2.1.9.1.25 Configure Preempt Track Red Clearance Time**
- **3.5.2.1.9.1.26 Configure Preempt Exit Priority Levels**
- **3.5.2.1.9.1.27 Configure Preempt Max Presence Exceeded Requirements**
- **3.5.2.1.9.1.28 Configure Preempt Cycling Phases Sequence**
- **3.5.2.1.9.1.29 Configure Preempt Enter Minimum Bicycle Time**
- **3.5.2.1.9.1.30 Configure Preempt Enter Bicycle Clearance Time**
- **3.5.2.1.9.1.31 Configure Preempt Cycling Bicycle Phases**
- **3.5.2.1.9.1.32 Configure Preempt Enter Minimum Transit Time**
- **3.5.2.1.9.1.33 Configure Preempt Enter Transit Clearance Time**
- **3.5.2.1.9.1.34 Configure Preempt Cycling Transit Phases**
- **3.5.2.1.9.1.35 Configure Preempt Gate Description**

###### 3.5.2.1.9.2 Retrieve Preempt Configuration for Phase-Based ASC Requirements

- **3.5.2.1.9.2.1 Determine Maximum Number of Preempts**

##### 3.5.2.1.10 Manage Timing Pattern Scheduler Requirements

###### 3.5.2.1.10.1 Configure Timing Pattern Scheduler Requirements

- **3.5.2.1.10.1.1 Configure Timebase Pattern Synchronization Time**
- **3.5.2.1.10.1.2 Configure Timebased Action—Pattern**
- **3.5.2.1.10.1.3 Configure Timebased Action—Auxiliary Functions Requirements**
- **3.5.2.1.10.1.4 Configure Timebased Action—Special Functions Requirements**

###### 3.5.2.1.10.2 Retrieve Timing Pattern Scheduler Requirements

- **3.5.2.1.10.2.1 Determine Maximum Number of Timebased Actions**
- **3.5.2.1.10.2.2 Determine Action in Effect**

##### 3.5.2.1.11 Manage I/O Mapping Requirements

###### 3.5.2.1.11.1 Configure I/O Mapping Requirements

- **3.5.2.1.11.1.1 Set Active I/O Map**
- **3.5.2.1.11.1.2 Configure I/O Map Requirements** - Map inputs/outputs to functions

###### 3.5.2.1.11.2 Determine I/O Mapping Requirements

- **3.5.2.1.11.2.1 Retrieve Maximum Number of I/O Maps**
- **3.5.2.1.11.2.2 Retrieve Maximum Number of I/O Map Inputs**
- **3.5.2.1.11.2.3 Retrieve Maximum Number of I/O Map Outputs**
- **3.5.2.1.11.2.4 Retrieve I/O Mapping Activate Conditions**
- **3.5.2.1.11.2.5 Retrieve I/O Mapping Input Functions**
- **3.5.2.1.11.2.6 Retrieve I/O Mapping Output Functions**
- **3.5.2.1.11.2.7 Retrieve I/O Map Input Device Pin Status**
- **3.5.2.1.11.2.8 Retrieve I/O Map Output Device Pin Status**
- **3.5.2.1.11.2.9 Enumerate I/O Mapping Device Pin Requirements**

##### 3.5.2.1.12 Manage Intra-Cabinet Communications Requirements

- **3.5.2.1.12.1 Determine Serial Bus 1 Device Present**

###### 3.5.2.1.12.2 Retrieve Intra-Cabinet Communications Requirements—TS2

- **3.5.2.1.12.2.1 Determine TS2 Port 1 Device Present**
- **3.5.2.1.12.2.2 Determine TS2 Port 1 Frame 40 Enable**

##### 3.5.2.1.13 Manage ADA Support Requirements

###### 3.5.2.1.13.1 Configure ADA Support Requirements

- **3.5.2.1.13.1.1 Configure APS Push Button Minimum Press Time**
- **3.5.2.1.13.1.2 Configure APS Push Button to Phase Association**
- **3.5.2.1.13.1.3 Configure APS Extra Crossing Time**

###### 3.5.2.1.13.2 Determine Maximum Number of Pedestrian Buttons

##### 3.5.2.1.14 Manage Block Object Requirements

###### 3.5.2.1.14.1 Configure Block Object Requirements

- **3.5.2.1.14.1.1 Configure Block Object Get Control Requirements** - Request block data
- **3.5.2.1.14.1.2 Configure Block Data** - Set block data

###### 3.5.2.1.14.2 Retrieve Block Object Requirements

- **3.5.2.1.14.2.1 Monitor Block Object Get Control**
- **3.5.2.1.14.2.2 Monitor Block Data**
- **3.5.2.1.14.2.3 Monitor Block Error Status Requirements**

#### 3.5.2.2 Monitor Signal Operations Requirements

##### 3.5.2.2.1 Determine Controller Health Requirements

###### 3.5.2.2.1.1 Determine Alarm Status Requirements

The standard defines numerous alarm monitoring requirements:

**Traffic Control Alarms:**
- **3.5.2.2.1.1.1 Monitor Preempt Active**
- **3.5.2.2.1.1.2 Monitor Terminal and Facilities Flash**
- **3.5.2.2.1.1.3 Monitor Local Cycle Zero Alarm**
- **3.5.2.2.1.1.4 Monitor Local Override**
- **3.5.2.2.1.1.5 Monitor Coordination Alarm**
- **3.5.2.2.1.1.6 Monitor Detector Fault**
- **3.5.2.2.1.1.7 Monitor Non-Critical Alarm**
- **3.5.2.2.1.1.8 Monitor Stop Time Input Alarm**
- **3.5.2.2.1.1.9 Monitor Cycle Fault Alarm**
- **3.5.2.2.1.1.10 Monitor Coordination Fault**
- **3.5.2.2.1.1.11 Monitor Coordination Fail Alarm**
- **3.5.2.2.1.1.12 Monitor Cycle Fail Alarm**
- **3.5.2.2.1.1.13 Monitor SMU Flash Alarm**
- **3.5.2.2.1.1.14 Monitor Local Flash Alarm**
- **3.5.2.2.1.1.15 Monitor Local Free Alarm**
- **3.5.2.2.1.1.16 Monitor Coordination Active Alarm**
- **3.5.2.2.1.1.17 Monitor Power Restart Alarm**
- **3.5.2.2.1.1.18 Monitor Low Battery Alarm**
- **3.5.2.2.1.1.19 Monitor Response Fault Alarm**
- **3.5.2.2.1.1.20 Monitor External Start**
- **3.5.2.2.1.1.21 Monitor Stop Time Alarm**
- **3.5.2.2.1.1.22 Monitor Offset Transitioning Alarm**
- **3.5.2.2.1.1.23 Monitor Stall Condition**

**System Alarms:**
- **3.5.2.2.1.1.24 Monitor Memory Fault**
- **3.5.2.2.1.1.25 Monitor Process Failure**
- **3.5.2.2.1.1.26 Monitor Communications Timeout**
- **3.5.2.2.1.1.27 Monitor Power Problems**
- **3.5.2.2.1.1.28 Monitor UPS Errors**
- **3.5.2.2.1.1.29 Monitor Scheduler Errors**
- **3.5.2.2.1.1.30 Monitor Signal Monitor Communications Error**
- **3.5.2.2.1.1.31 Monitor Signal Monitor Unit Presence**
- **3.5.2.2.1.1.32 Monitor USB Memory Device**

**Environmental Alarms:**
- **3.5.2.2.1.1.33 Monitor ASC Cabinet Temperature Alarm**
- **3.5.2.2.1.1.34 Monitor ASC Cabinet Humidity Alarm**
- **3.5.2.2.1.1.35 Monitor Clock Failure**

**Preempt and CV Alarms:**
- **3.5.2.2.1.1.36 Monitor Preempt Maximum Presence Alarm**
- **3.5.2.2.1.1.37 Monitor RSU Watchdog Timer**
- **3.5.2.2.1.1.38 Monitor CV Certificate Faults**

###### 3.5.2.2.1.2 Monitor Alarm Group State
Query alarm states by functional groups.

##### 3.5.2.2.2 Retrieve Mode of Operation Requirements

- **3.5.2.2.2.1 Monitor Unit Control Status** - Current operational mode
- **3.5.2.2.2.2 Monitor External Minimum Recall**
- **3.5.2.2.2.3 Monitor Call to Non-Actuated 1**
- **3.5.2.2.2.4 Monitor Call to Non-Actuated 2**
- **3.5.2.2.2.5 Monitor Walk Rest Modifier**
- **3.5.2.2.2.6 Monitor Interconnect**
- **3.5.2.2.2.7 Monitor Dimming Enabled**
- **3.5.2.2.2.8 Monitor Unit Flash Status**

###### 3.5.2.2.2.9 Monitor Current Timing Pattern Requirements

- **3.5.2.2.2.9.1 Monitor Current Pattern Status**
- **3.5.2.2.2.9.2 Monitor Local Free Status**
- **3.5.2.2.2.9.3 Monitor Current Mode of Operation**
- **3.5.2.2.2.9.4 Monitor Programmed Pattern**

###### 3.5.2.2.2.10 Monitor Current Cycle Requirements

- **3.5.2.2.2.10.1 Monitor Coordination Cycle Status**
- **3.5.2.2.2.10.2 Monitor Coordination Synchronization Status**
- **3.5.2.2.2.10.3 Monitor Current Split**
- **3.5.2.2.2.10.4 Monitor Current Offset**

##### 3.5.2.2.3 Monitor Current Signal Indications Requirements

- **3.5.2.2.3.1 Determine Maximum Number of Phase Groups**
- **3.5.2.2.3.2 Monitor Phase Group Reds** - Bit array of red indications
- **3.5.2.2.3.3 Monitor Phase Group Yellows**
- **3.5.2.2.3.4 Monitor Phase Group Greens**
- **3.5.2.2.3.5 Monitor Phase Group Don't Walks**
- **3.5.2.2.3.6 Monitor Phase Group Pedestrian Clearance** - FDW state
- **3.5.2.2.3.7 Monitor Phase Group Walks**
- **3.5.2.2.3.8 Monitor Phase Group Flashing Yellow Arrow**
- **3.5.2.2.3.9 Monitor Phase Group Flashing Red Arrow**

##### 3.5.2.2.4 Monitor Current Phase Requirements

- **3.5.2.2.4.1 Monitor Phase Group Phase Ons** - Active phases
- **3.5.2.2.4.2 Monitor Phase Group Phase Nexts** - Next phases
- **3.5.2.2.4.3 Monitor Phase Group Vehicle Call**
- **3.5.2.2.4.4 Monitor Phase Group Pedestrian Call**
- **3.5.2.2.4.5 Monitor Phase Group Bicycle Call**
- **3.5.2.2.4.6 Monitor Phase Group Transit Call**

##### 3.5.2.2.5 Retrieve Current Ring Requirements

- **3.5.2.2.5.1 Monitor Ring Status** - Ring state
- **3.5.2.2.5.2 Monitor Ring Termination Cause** - Why ring terminated

##### 3.5.2.2.6 Retrieve Current Channel Status Requirements

- **3.5.2.2.6.1 Determine Maximum Number of Channel Status Groups**
- **3.5.2.2.6.2 Monitor Channel Status Group Reds**
- **3.5.2.2.6.3 Monitor Channel Status Group Yellows**
- **3.5.2.2.6.4 Monitor Channel Status Group Greens**

##### 3.5.2.2.7 Retrieve Current Overlap Status Requirements

- **3.5.2.2.7.1 Determine Maximum Number of Overlap Status Groups**
- **3.5.2.2.7.2 Monitor Overlap Status Group Reds**
- **3.5.2.2.7.3 Monitor Overlap Status Group Yellows**
- **3.5.2.2.7.4 Monitor Overlap Status Group Greens**
- **3.5.2.2.7.5 Monitor Overlap Status Group Flashing Yellow Arrows**
- **3.5.2.2.7.6 Monitor Overlap Status Group Flashing Red Arrows**

##### 3.5.2.2.8 Retrieve Current Preempt Status Requirements

- **3.5.2.2.8.1 Monitor Currently Active Preempt**
- **3.5.2.2.8.2 Monitor Current Preempt Inputs**
- **3.5.2.2.8.3 Monitor Current Preempt State** - Entry, dwell, exit, etc.
- **3.5.2.2.8.4 Monitor Current Gate Status** - Railroad gate status

##### 3.5.2.2.9 Retrieve Special Function Outputs Requirements

- **3.5.2.2.9.1 Determine Maximum Number of Special Functions**
- **3.5.2.2.9.2 Monitor Special Function State** - On/off
- **3.5.2.2.9.3 Monitor Special Function Status**
- **3.5.2.2.9.4 Monitor Special Function Control Source**

##### 3.5.2.2.10 Monitor Timebase Action Status Requirements

- **3.5.2.2.10.1 Monitor Timebase Action Status**
- **3.5.2.2.10.2 Monitor Timebase Timing Pattern Status**

##### 3.5.2.2.11 Monitor Intra-Cabinet Communications Requirements

- **3.5.2.2.11.1 Monitor TS2 Port 1 Status**
- **3.5.2.2.11.2 Monitor TS2 Port 1 Fault Frame**
- **3.5.2.2.11.3 Monitor Serial Bus 1 Status**

#### 3.5.2.3 Manage Signal Operations Control Requirements

##### 3.5.2.3.1 Control ASC Function Requirements

- **3.5.2.3.1.1 Control External Minimum Recall**
- **3.5.2.3.1.2 Control Call to Non-Actuated 1**
- **3.5.2.3.1.3 Control Call to Non-Actuated 2**
- **3.5.2.3.1.4 Control Walk Rest Modifier**
- **3.5.2.3.1.5 Control Interconnect**
- **3.5.2.3.1.6 Control Dimming Enabled**
- **3.5.2.3.1.7 Control Disable Remote Commands** - Lock out remote control
- **3.5.2.3.1.8 Acknowledge Local Cycle Zero Alarm**
- **3.5.2.3.1.9 Control Weather-Based Signal Operation Changes**

##### 3.5.2.3.2 Command Timing Pattern Requirements

- **3.5.2.3.2.1 Command System Timing Pattern**
- **3.5.2.3.2.2 Command System Timing Pattern System Reference Point**

##### 3.5.2.3.3 Control Phases Requirements

- **3.5.2.3.3.1 Control Phase Group Phase Omits** - Temporarily skip phases
- **3.5.2.3.3.2 Control Phase Group Pedestrian Omits**
- **3.5.2.3.3.3 Control Phase Group Holds** - Hold on green
- **3.5.2.3.3.4 Control Phase Group Force Offs** - Force to yellow/red
- **3.5.2.3.3.5 Control Phase Group Vehicle Calls** - Place vehicle calls
- **3.5.2.3.3.6 Control Phase Group Pedestrian Calls**
- **3.5.2.3.3.7 Control Phase Group Bicycle Calls**
- **3.5.2.3.3.8 Control Phase Group Transit Calls**

##### 3.5.2.3.4 Control Preempt Requirements

- **3.5.2.3.4.1 Command Preempt Remote Activation** - Remotely activate preempt

##### 3.5.2.3.5 Control Ring Requirements

- **3.5.2.3.5.1 Control Ring Stop Time** - Inhibit ring advance
- **3.5.2.3.5.2 Control Ring Force Offs**
- **3.5.2.3.5.3 Control Ring Maximum 2 Time Settings**
- **3.5.2.3.5.4 Control Ring Maximum 3 Time Settings**
- **3.5.2.3.5.5 Control Ring Maximum Inhibit Settings**
- **3.5.2.3.5.6 Control Ring Pedestrian Recycle Settings**
- **3.5.2.3.5.7 Control Ring Red Rest Settings**
- **3.5.2.3.5.8 Control Ring Red Clearance Omit Settings**
- **3.5.2.3.5.9 Determine Maximum Number of Ring Control Groups**

##### 3.5.2.3.6 Special Functions Control Requirements

- **3.5.2.3.6.1 Activate Special Function**
- **3.5.2.3.6.2 Release Special Function Control**

##### 3.5.2.3.7 Control Frame 40 Requirements

- **3.5.2.3.7.1 Control TS2 Port 1 Frame 40 Messages** - TS2 Type 1 communications

##### 3.5.2.3.8 Activate Action Plan
Command a specific time-of-day action plan.

##### 3.5.2.3.9 Remote Manual Control Requirements

- **3.5.2.3.9.1 Enable Manual Control** - Enter manual control mode
- **3.5.2.3.9.2 Remote Manual Control Advance Command** - Advance to next phase
- **3.5.2.3.9.3 Configure Manual Control Timeout** - Auto-exit after timeout

### 3.5.3 Detector Management Requirements

#### 3.5.3.1 Manage Detector Configuration Requirements

##### 3.5.3.1.1 Configure Detectors Requirements

###### 3.5.3.1.1.1 Configure Vehicle Detectors Requirements

**Basic Configuration:**
- **3.5.3.1.1.1.1 Configure Vehicle Volume Detectors** - Count vehicles
- **3.5.3.1.1.1.2 Configure Vehicle Occupancy Detectors** - Measure presence time
- **3.5.3.1.1.1.3 Configure Vehicle Speed Detectors** - Measure speed
- **3.5.3.1.1.1.4 Configure Vehicle Detection Zone Length**
- **3.5.3.1.1.1.5 Configure Vehicle Travel Mode** - Direction of travel

**Detector Options:**
- **3.5.3.1.1.1.6 Configure Vehicle Detector Yellow Lock Call Enabled**
- **3.5.3.1.1.1.7 Configure Vehicle Detector Red Lock Call Enabled**
- **3.5.3.1.1.1.8 Configure Vehicle Detector Passage Enabled**
- **3.5.3.1.1.1.9 Configure Vehicle Detector Added Initial Time Enabled**
- **3.5.3.1.1.1.10 Configure Vehicle Detector Queue Enabled**
- **3.5.3.1.1.1.11 Configure Vehicle Detector Call Enabled**

**Detector Assignment:**
- **3.5.3.1.1.1.12 Configure Vehicle Detector Call Phase**
- **3.5.3.1.1.1.13 Configure Vehicle Detector Switch Phase** - Conditional phase

**Timing Parameters:**
- **3.5.3.1.1.1.14 Configure Vehicle Detector Delay Time**
- **3.5.3.1.1.1.15 Configure Vehicle Detector Extend Time** - Passage extension
- **3.5.3.1.1.1.16 Configure Vehicle Detector Queue Limit Time**
- **3.5.3.1.1.1.17 Configure Vehicle Detector No Activity Time**
- **3.5.3.1.1.1.18 Configure Vehicle Detector Maximum Presence Time**

**Fault Detection:**
- **3.5.3.1.1.1.19 Configure Vehicle Detector Erratic Counts** - Threshold for fault
- **3.5.3.1.1.1.20 Configure Vehicle Detector Fail Time**

**Speed Measurement:**
- **3.5.3.1.1.1.21 Configure Single Detector Speed Mode**
- **3.5.3.1.1.1.22 Configure Paired Detector** - Speed trap configuration
- **3.5.3.1.1.1.23 Configure Paired Detector Placement**
- **3.5.3.1.1.1.24 Configure Paired Detector Spacing**
- **3.5.3.1.1.1.25 Configure Average Vehicle Length**

###### 3.5.3.1.1.2 Configure Pedestrian Detectors Requirements

- **3.5.3.1.1.2.1 Configure Pedestrian Detector Call Phase**
- **3.5.3.1.1.2.2 Configure Pedestrian Detector No Activity Time**
- **3.5.3.1.1.2.3 Configure Pedestrian Detector Maximum Presence Time**
- **3.5.3.1.1.2.4 Configure Pedestrian Detector Erratic Counts**
- **3.5.3.1.1.2.5 Configure Pedestrian Detector Non-Lock Calls**
- **3.5.3.1.1.2.6 Configure Pedestrian Detector Alternate Pedestrian Timing**
- **3.5.3.1.1.2.7 Configure Pedestrian Detector Type**

##### 3.5.3.1.2 Retrieve Detector Configuration Requirements

###### 3.5.3.1.2.1 Retrieve Vehicle Detectors Requirements

- **3.5.3.1.2.1.1 Determine Maximum Number of Vehicle Detectors**

###### 3.5.3.1.2.2 Retrieve Pedestrian Detectors Requirements

- **3.5.3.1.2.2.1 Determine Maximum Number of Pedestrian Detectors**

#### 3.5.3.2 Retrieve Detector Status Requirements

##### 3.5.3.2.1 Monitor Vehicle Detector Status Groups Requirements

- **3.5.3.2.1.1 Determine Maximum Number of Vehicle Detector Status Groups**
- **3.5.3.2.1.2 Monitor Vehicle Detector Status Group Active** - Currently detecting
- **3.5.3.2.1.3 Monitor Vehicle Detector Status Group Alarm Status** - Fault conditions

##### 3.5.3.2.2 Monitor Pedestrian Detector Status Requirements

- **3.5.3.2.2.1 Determine Maximum Number of Pedestrian Detector Status Groups**
- **3.5.3.2.2.2 Monitor Pedestrian Detector Status Active**
- **3.5.3.2.2.3 Monitor Pedestrian Detector Alarm Status**

#### 3.5.3.3 Retrieve Detector Health Requirements

##### 3.5.3.3.1 Retrieve Vehicle Detector Health Requirements

- **3.5.3.3.1.1 Monitor Vehicle Detector No Activity Fault**
- **3.5.3.3.1.2 Monitor Vehicle Detector Max Presence Fault** - Stuck-on detector
- **3.5.3.3.1.3 Monitor Vehicle Detector Erratic Output Fault** - Chattering
- **3.5.3.3.1.4 Monitor Vehicle Detector Communications Fault**
- **3.5.3.3.1.5 Monitor Vehicle Detector Configuration Fault**

##### 3.5.3.3.2 Retrieve Vehicle Loop Detector Requirements

Inductive loop-specific faults:
- **3.5.3.3.2.1 Monitor Loop Vehicle Detector Watchdog Failure**
- **3.5.3.3.2.2 Monitor Loop Vehicle Detector Open Loop Failure**
- **3.5.3.3.2.3 Monitor Loop Vehicle Detector Shorted Loop Fault**
- **3.5.3.3.2.4 Monitor Loop Vehicle Detector Excessive Change Fault**

##### 3.5.3.3.3 Retrieve Pedestrian Detector Health Requirements

- **3.5.3.3.3.1 Monitor Pedestrian Detector No Activity Fault**
- **3.5.3.3.3.2 Monitor Pedestrian Detector Max Presence Fault**
- **3.5.3.3.3.3 Monitor Pedestrian Detector Erratic Output Fault**
- **3.5.3.3.3.4 Monitor Pedestrian Detector Communications Fault**
- **3.5.3.3.3.5 Monitor Pedestrian Detector Configuration Fault**

#### 3.5.3.4 Control Detector Requirements

- **3.5.3.4.1 Control Vehicle Detector Reset** - Reset fault status
- **3.5.3.4.2 Control Pedestrian Detector Reset**
- **3.5.3.4.3 Control Vehicle Detector Actuation** - Simulate actuation
- **3.5.3.4.4 Control Pedestrian Detector Actuation**

#### 3.5.3.5 Manage Vehicle Detector Data Collection Requirements

##### 3.5.3.5.1 Configure Vehicle Detector Data Collection Requirements

###### 3.5.3.5.1.1 Configure Detector Data Collection Sample Period Requirements

- **3.5.3.5.1.1.1 Configure Detector Data Sample Period** - Collection interval
- **3.5.3.5.1.1.2 Configure Detector Data Sample Period—Version 3** - Enhanced timing

##### 3.5.3.5.2 Retrieve Vehicle Detector Data Collection Requirements

###### 3.5.3.5.2.1 Retrieve Detector Data Collection Sample Period Requirements

- **3.5.3.5.2.1.1 Monitor Detector Data Sequence** - Data version number
- **3.5.3.5.2.1.2 Determine Detector Data Active Detectors** - Bit array
- **3.5.3.5.2.1.3 Monitor Volume Data** - Vehicle counts
- **3.5.3.5.2.1.4 Monitor Average Speed** - Mean speed per detector
- **3.5.3.5.2.1.5 Monitor Occupancy Data** - Percent occupancy
- **3.5.3.5.2.1.6 Monitor Vehicle Detector Data Alarms** - Data quality flags
- **3.5.3.5.2.1.7 Monitor Detector Data Sample Time** - Timestamp
- **3.5.3.5.2.1.8 Monitor Detector Data Sample Duration** - Actual sample length

#### 3.5.3.6 Manage Pedestrian Detector Data Collection Requirements

##### 3.5.3.6.1 Configure Pedestrian Detector Data Collection Requirements

- **3.5.3.6.1.1 Configure Pedestrian Data Collection Sample Period**

##### 3.5.3.6.2 Retrieve Pedestrian Detector Data Collection Requirements

- **3.5.3.6.2.1 Monitor Pedestrian Counts** - Total button presses
- **3.5.3.6.2.2 Monitor Pedestrian Detector Actuations** - Actuation events
- **3.5.3.6.2.3 Monitor Pedestrian Detector Data Alarms**
- **3.5.3.6.2.4 Monitor Pedestrian Services** - Ped phases served
- **3.5.3.6.2.5 Determine Pedestrian Detector Data Active Detectors**
- **3.5.3.6.2.6 Monitor Pedestrian Detector Data Sample Time**
- **3.5.3.6.2.7 Monitor Pedestrian Detector Data Sample Duration**
- **3.5.3.6.2.8 Monitor Pedestrian Detector Data Sequence**

### 3.5.4 Connected Vehicles Interface Management

This section defines requirements for exchanging data between the ASC and Connected Vehicle (CV) systems, including Roadside Units (RSU) for V2I communications.

#### 3.5.4.1 Manage Management Station—ASC Interface Requirements

##### 3.5.4.1.1 Manage RSU Interface Requirements

- **3.5.4.1.1.1 Configure RSU Interface** - Configure RSU connection
- **3.5.4.1.1.2 Configure Logical RSU Ports** - Map logical to physical ports
- **3.5.4.1.1.3 Configure RSU Interface Polling Period** - Data exchange frequency

##### 3.5.4.1.2 Manage RSU Interface Watchdog Requirements

- **3.5.4.1.2.1 Configure RSU Interface Watchdog** - Detect RSU failures
- **3.5.4.1.2.2 Monitor RSU Interface Watchdog Timer**

##### 3.5.4.1.3 Manage Signal Phase and Timing Requirements

###### 3.5.4.1.3.1 Enable Signal Phase and Timing Data
Enable SPaT message generation.

###### 3.5.4.1.3.2 Retrieve Intersection Identifier [Deprecated]
###### 3.5.4.1.3.3 Retrieve Signal Phase and Timing Time Point [Deprecated]
###### 3.5.4.1.3.4 Retrieve Signal Phase and Timing Generation Time
Timestamp of SPaT data generation.

###### 3.5.4.1.3.5 Retrieve Signal Phase and Timing Intersection Status [Deprecated]

###### 3.5.4.1.3.6 Exchange Movement Status Requirements

- **3.5.4.1.3.6.1 Monitor Movement State [Deprecated]**
- **3.5.4.1.3.6.2 Retrieve Movement Timing Requirements** - Min/max/likely times
- **3.5.4.1.3.6.3 Configure Movement Assistance Requirements** - Queue/storage warnings
- **3.5.4.1.3.6.4 Retrieve Movement Assistance Requirements**
- **3.5.4.1.3.6.5 Manage Advisory Speed Requirements** - Green wave speed
- **3.5.4.1.3.6.6 Monitor Movement Status [Deprecated]**
- **3.5.4.1.3.6.7 Monitor Lane Connection Maneuver Status [Deprecated]**
- **3.5.4.1.3.6.8 Monitor Movement State V2** - Current signal state
- **3.5.4.1.3.6.9 Monitor Next Movement State** - Next expected state
- **3.5.4.1.3.6.10 Monitor Movement Status V2** - Enhanced status

###### 3.5.4.1.3.7 Manage Enabled Lane Requirements

- **3.5.4.1.3.7.1 Configure Concurrent Enabled Lanes** - Lanes open concurrently
- **3.5.4.1.3.7.2 Configure Enabled Lanes for a Pattern [Deprecated]**
- **3.5.4.1.3.7.3 Command Enabled Lanes [Deprecated]**
- **3.5.4.1.3.7.4 Configure Enabled Lanes by Time of Day**
- **3.5.4.1.3.7.5 Determine Lanes Enabled** - Currently active lanes
- **3.5.4.1.3.7.6 Command Enabled Lanes V2**

###### 3.5.4.1.3.8 Configure Movement Type [Deprecated]
###### 3.5.4.1.3.9 Configure Lane Connection Type [Deprecated]
###### 3.5.4.1.3.10 Enable Signal Phase and Timing Data Exchange

###### 3.5.4.1.3.11 Configure Road Authority
Identify operating agency.

###### 3.5.4.1.3.12 Retrieve Signal Phase and Timing Intersection Status Requirements

- **3.5.4.1.3.12.1 Monitor Manual Control Indication**
- **3.5.4.1.3.12.2 Monitor Stop Indication** - Stop time active
- **3.5.4.1.3.12.3 Monitor Failure Flash Indication**
- **3.5.4.1.3.12.4 Monitor Preemption Operation Indication**
- **3.5.4.1.3.12.5 Monitor Priority Operation Indication** - TSP active
- **3.5.4.1.3.12.6 Monitor Fixed Time Control Indication** - Pre-timed mode
- **3.5.4.1.3.12.7 Monitor Non-Fixed Time Control Indication** - Actuated mode
- **3.5.4.1.3.12.8 Monitor Standby Operation Indication** - Dark mode
- **3.5.4.1.3.12.9 Monitor Controller Failure**
- **3.5.4.1.3.12.10 Monitor MAP Message Validity**
- **3.5.4.1.3.12.11 Monitor SPaT Data Validity**

###### 3.5.4.1.3.13 Mark SPaT Invalid—Controller
Invalidate SPaT due to controller fault.

###### 3.5.4.1.3.14 Mark SPaT Invalid—Port
Invalidate SPaT for specific RSU port.

###### 3.5.4.1.3.15 Mark MAP Message Invalid—Controller
###### 3.5.4.1.3.16 Mark MAP Message Invalid—Port

###### 3.5.4.1.3.17 Manage Signal Group Requirements

Signal groups map ASC phases/overlaps to SAE J2735 signal groups:

- **3.5.4.1.3.17.1 Determine Maximum Number of Signal Groups**
- **3.5.4.1.3.17.2 Configure Signal Group Intersection Mapping**
- **3.5.4.1.3.17.3 Configure Signal Group Control Source** - Phase or overlap
- **3.5.4.1.3.17.4 Configure Signal Group Indication Types** - Ball/arrow/ped
- **3.5.4.1.3.17.5 Configure Signal Group Permissive Control Source**
- **3.5.4.1.3.17.6 Configure Signal Group Lanes** - Lanes controlled
- **3.5.4.1.3.17.7 Determine Maximum Number of Signal State Entries**
- **3.5.4.1.3.17.8 Configure Signal State Parameters**

###### 3.5.4.1.3.18 Retrieve Signal Phase and Timing Time Point V2
Enhanced timestamp with millisecond precision.

#### 3.5.4.2 Manage Management Station – CV Roadside Process Interface Requirements [Deprecated]

This section contains deprecated requirements for the MAP message configuration interface. Modern implementations use SAE J2735 MAP messages configured through other means.

##### 3.5.4.2.1 Manage Roadway Geometrics Information Requirements [Deprecated]

Requirements for configuring intersection geometry, lanes, node points, and overlays (deprecated in favor of external MAP tools).

#### 3.5.4.3 ASC – CV Roadside Process Interface Requirements

##### 3.5.4.3.1 Exchange Current and Next Movement Information Requirements

###### 3.5.4.3.1.1 Provide Current and Next Movement Information Requirements

ASC provides SPaT data to RSU:
- **3.5.4.3.1.1.1 Provide Intersection Identifier [Deprecated]**
- **3.5.4.3.1.1.2 Provide Signal Phase and Timing Intersection Status [Deprecated]**
- **3.5.4.3.1.1.3 Provide Movement Status Requirements** - Per-movement state/timing
- **3.5.4.3.1.1.4 Provide Movement Assistance Requirements** - Queue/storage data
- **3.5.4.3.1.1.5 Provide Advisory Speed Requirements**
- **3.5.4.3.1.1.6 Provide Intersection Channel Assignment [Deprecated]**
- **3.5.4.3.1.1.7 Provide Road Authority ID**
- **3.5.4.3.1.1.8 Provide Signal Phase and Timing Intersection Status V2**
- **3.5.4.3.1.1.9 Provide SPaT Information to a CV Roadside Process**

###### 3.5.4.3.1.2 Retrieve Current and Next Movement Information Requirements [Deprecated]

##### 3.5.4.3.2 Exchange Next Occurrence of a Movement Requirements

- **3.5.4.3.2.1 Provide Movement Next Occurrence [Deprecated]**
- **3.5.4.3.2.2 Retrieve Movement Next Occurrence [Deprecated]**

##### 3.5.4.3.3 Exchange Presence of Connected Device Requirements

###### 3.5.4.3.3.1 Retrieve Connected Devices Presence Information Requirements

- **3.5.4.3.3.1.1 Retrieve Actuation Report (ASC)** - BSM-based actuations
- **3.5.4.3.3.1.2 Retrieve Detection Report (ASC)** - BSM-based detection data

##### 3.5.4.3.4 Exchange Roadway Geometry Plan Information Requirements

- **3.5.4.3.4.1 Retrieve Roadway Geometry Plan Requirements**
- **3.5.4.3.4.2 Provide Roadway Geometry Plan Requirements [Deprecated]**
- **3.5.4.3.4.3 Confirm MAP Plan Compatibility** - Verify MAP/SPaT alignment

### 3.5.5 Backward Compatibility Requirements

#### 3.5.5.1 NTCIP 1202 v01—Configure Special Function State
Support for legacy special function control method.

## 3.6 Supplemental Non-Communications Requirements

### 3.6.1 Response Time for Requests
ASC shall respond to SNMP requests within specified time limits (typically 1-5 seconds).

### 3.6.2 Condition-Based Maximum Transmission Start Time
Requirements for timely transmission of event-driven data.

### 3.6.3 Signal Phase and Timing Data Performance Requirements

#### 3.6.3.1 SPaT Maximum Transmission Start Time
Maximum delay from signal state change to SPaT transmission start.

#### 3.6.3.2 Movement Time Point Minimum Transmission Rate
Minimum frequency for broadcasting updated time predictions.

#### 3.6.3.3 SPaT-data Request Transmission Rate [Deprecated]
#### 3.6.3.4 Condition-Based SPaT Maximum Transmission Start Time [Deprecated]
#### 3.6.3.5 SPaT Latency [Deprecated]

#### 3.6.3.6 SPaT Maximum Transmission Rate
Maximum frequency to avoid network flooding.

#### 3.6.3.7 SPaT Time Accuracy
Required accuracy for time predictions (typically ±0.1 seconds).

---

## Summary

Section 3 defines comprehensive functional requirements organized into the following major categories:

1. **Protocol Requirements List (PRL)** - Standardized conformance table
2. **Architectural Requirements** - SNMP communications, logging, access control
3. **ASC Configuration Management** - Location, communications, environment, power, clock
4. **Signal Operations Management** - Phases, coordination, patterns, splits, rings, channels, overlaps, preempts, scheduling
5. **Detector Management** - Vehicle and pedestrian detector configuration, status, health, and data collection
6. **Connected Vehicles Interface** - RSU interface, SPaT/MAP message generation, CV detection zones
7. **Performance Requirements** - Response times, SPaT latency, and data accuracy

Each requirement is identified with a hierarchical numbering system and includes requirement IDs that map to specific MIB objects defined in Section 5.
