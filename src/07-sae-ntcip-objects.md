# Section 7: SAE/NTCIP Object Definitions

## 7.1 MIB Header

This section defines objects used for connected vehicle (CV) integration, specifically for Signal Phase and Timing (SPaT) and MAP message generation.

## 7.2 Signal Phase and Timing (SPaT)

### 7.2.1 Intersection Status
Reports the current operational status of the intersection for inclusion in SPaT messages.

### 7.2.2 Maximum SPaT Speed Advisories
Defines the maximum number of speed advisory entries that can be included in SPaT messages.

### 7.2.3 SPaT Speed Advisories Table

Contains speed advisory information for specific movements:

#### 7.2.3.1 SPaT Speed Advisory Index
Unique identifier for each speed advisory entry.

#### 7.2.3.2 SPaT Movement Advisory Speed Type
Type of speed advisory (e.g., maximum, minimum, recommended).

#### 7.2.3.3 SPaT Movement Advisory Speed Advice
The actual speed value being advised (in units per second).

#### 7.2.3.4 SPaT Movement Advisory Speed Zone
Geographic zone where the speed advisory applies.

#### 7.2.3.5 SPaT Movement Advisory Speed Restriction Class
Vehicle class to which the restriction applies.

#### 7.2.3.6 SPaT Movement Advisory Speed Confidence
Confidence level in the speed advisory.

### 7.2.4 Maximum SPaT Movement Maneuvers
Maximum number of movement maneuvers (signal groups) supported.

### 7.2.5 SPaT Movement Maneuvers Table

Defines the maneuvers (turning movements) at the intersection:

#### 7.2.5.1 SPaT Movement Maneuver Number
Unique identifier for the maneuver.

#### 7.2.5.2 SPaT Movement Maneuver Identifier
SAE J2735 movement identifier.

#### 7.2.5.3 SPaT Movement Maneuver State
Current state of the movement (e.g., stop-And-Remain, protected-Movement-Allowed).

#### 7.2.5.4 SPaT Movement Queue
Queue status information for the movement.

#### 7.2.5.5 SPaT Movement Storage
Available storage length for queuing vehicles.

#### 7.2.5.6 SPaT Movement Assist Status
Status of pedestrian assistance features.

#### 7.2.5.7 SPaT Movement Queue Detector
Detector used for queue detection.

#### 7.2.5.8 SPaT Movement Pedestrian Presence
Indicates pedestrian presence for this movement.

#### 7.2.5.9 SPaT Movement Bicycle Presence
Indicates bicycle presence for this movement.

#### 7.2.5.10 SPaT Movement Type
Type of movement (vehicle, pedestrian, bicycle, etc.).

#### 7.2.5.11 SPaT Movement Included Movements
Other movements included in this signal group.

### 7.2.6 SPaT Enabled Lanes Status
Reports which lanes are currently enabled in the SPaT message.

### 7.2.7 SPaT Signal Status Table

Provides timing information for each signal state:

#### 7.2.7.1 SPaT Event State
The signal state event (e.g., protected-clearance, stop-And-Remain).

#### 7.2.7.2 SPaT Signal State Minimum End Time
Minimum time until this state will end (in tenths of seconds).

#### 7.2.7.3 SPaT Signal State Maximum End Time
Maximum time until this state will end (in tenths of seconds).

#### 7.2.7.4 SPaT Signal State Likely Time
Most likely time until state change (in tenths of seconds).

#### 7.2.7.5 SPaT Signal State Time Confidence
Confidence in the timing prediction.

#### 7.2.7.6 SPaT Signal Next Tick
Timestamp for the next update tick.

### 7.2.8 SPaT Signal Status Block
Block data format for efficient retrieval of signal status information.

### 7.2.9 SPaT Movement Maneuver Status Block
Block data format for efficient retrieval of movement maneuver status.

### 7.2.10 Intersection Status V2
Enhanced version of intersection status with additional fields.

### 7.2.11 Maximum Movement Events
Maximum number of movement event states supported per movement.

### 7.2.12 SPaT Signal Status Table V2

Enhanced signal status table supporting multiple events per movement:

#### 7.2.12.1 Movement Event Number
Index of the event in the event sequence.

#### 7.2.12.2 SPaT Event State
The signal state event.

#### 7.2.12.3 SPaT Signal State Minimum End Time V2
Minimum time until state end.

#### 7.2.12.4 SPaT Signal State Maximum End Time V2
Maximum time until state end.

#### 7.2.12.5 SPaT Signal State Likely Time V2
Most likely time until state change.

#### 7.2.12.6 SPaT Signal State Time Confidence
Confidence in the timing.

#### 7.2.12.7 SPaT Signal Next Tick V2
Next update timestamp.

#### 7.2.12.8 SPaT Signal Start Tick
Timestamp when this event state started.

### 7.2.13 Maximum SPaT Speed Advisories
Maximum speed advisories for V2 tables.

### 7.2.14 SPaT Speed Advisories Table 2

Enhanced speed advisory table:

#### 7.2.14.1 SPaT Speed Advisory Index 2
Advisory entry index.

#### 7.2.14.2 SPaT Advisory Signal Group 2
Signal group this advisory applies to.

#### 7.2.14.3 SPaT Movement Advisory Speed Type 2
Type of speed advice.

#### 7.2.14.4 SPaT Movement Advisory Speed Advice 2
Speed value being advised.

#### 7.2.14.5 SPaT Movement Advisory Speed Zone 2
Geographic zone for the advisory.

#### 7.2.14.6 SPaT Movement Advisory Speed Restriction Class 2
Vehicle class restriction.

### 7.2.15 Maximum SPaT Movement Maneuvers
Maximum maneuvers for V2 tables.

### 7.2.16 SPaT Movement Maneuvers Table V2

Enhanced movement maneuvers table:

#### 7.2.16.1 SPaT Movement Maneuver Number V2
Maneuver identifier.

#### 7.2.16.2 SPaT Movement Maneuver Signal Group
Signal group identifier per SAE J2735.

#### 7.2.16.3 SPaT Movement Queue V2
Queue status.

#### 7.2.16.4 SPaT Movement Assist Status V2
Pedestrian assist status.

#### 7.2.16.5 SPaT Movement Queue Detector V2
Queue detection status.

#### 7.2.16.6 SPaT Movement Pedestrian Presence V2
Pedestrian detection status.

#### 7.2.16.7 SPaT Movement Bicycle Presence V2
Bicycle detection status.

### 7.2.17 Road Authority Identifier
Identifier for the road authority managing the intersection.

### 7.2.18 SPaT Signal Status Block V2
Enhanced block data format for signal status.

## 7.3 MAP Data

Geographic description of the intersection for MAP message generation.

### 7.3.1 MAP Message Count
Counter incremented each time MAP message content changes.

### 7.3.2 MAP Message Time
Timestamp of the last MAP message update.

### 7.3.3 Maximum Number of Lanes
Maximum number of lanes that can be defined.

### 7.3.4 Intersection Lane Table

Defines each lane at the intersection:

#### 7.3.4.1 Lane Index
Unique lane index.

#### 7.3.4.2 Lane Intersection
Intersection this lane belongs to.

#### 7.3.4.3 Lane Number
Lane identifier per SAE J2735.

#### 7.3.4.4 Lane Name
Descriptive name for the lane.

#### 7.3.4.5 Lane Direction
Compass direction of the lane.

#### 7.3.4.6 Lane Sharing
How the lane is shared between modes.

#### 7.3.4.7 Lane Type
Type of lane (vehicle, crosswalk, etc.).

#### 7.3.4.8 Lane Attribute
Attributes of the lane (e.g., bike lane, parking).

#### 7.3.4.9 Lane Maneuver
Allowed maneuvers from this lane.

#### 7.3.4.10 Lane Overlay
Overlay types for the lane.

#### 7.3.4.11 Lane Ingress
Ingress approach identifier.

#### 7.3.4.12 Lane Egress
Egress approach identifier.

#### 7.3.4.13 MAP Lane CRC
CRC checksum for lane data integrity.

### 7.3.5 Maximum Number of Intersections
Maximum intersections in the MAP.

### 7.3.6 MAP Intersection Table

Defines each intersection:

#### 7.3.6.1 MAP Intersection Index
Intersection index.

#### 7.3.6.2 MAP Intersection Identifier
Unique intersection ID.

#### 7.3.6.3 MAP Intersection Name
Descriptive intersection name.

#### 7.3.6.4 MAP Authority Identifier
Road authority identifier.

#### 7.3.6.5 MAP Intersection Latitude
Latitude of reference point.

#### 7.3.6.6 MAP Intersection Longitude
Longitude of reference point.

#### 7.3.6.7 MAP Intersection Elevation
Elevation of reference point.

#### 7.3.6.8 MAP Intersection Default Width
Default lane width for unmarked lanes.

#### 7.3.6.9 MAP Intersection Message Count
Version counter for this intersection's MAP data.

### 7.3.7 Maximum Number of Node Points
Maximum node points per lane.

### 7.3.8 Node Point Table

Defines geometric points along lanes:
- Node Point X/Y coordinates
- Node Point Attributes
- Width, Elevation, Angle
- Crown point information
- Speed limits

### 7.3.9 Maximum Computed Lane
Maximum number of computed (derived) lanes.

### 7.3.10 Intersection Computed Lane Table
Lanes computed from other lanes using offsets and scaling.

### 7.3.11 Maximum Lane Connections
Maximum egress lane connections.

### 7.3.12 Lane Connection Table
Defines connections between ingress and egress lanes, including maneuvers and restrictions.

### 7.3.13 Maximum Number of Speed Limits
Maximum speed limit entries per node.

### 7.3.14 Intersection Speed Limit Table
Speed limits for different vehicle classes and conditions.

### 7.3.15 Maximum User Types
Maximum user/vehicle type definitions.

### 7.3.16 Intersection User Types Table
Defines vehicle classes using SAE J2735 classifications.

### 7.3.17 Maximum MAP Plans
Maximum number of MAP plan configurations.

### 7.3.18 MAP Plan Table

Defines MAP plans (different geometric configurations):
- MAP Plan Lanes (which lanes are active)
- MAP Plan CRC (data integrity)
- MAP Plan Layer Type and Identifier
- MAP Plan Metadata (method, agency, date, geoid)

---

*© 2023 AASHTO / ITE / NEMA*
