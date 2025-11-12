# Section 4: Dialogs [Normative]

## 4.1 Tutorial [Informative]

This section defines the standardized dialogs used for communication between management stations and ASCs. Dialogs represent sequences of message exchanges that accomplish specific tasks.

## 4.2 Specified Dialogs

### 4.2.1 Get Block Data
Dialog for retrieving pre-defined blocks of data from the ASC. Block data provides efficient transfer of grouped configuration and status information.

### 4.2.2 Set Complex Configuration Parameters (called 'P2' Objects)
Dialog for setting complex configuration parameters that require special handling or validation.

### 4.2.3 Set Block Data
Dialog for uploading pre-defined blocks of data to the ASC. Enables efficient bulk configuration updates.

### 4.2.4 Setup, Programming, and Processing of I/O Mapping
Dialog for configuring the input/output mapping in the ASC, allowing reassignment of physical I/O to logical functions.

### 4.2.5 Making an I/O Map Active
Dialog for activating a previously configured I/O mapping, putting it into operational use.

### 4.2.6 Configure Speed Limits for a Node Point [Deprecated]
Legacy dialog for configuring speed limits. This dialog has been deprecated.

### 4.2.7 Enable Collection of Connected Data [Deprecated]
Legacy dialog for enabling connected vehicle data collection. This dialog has been deprecated.

### 4.2.8 Retrieve Connected Device Detector Zone—Geographic [Deprecated]
Legacy dialog for retrieving geographic detector zone information. This dialog has been deprecated.

### 4.2.9 Configure Enabled Lanes [Deprecated]
Legacy dialog for configuring enabled lanes. This dialog has been deprecated.

### 4.2.10 Provide Detection Reports to an ASC
Dialog for external detection systems to provide detection reports to the ASC. Enables integration of advanced detection systems.

### 4.2.11 Activating a MAP Plan [Deprecated]
Legacy dialog for activating MAP plans. This dialog has been deprecated.

### 4.2.12 Confirm MAP Compatibility
Dialog for confirming that a MAP (geographic intersection description) is compatible with the ASC configuration.

### 4.2.13 Configure Enabled Lanes V2
Updated dialog for configuring which lanes are enabled in the MAP for SPaT broadcasting.

## 4.3 State-Transition Diagrams

### 4.3.1 Data Parameter Types
NTCIP 1202 v03 defines different types of data parameters:
- **Configuration Parameters**: Define how the ASC operates
- **Status Parameters**: Report current state of the ASC
- **Control Parameters**: Allow external control of ASC operations

### 4.3.2 Consistency Checks

#### 4.3.2.1 Consistency Check Rules
When configuration data is downloaded to an ASC, the ASC shall perform consistency checks to ensure:
- Data values are within valid ranges
- Required dependencies between parameters are satisfied
- Configuration is safe and operationally valid

The ASC shall report any consistency check failures with specific error codes indicating the nature and location of the error.

### 4.3.3 Non-Sequential Time Change
Defines how the ASC handles situations where the system time changes non-sequentially (e.g., due to daylight saving time or NTP synchronization).

## 4.4 Class Diagrams

Class diagrams show the relationships between different object types defined in the MIB (Management Information Base).

## 4.5 Object Types

Object types define the structure and characteristics of data elements that can be accessed via NTCIP protocols. Each object type specifies:
- Data type (integer, string, bit field, etc.)
- Valid range or enumeration values
- Access permissions (read-only, read-write)
- Units of measurement
- Semantic meaning

---

*© 2023 AASHTO / ITE / NEMA*
