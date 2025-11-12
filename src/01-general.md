# Section 1: General [Informative]

## 1.1 Scope

NTCIP 1202 v03 specifies the logical interface between an Actuated Signal Controller (ASC) and the host systems that control them; and the logical interface with a connected vehicle roadside process (such as a roadside unit (RSU)) that interfaces with other devices in a connected vehicle environment. NTCIP 1202 v03 describes the supported ASC functionality in terms of user needs and requirements; however, the nature of the interfaces is determined in part by the operational nature of the devices being controlled, and therefore NTCIP 1202 v03 touches on such operational issues on occasion.

Prior to the development of NTCIP 1202, there were no standards defining how ASCs communicate with host systems. As a result, each manufacturer has developed its own protocol to meet its own particular needs. This approach has resulted in systems that are not interchangeable or interoperable. If an agency wishes to use either a central management system or additional ASC from a different vendor, the agency encounters significant systems integration challenges, requiring additional resources to address. These additional resource requirements inhibit information sharing within and between various potential users of the data and prevent vendor independence. Without manufacturer independence, resource requirements further increase because of a lack of a competitive market.

These problems have not been limited to traffic signal controllers. Many other devices also need to exchange information. In surface transportation, examples include dynamic message signs, bus priority sensors, weather, environmental monitoring, etc.

To address these problems, NTCIP is developing a family of open standards for communications between field devices and central management systems. NTCIP 1202 v03 is part of that larger family and is designed to define an interoperable and interchangeable interface between a transportation management system and an ASC, while still allowing for extensions beyond NTCIP 1202 v03 to allow for new functions as needed; and between an ASC and a connected vehicle roadside process, generally in the form of an RSU. This approach is expected to support the deployment of ASC from one or more vendors in a consistent and resource-efficient way.

NTCIP 1202 v03 standardizes the communications interface by identifying the various operational needs of the users (Section 2) and subsequently identifying the necessary requirements (Section 3) that support each need. NTCIP 1202 v03 then defines the NTCIP standardized communications interface used to fulfill these requirements by identifying the dialogs (Section 4) and related data concepts (Section 5) that support each requirement. Traceability among the various sections is defined by the Protocol Requirements List (Section 3.3) and the Requirements Traceability Matrix (Annex A). Conformance requirements for NTCIP 1202 v03 are provided in Section 3.3. NTCIP 1202 v03 only addresses a subset of the requirements needed for procurement. It does not address requirements related to the performance of the traffic detectors (e.g., accuracy, the supported detection range, the time it takes to detect conditions), hardware components, mounting details, etc.

Previous versions of NTCIP 1202 addressed only Actuated Traffic Signal Controllers (ASC) that employ vehicle or pedestrian detectors to activate a particular phase—the scope did not include pre-timed controllers or fixed-time signal controllers that cycle through phases regardless of the number of vehicles or pedestrians present. ASCs included both fully actuated traffic signals, where all phases are actuated, and phases are skipped if no vehicles or pedestrians are detected, as well as semi-actuated traffic signals, where at least one phase is guaranteed to be served regardless of whether pedestrians or vehicles are detected. For NTCIP 1202 v03 purposes, controllers that allow different phases to be active (or skipped) at any point in time phase are known as phase-based controllers.

Beginning with NTCIP 1202 v03, the scope was expanded to standardize the communications interface between an ASC and a Roadside Unit (RSU). An RSU is any connected vehicle field device that is used to broadcast messages to, and receive messages from, nearby vehicles using Vehicle-to-Everything (V2X) communications. V2X communications include Dedicated Short Range Communications (DSRC) and Cellular Vehicle-to-Everything (C-V2X).

An implementation of NTCIP 1202 v03 requires lower-level services to structure, encode, and exchange the data concepts defined by NTCIP 1202 v03. NTCIP 1202 v03 assumes that the data concepts are exchanged by one of the protocols defined in NTCIP 2301 v02.

## 1.2 References

### 1.2.1 Normative References

Normative references contain provisions that, through reference in this text, constitute provisions of NTCIP 1202 v03. Other references in NTCIP 1202 v03 might provide a complete understanding or provide additional information. At the time of publication, the editions indicated were valid. All standards are subject to revision, and parties to agreements based on NTCIP 1202 v03 are encouraged to investigate the possibility of applying the most recent editions of the standards listed.

| Identifier | Title |
|------------|-------|
| NTCIP 1103 v03 | Transportation Management Protocols (TMP), AASHTO / ITE / NEMA, published December 2016 |
| NTCIP 1201 v03 | Global Object (GO) Definitions, AASHTO / ITE / NEMA, published March 2011 |
| NTCIP 1204 v04 | Environmental Sensor Station Interface Standard, AASHTO / ITE / NEMA, published September 2014 (with errata) |
| NTCIP 2103 v02 | Point-to-Point Protocol over RS-232 Subnetwork Profile, AASHTO / ITE / NEMA, published December 2008 |
| NTCIP 2301 v02 | Simple Transportation Management Framework (STMF) Application Profile (AP) (AP-STMF), AASHTO / ITE / NEMA, published July 2010 |
| NTCIP 8004 v02 | Structure and Identification of Management Information (SMI), AASHTO / ITE / NEMA, published June 2010 |
| IETF RFC 1628 | UPS Management Information Base, Published May 1994 |
| SAE J2735 | V2X Communications Message Set Dictionary, SAE International, published November 2022 |

### 1.2.2 Other References

The following documents and standards may provide the reader with a better understanding of the entire protocol and the relations between all parts of the protocol. However, these documents do not contain direct provisions that are required by NTCIP 1202 v03. At the time of publication, the editions indicated were valid. All standards are subject to revision, and parties to agreements based on NTCIP 1202 v03 are encouraged to investigate the possibility of applying the most recent editions of the standard listed.

| Identifier | Title |
|------------|-------|
| ATC 5301 v02.02 | Advanced Transportation Controller (ATC) Cabinet Standard Version 02, v02.02, AASHTO / ITE / NEMA, published March 18, 2019 |
| Caltrans TEES 2020 | Caltrans Transportation Electrical Equipment Specifications (TEES), 2020 |
| CTI 4001 | Connected Transportation Interoperability 4001 - Roadside Unit (RSU) Standard, September 2022, v01.01. https://www.ite.org/technical-resources/standards/rsu-standardization/ |
| CTI 4501 | Connected Transportation Interoperability 4501 – Connected Intersections (CI) Implementation Guide, June 2022, v01.01. https://www.ite.org/technical-resources/standards/connected-intersections/ |
| DSRC Roadside Unit (RSU) Specifications Document v4.1 | DSRC Roadside Unit (RSU) Specifications Document v4.1, USDOT, Saxton Transportation Operations Laboratory, Submitted October 31, 2016, Version 1 |
| IAB 16 | (RFC 1155) Structure and Identification of Management Information for TCP/IP-based Internets, M. Rose, K. McCloghrie, May 1990, (RFC 1212) Concise MIB Definitions, M. Rose and K. McCloghrie, March 1991 |
| IEEE 100-2000 | The Authoritative Dictionary of IEEE Standards Terms, 2000 |
| Indiana Traffic Signal Hi Resolution Data Logger Enumerations | J. Sturdevant, T. Overman, E. Raamot, R. Deer, D. Miller, D. Bullock, C. Day, T. Brennan Jr., H. Li, A. Hainen, and S. Remias, Indiana Department of Transportation and Purdue University, 2012. http://docs.lib.purdue.edu/cgi/viewcontent.cgi?article=1002&context=jtrpdata |
| Manual on Uniform Traffic Control Devices (MUTCD) | Manual on Uniform Traffic Control Devices (MUTCD), Federal Highways Administration, 2009 edition with Revision Number 3 Incorporated, August 2022, NEMA, published 2020 |
| NEMA TS 1-1989 (R2020) | NEMA Standards Publication TS 1-1989 (R1994, R2000, R2005, R2020), Traffic Control Systems (Not Recommended for New Designs) |
| NEMA TS 2-2021 | NEMA Standards Publication TS 2-2021, Traffic Controller Assemblies with NTCIP Requirements Version 03.08, NEMA, published 2021 |
| NTCIP 2201:2003 | Transportation Transport Profile (T2), AASHTO / ITE / NEMA, published September 2005 |
| NTCIP 2202:2001 | Transport Profile for Internet (TCP/IP and UDP/IP), AASHTO / ITE / NEMA, published December 2001 |
| OMG Unified Modeling Language Specification, Version 1.5 | OMG Unified Modeling Language Specification, Object Management Group, 2003 |
| SAE J2945/1_202004 | On-Board System Requirements for V2V Safety Communications, SAE International, published April 2020 |
| U.S. Architecture Reference for Cooperative and Intelligent Transportation (ARC-IT) | Architecture Reference for Cooperative and Intelligent Transportation (ARC-IT), USDOT, http://arc-it.net/ |
| V2I Hub Interface Control Document | Integrated Vehicle-to-Infrastructure Prototype (IVP), V2I Hub Interface Control Document (ICD) - Final Report March 2017, FHWA JPO |

### 1.2.3 Contact Information

#### 1.2.3.1 Internet Documents

Obtain Request for Comment (RFC) electronic documents from several repositories on the World Wide Web, or by "anonymous" File Transfer Protocol (FTP) with several hosts. Browse or FTP to:
- www.rfc-editor.org
- For FTP sites, read ftp://ftp.isi.edu/in-notes/rfc-retrieval.txt

#### 1.2.3.2 Architecture Reference for Cooperative and Intelligent Transportation

The Architecture Reference for Cooperative and Intelligent Transportation (ARC-IT) may be viewed at:
- http://arc-it.net/

ARC-IT is also known as US National ITS Architecture and combines the US National ITS Architecture and the Connected Vehicle Reference Implementation Architecture (CVRIA).

#### 1.2.3.3 NTCIP Standards

Copies of NTCIP standards may be obtained from:

**NTCIP Coordinator**  
National Electrical Manufacturers Association  
1300 N. 17th Street, Suite 900  
Rosslyn, Virginia 22209-3801  
www.ntcip.org  
email: ntcip@nema.org

Draft amendments, which are under discussion by the relevant NTCIP Working Group, and amendments recommended by the NTCIP Joint Committee are available.

#### 1.2.3.4 Object Management Group Documents

Copies of OMG standards may be obtained electronically from the Object Management Group at:
- www.omg.org

#### 1.2.3.5 SAE International Documents

Copies of SAE International documents may be obtained from:

**SAE International**  
400 Commonwealth Drive  
Warrendale, PA 15096  
www.sae.org

#### 1.2.3.6 ATC Standards

The Advanced Transportation Controller (ATC) Family of Standards may be viewed at:
- https://www.ite.org/technical-resources/standards/

#### 1.2.3.7 Caltrans Standards

Caltrans' Transportation Electrical Equipment Specifications (TEES) may be viewed at:
- https://dot.ca.gov/programs/traffic-operations/tees

#### 1.2.3.8 V2I Hub Document

Copies of Integrated Vehicle-to-Infrastructure Prototype (IVP), V2I Hub Interface Control Document (ICD), Final Report – March 2017, may be obtained from the FHWA Open Source Application Development Portal (OSADP):
- https://www.itsforge.net/

## 1.3 General Statements

<In the opinion of the responsible NTCIP working group, Section 1.3 does not apply in the context of NTCIP 1202 v03.>

## 1.4 Terms

For the purposes of NTCIP 1202 v03, the following terms, definitions, acronyms, and abbreviations apply. Meteorological terms not defined in this section are in accordance with their definitions in the Glossary of Meteorology. Electrical and electronic terms not defined here are used in accordance with their definitions in IEEE 100-2000. English words not defined here or in IEEE 100-2000 are used in accordance with their definitions in Webster's New Collegiate Dictionary.

| Term | Definition |
|------|------------|
| Actuated Signal Controller (ASC) | Any traffic signal controller, regardless if it is a phase-based controller or interval-based controller. |
| actuation | The operation of any type of detector. |
| advanced preemption time | The period of time between the minimum warning time needed for railroad operations and the maximum preemption time required for highway traffic signal operations. |
| automatic flash | Automatic programmed flash mode not caused by manual switch activation or fault condition or startup. |
| auxiliary function | A control that may activate auxiliary functions or outputs in an actuated controller unit. |
| backup mode | Control by local TBC or Interconnect based on absence of master or central command. |
| barrier | A barrier (compatibility line) is a reference point in the preferred sequence of a multi-ring CU at which all rings are interlocked. Note: Barriers ensure there is no concurrent selection and timing of conflicting phases for traffic movement in different rings. All rings cross the barrier simultaneously for the selection and timing of phases on the other side. |
| Basic Safety Message (BSM) | The Basic Safety Message (BSM) is used in a variety of applications to exchange safety data regarding vehicle state. Source: SAE J2735_202211. |
| Bus Rapid Transit (BRT) | Bus rapid transit (BRT) refers to a system of buses that operate more like a conventional rail system than the traditional local buses. BRT lines can operate in mixed traffic like other bus routes, in reserved bus lanes, or even in segregated rights of way. For the purpose of this document, BRT refers to reserved bus lanes or segregated lanes arriving at a signalized intersection. |
| call | A registration of a demand for right-of-way by traffic (vehicles or pedestrians) to a controller unit. |
| call, serviceable conflicting | A call that: a) Occurs on a conflicting phase not having the right-of-way at the time the call is placed. b) Occurs on a conflicting phase that is capable of responding to a call. c) When occurring on a conflicting phase operating in an occupancy mode, remains present until given its right-of-way. |
| channel | Three circuits of a Monitor Device wired to monitor the green, yellow, and red outputs of the associated load switch position in the Terminal & Facilities. Channel 1 is assumed to monitor Load Switch 1, etc. |
| check | An output from a controller unit that indicates the existence of unanswered call(s). |
| clear track change interval | The yellow change interval following the clear track green interval and preceding the railroad hold intervals. A red clearance interval shall follow the clear track change interval if such an interval follows the normal yellow change interval. (Preemption of Traffic Signals Near Railroad Crossings - ITE, 2006.) |
| computed lane | A lane that has a similar geometry and attributes of another lane. |
| concurrency group | A group of phases that describes possible timing combinations. Note: A phase within the group is required to be able to time concurrently with any other phase from another ring contained in the group. For example, in the typical dual ring eight phase design, phases 1, 2, 5, and 6 form one concurrency group, and phases 3, 4, 7, and 8 form another concurrency group. |
| concurrent timing | A mode of controller unit operation whereby a traffic phase can be selected and timed simultaneously and independently with another traffic phase. |
| connected device | A mobile device, such as a vehicle or smartphone, equipped to broadcast, transmit, or receive messages using V2X communications. |
| Connected Vehicle Roadside Process | A logical, functional process consisting of sub-processes that support the connected vehicle environment. From the context of an ASC, the relevant sub-processes include running intersection CV applications, broadcasting the SPaT and MAP messages to connected devices, and processing Basic Safety Messages (BSMs) and Personal Safety Messages (PSMs) received from connected devices by the CV Roadside Process. Physically, this may be a roadside unit (RSU). |
| Controller Assembly (CA) | A complete electrical device mounted in a cabinet for controlling the operation of a traffic control signal display(s). |
| Controller Unit (CU) | A controller unit is that portion of a controller assembly that is devoted to the selection and timing of signal displays. |
| Coordinated Universal Time (UTC) | UTC is the time standard commonly used across the world. The world's timing centers have agreed to keep their time scales closely synchronized—or coordinated. This 24-hour time standard is kept using highly precise atomic clocks combined with the Earth's rotation. UTC is similar to Greenwich Mean Time, but while UTC is a time standard, GMT refers to a time zone (similar to Eastern Standard Time). UTC never changes to account for daylight saving time. |
| coordination | The control of controller units in a manner to provide a relationship between specific green indications at adjacent intersections in accordance with a time schedule to permit continuous operation of groups of vehicles along the street at a planned speed. |
| coordinator | A device or program/routine that provides coordination. |
| cycle | The total time to complete one sequence of signalization around an intersection. In an actuated controller unit, a complete cycle is dependent on the presence of calls on all phases. Note: In a pre-timed controller unit it is a complete sequence of signal indications. |
| cycle length | The time period in seconds required for one complete cycle. |
| detector, pedestrian | Pedestrian detectors may be pushbuttons or passive detection devices. Passive detection devices register the presence of a pedestrian in a position indicative of a desire to cross, without requiring the pedestrian to push a button. Some passive detection devices are capable of tracking the progress of a pedestrian as the pedestrian crosses the roadway for the purpose of extending or shortening the duration of certain pedestrian timing intervals. Note: Manual of Uniform Traffic Control Devices, FHWA, May 2012. |
| detector, system | Any type of vehicle detector used to obtain representative traffic flow information. |
| detector, vehicle | A detector that is responsive to operation by or the presence of a vehicle. |
| dial | The cycle timing reference or coordination input activating same. Dial is also frequently used to describe the cycle. |
| display map | A graphic display of the street system being controlled showing the status of the signal indications and the status of the traffic flow conditions. |
| dual entry | Dual entry is a mode of operation (in a multi-ring CU) in which one phase in each ring is required to be in service. Note: If a call does not exist in a ring when it crosses the barrier, a phase is selected in that ring to be activated by the CU in a predetermined manner. |
| dwell | The interval portion of a phase when present timing requirements have been completed. |
| dynamic timing pattern | A transient timing plan to be used for the next cycle only. |
| external control location application | An application that asserts a higher-level control over the traffic signal controller. |
| enabled lanes (list) | A sequence of lane identifiers for lanes that are identified to be enabled (active) and can be used by the appropriate travelers at the current time. |
| fault monitor state | Internal CU diagnostics have determined that the CU device is not in a safe operational state. Note: An output may be asserted to indicate this condition. |
| first coordinated phase | The coordinated phase that occurs first within the concurrent group of phases containing the coordinated phase(s) when there are constant calls on all phases. |
| Flash | An operation where one section in each vehicle signal (yellow or red) is alternately on and off with a one-second cycle time and a 50% duty cycle. |
| Force Off | A command to force the termination of the green indication in the actuated mode or Walk Hold in the nonactuated mode of the associated phase. Note: Termination is subject to the presence of a serviceable conflicting call. The Force Off function is not effective during the timing of the Initial, Walk, or Pedestrian Clearance. The Force Off is only effective as long as the condition is sustained. If a phase-specific Force Off is applied, the Force Off does not prevent the start of green for that phase. |
| Free | Operation without coordination control from any source. |
| gap reduction | A feature whereby the Unit Extension or allowed time spacing between successive vehicle actuations on the phase displaying the green in the extensible portion of the Green indication is reduced. |
| Group | Any portion of a traffic control network (system) that can be controlled by a common set of timing patterns. |
| Hold | A command that retains the existing Green indication. |
| Hold-on line | A signal to an intersection controller commanding it to remain under computer control. |
| indication | The part or parts of the signal cycle during which signal indication displays do not change. |
| interchangeability | A condition that exists when two or more items possess such functional and physical characteristics as to be equivalent in performance and durability and are capable of being exchanged one for the other without alteration of the items themselves, or adjoining items, except for adjustment, and without selection for fit and performance. Source: National Telecommunications and Information Administration, U.S. Department of Commerce. |
| Interconnect | A means of remotely controlling some or all of the functions of a traffic signal. |
| interoperability | The ability of two or more systems or components to exchange information and use the information that has been exchanged Source: IEEE 610.12-1990: IEEE Standard Glossary of Software Engineering Terminology. |
| intersection status | The knowledge of whether a controlled intersection is online and which mode it is currently operating in. |
| Interval-based controller | A traffic signal controller implementing a sequence of defined, discrete steps (i.e., an interval), each interval driving their associated signal indications, in a repeating cycle according to the timing constraints programmed into the device. Note that some step sequences may be displayed or skipped in response to traffic conditions. |
| Light Rail Transit (LRT) | A metropolitan electric railway system characterized by its ability to operate single cars or short trains along exclusive rights-of-way at ground level, on aerial structures, in subways, or, occasionally, in streets, and to board and discharge passengers at track or car-floor level. For the purpose of this document, LRT refers to exclusive rights-of-way lanes arriving at a signalized intersection. |
| load switch driver group | The set of three outputs that are used to drive load switch inputs to provide a Green, Yellow, or Red output condition for vehicle signals or Walk, Ped Clear, or Don't Walk output condition for pedestrian signals. |
| Malfunction Management Unit (MMU) | A device used to detect and respond to improper and conflicting signals and improper operating voltages in a traffic controller assembly. |
| Management Information Base (MIB) | A structured collection or database of related managed objects defined using Abstract Syntax Notation One (ASN.1). Source: NTCIP 8004 v02 and ISO/IEC 8824-1:2008 and ISO/IEC 8825-1:2008. |
| MAP message | The MAPData message is used to convey many types of geographic road information. At the current time, its primary use is to convey one or more intersection lane geometry maps within a single message. Source: SAE J2735_202211. |
| maximum green | The maximum green time with a serviceable opposing actuation, which may start during the initial portion. |
| Mobile Unit (MU) | A device used to wirelessly communicate with other devices for safety and mobility purposes carried by a pedestrian, bicyclist, work zone worker, or other traveler. |
| Movement | An action that is taken to traverse through an intersection, reflecting the user perspective and defined by the user type. |
| Multi-ring controller unit | A multi-ring CU contains two or more interlocked rings that are arranged to time in a preferred sequence and to allow concurrent timing of all rings, subject to barrier restraint. |
| Node point | A point defining the centerline of the pathway of a lane. |
| nonlocking memory | A mode of actuated controller unit operation that does not require the retention of a call for future utilization by the controller assembly. |
| Occupancy | A measurement of vehicle presence within a zone of detection, expressed in seconds of time a given point or area is occupied by a vehicle. |
| Off-line | A controller assembly not under the control of the normal control source. |
| Offset | The time relationship, expressed in seconds, between the starting point of the first coordinated phase Green and a system reference point. (See definition of first coordinated phase.) |
| omit, phase | A command that causes omission of a selected phase. |
| On-Board Unit (OBU) | A device used to wirelessly communicate with other devices for safety and mobility purposes installed in a vehicle as original equipment or as aftermarket equipment (sometimes referred to as an "aftermarket safety device (ASD)". |
| Online | A controller assembly under the control of the normal control source. |
| Overlap | A Green display that allows traffic movement during the green indications of and clearance indications between two or more phases. |
| Passage time | The time allowed for a vehicle to travel at a selected speed from the detector to the stop line. |
| Pattern | A unique set of coordination parameters (cycle value, split values, offset value, and either signal plan or phase sequence). Note: A phase-based timing pattern consists of a cycle length, offset, set of minimum green and maximum green values, force off (determined by splits in some cases), and phase sequence. It also includes specification of phase parameters for minimum or maximum vehicle recall, pedestrian recall, or phase omit. An interval-based timing pattern consists of a cycle length, offset, set of minimum and programmed interval duration values, and signal plan sequence. |
| Pedestrian clearance interval | The first clearance interval for the pedestrian signal following the pedestrian WALK indication. |
| Pedestrian recycle | A method of placing a recurring demand for pedestrian service on the movement when that movement is not in its Walk interval. |
| permissive | A time period, during which the CU is allowed to leave the coordinated phase(s) under coordination control to go to other phases. |
| Personal Safety Message (PSM) | The Personal Safety Message (PSM) is used to broadcast safety data regarding the kinematic state of various types of Vulnerable Road Users (VRU), such as pedestrians, cyclists, or road workers. Source: SAE J2735_202211. |
| phase sequence | A predetermined order in which the phases of a cycle occur. |
| phase, active | The indicated phase is currently timing. A phase is always active if it is Green or Yellow (Walk or Pedestrian Clear for Pedestrian Phases). It is also active if it is timing Red Clearance. It may be considered active during Red Dwell. |
| phase, conflicting | Conflicting phases are two or more traffic phases that cause interfering traffic movements if operated concurrently. |
| phase, nonconflicting | Nonconflicting phases are two or more traffic phases that do not cause interfering traffic movements if operated concurrently. |
| phase, pedestrian | A traffic phase allocated to pedestrian traffic that may provide a right-of-way pedestrian indication either concurrently with one or more vehicular phases, or to the exclusion of all vehicular phases. |
| phase, traffic | Those green, change, and clearance intervals in a cycle assigned to any independent movement(s) of traffic. |
| phase, vehicular | A vehicular phase is a phase that is allocated to vehicular traffic movement as timed by the controller unit. |
| preempt dwell interval | The period of time when the track area is occupied by a tracked vehicle. |
| preemption | The transfer of the normal control of signals to a special signal control mode for the purpose of servicing railroad crossings, emergency vehicle passage, mass transit vehicle passage, and other special tasks, the control of which requires terminating normal traffic control to provide the priority needs of the special task. |
| preemptor | A device or program/routine that provides preemption. |
| priority request | The information that describes a need for (signal) priority service based upon user-defined criteria (such as the number of minutes behind schedule, vehicle occupancy levels, vehicle class, etc.). Note: From NTCIP 1211 v02. |
| progression | The act of various controller units providing specific green indications in accordance with a time schedule to permit continuous operation of groups of vehicles along the street at a planned speed. |
| red clearance interval | A clearance interval that may follow the yellow change interval during which both the terminating phase and the next phase display Red signal indications. |
| red revert | Provision within the controller unit to ensure a minimum Red signal indication in a phase following the Yellow Change interval of that phase. |
| referenced lane | A lane used to define the attributes of another lane. |
| rest | The interval portion of a phase when present timing requirements have been completed. |
| right-of-way transfer time | While providing preemption, the maximum amount of time needed for the worst-case condition, prior to display of the clear track green interval. This includes any railroad or traffic signal control equipment time to react to a preemption call, and any traffic signal green, pedestrian walk and clearance, yellow change, and red clearance interval for conflicting traffic. |
| ring | A ring consists of two or more sequentially timed and individually selected conflicting phases so arranged as to occur in an established order. |
| Roadside Unit (RSU) | A transportation infrastructure communications device located on the roadside that provides V2X connectivity between OBUs/MUs and other parts of the transportation infrastructure, including traffic control devices, traffic management systems, and back-office systems. Note: Devices that are not part of the transportation infrastructure, such as cellular base stations or satellites, are not RSUs. Source: CTI 4001. |
| sample | A collection of data recorded over an identified period of time. |
| sequence, interval | The order of appearance of signal indications during successive intervals of a cycle. |
| service request | The information that describes a (signal) priority service to be processed by the ASC. Note: From NTCIP 1211 v02. |
| service requestor | A traveler requesting signal service or priority using a connected device. The connected device may be an OBE or a smartphone. |
| signal control priority strategy | Defines the phases to be serviced, phases to be omitted, and maximum green times that can be reduced or extended to service a priority request. |
| Signal Monitoring Unit (SMU) | A subassembly that performs signal monitoring functions within a traffic signal cabinet. The signal monitoring unit is called a Malfunction Management Unit (MMU) in the NEMA TS 2 standard and a Cabinet Monitor Unit (CMU) in the ITS Cabinet Standard. |
| signal plan | A unique set of parameters that define the phase / interval sequence of signal indications and control for one cycle. |
| signal request | A request for signal service or signal priority via an SAE J2735 Signal Request Message. |
| single entry | Single entry is a mode of operation (in a multi-ring CU) in which a phase in one ring can be selected and timed alone if there is no demand for service in a nonconflicting phase on the parallel ring(s). |
| single-ring controller unit | A single-ring CU contains two or more sequentially timed and individually selected conflicting phases so arranged as to occur in an established order. |
| special function | A control that may activate a device external to the controller unit. |
| split | The segment of the cycle length allocated to each phase or interval that may occur (expressed in seconds). Note: In an actuated controller unit, split is the time in the cycle allocated to a phase. |
| stall condition | An operational state in which the ASC can no longer transmit any data to the management station. Note: The health monitor (watchdog) might or might not work in this situation, but its condition is not able to be transmitted to the management station. |
| standby mode | An operational state called by master or central command that directs the controller unit to select Pattern, Automatic Flash, or Automatic Free based on local Time Base schedule or Interconnect inputs. |
| TimeChangeDetail | A data frame that conveys details about the timing of a phase within a movement. The core data concept expressed is the time stamp (time mark) at which the related phase will change to the next state. Source: SAE J2735_202211. |
| Time-based Control (TBC) | A means for the automatic selection of modes of operation of traffic signals in a manner prescribed by a predetermined time schedule. |
| timing pattern | See Pattern. |
| timing plan | The Split times for all segments (Phase/Interval) of the coordination cycle. |
| track clearing interval | While providing preemption, the time assigned to clear stopped vehicles from the track area on the approach to the signalized highway intersection. |
| Traffic Signal Controller Broadcast Message (TSCBM) | A message defined in the V2I Hub Interface Control Document containing signal phase and timing (SPaT) information composed of the SNMP data objects sent by the traffic signal controller to an RSU. |
| volume | The number of vehicles passing a given point per unit of time. |
| yellow change interval | The first interval following the green interval in which the signal indication for that phase is yellow. |
| yield | A command that permits termination of the green interval. |
| zone | An area in which traffic parameters can be measured and/or traffic data can be generated. |

## 1.5 Abbreviations

The abbreviations (acronyms) used in NTCIP 1202 v03, and not defined in Section 1.4, are defined as follows:

| Abbreviation | Full Term |
|--------------|-----------|
| ADA | Americans with Disabilities Act |
| APS | Accessible Pedestrian Signals |
| BIU | Bus Interface Unit |
| CMU | Cabinet Monitor Unit |
| CV | Connected Vehicles |
| CVRIA | Connected Vehicles Reference Implementation Architecture |
| DSRC | Dedicated Short Range Communications |
| ECLA | External Control Local Application |
| GNSS | Global Navigation Satellite System |
| GPS | Global Positioning System |
| HOV | High Occupancy Vehicle |
| ITS | Intelligent Transportation Systems |
| MAC | Media Access Control |
| MUTCD | Manual on Uniform Traffic Control Devices |
| PRL | Protocol Requirements List |
| RSE | Roadside Equipment |
| RSU | Roadside Unit |
| RTM | Requirements Traceability Matrix |
| SIU | Serial Interface Unit |
| SNMP | Simple Network Management Protocol |
| SPaT | Signal Phase and Timing (as defined by SAE J2735_202007) |
| V2X | Vehicle-to-Everything |
| VRU | Vulnerable Road User |

---

**Document Information:**
- Source: NTCIP 1202 v03B.35
- Published by: AASHTO / ITE / NEMA, © 2023
- Page Range: Pages 1-14
