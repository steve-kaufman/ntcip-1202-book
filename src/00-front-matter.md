# NTCIP 1202 Version 03B - Front Matter

## Title Page

**A Joint Standard of AASHTO, ITE, and NEMA**

### NTCIP 1202 Version 03B

**National Transportation Communications for ITS Protocol**  
**Object Definitions for Actuated Signal Controllers (ASC) Interface**

Published in October 2023

---

### Published by

**American Association of State Highway and Transportation Officials (AASHTO)**  
444 North Capitol Street, N.W., Suite 249  
Washington, D.C. 20001

**Institute of Transportation Engineers (ITE)**  
1627 Eye Street, N.W., Suite 550  
Washington, D.C. 20006

**National Electrical Manufacturers Association (NEMA)**  
1300 North 17th Street, Suite 900  
Rosslyn, Virginia 22209-3801

---

## Copyright Notice

© 2023 by the American Association of State Highway and Transportation Officials (AASHTO), the Institute of Transportation Engineers (ITE), and the National Electrical Manufacturers Association (NEMA).

All intellectual property rights, including, but not limited to, the rights of reproduction, translation, and display are reserved under the laws of the United States of America, the Universal Copyright Convention, the Berne Convention, and the International and Pan American Copyright Conventions.

Except as licensed or permitted, you may not copy these materials without prior written permission from AASHTO, ITE, or NEMA. Use of these materials does not give you any rights of ownership or claim of copyright in or to these materials.

Visit www.ntcip.org for other copyright information, for instructions to request reprints of excerpts, and to request reproduction that is not granted below.

---

## License Agreements

### PDF File License Agreement

To the extent that these materials are distributed by AASHTO / ITE / NEMA in the form of an Adobe® Portable Document Format (PDF) electronic data file, AASHTO / ITE / NEMA authorizes each registered PDF file user to view, download, copy, or print the PDF file available from the authorized Web site, subject to the following terms and conditions:

- You may download one copy of each PDF file for personal, noncommercial, and intraorganizational use only
- Ownership of the PDF file is not transferred to you; you are licensed to use the PDF file
- You may make one more electronic copy of the PDF file, such as to a second hard drive or burn to a CD
- You agree not to copy, distribute, or transfer the PDF file from that media to any other electronic media or device
- You may print one paper copy of the PDF file
- You may make one paper reproduction of the printed copy
- Any permitted copies of the PDF file must retain the copyright notice, and any other proprietary notices contained in the file
- The PDF file license does not include: (1) resale of the PDF file or copies, (2) republishing the content in compendiums or anthologies, (3) publishing excerpts in commercial publications or works for hire, (4) editing or modification of the PDF file except those portions as permitted, (5) posting on network servers or distribution by electronic mail or from electronic storage devices, and (6) translation to other languages or conversion to other electronic formats
- Other use of the PDF file and printed copy requires express, prior written consent

### Data Dictionary and MIB Distribution Permission

To the extent that these materials are distributed by AASHTO / ITE / NEMA in the form of a Data Dictionary ("DD") or Management Information Base ("MIB"), AASHTO / ITE / NEMA extend the following permission:

You may make or distribute unlimited copies, including derivative works, of the DD or MIB, including copies for commercial distribution, provided that:

- Each copy you make or distribute includes the citation "Derived from NTCIP 0000 [insert the standard number]. Copyright by AASHTO / ITE / NEMA. Used by permission."
- The copies or derivative works are not made part of the standard publications or works offered by other standard developing organizations or publishers or as works-for-hire not associated with commercial hardware or software products intended for field implementation
- Use of the DD or MIB is restricted in that the SYNTAX fields may only be modified to define: 1) a more restrictive subrange; or 2) a subset of the standard enumerated values; or 3) a set of retired and defined enumerated values for systems supporting multiversion interoperability
- The description field may be modified but only to the extent that: 1) the more restrictive subrange is defined; and 2) only those bit values or enumerated values that are supported are listed

### PRL and RTM Distribution Permission

To the extent that these materials are distributed by AASHTO / ITE / NEMA in the form of a Protocol Requirements List ("PRL") or a Requirements Traceability Matrix ("RTM"), AASHTO / ITE / NEMA extend the following permission:

- You may make or distribute unlimited copies, including derivative works of the PRL (then known as a Profile Implementation Conformance Statement ("PICS")) or the RTM, provided that each copy you make or distribute contains the citation "Based on NTCIP 0000 [insert the standard number] PRL or RTM. Used by permission. Original text © AASHTO / ITE / NEMA."
- You may only modify the PRL or the RTM by adding: 1) text in the Project Requirements column, which is the only column that may be modified to show a product's implementation or the project-specific requirements; and/or 2) additional table columns or table rows that are clearly labeled as ADDITIONAL for project-unique or vendor-unique features
- If the PRL or RTM excerpt is made from an unapproved draft, add to the citation "PRL (or RTM) excerpted from a draft standard containing preliminary information that is subject to change."

### TRF Distribution Permission

A Testing Requirements Form ("TRF") may be a Testing Requirements Traceability Table and/or Test Procedures. To the extent that these materials are distributed by AASHTO / ITE / NEMA in the form of a TRF, AASHTO / ITE / NEMA extend the following permission:

- You may make and/or distribute unlimited electronic or hard copies, including derivative works of the TRF, provided that each copy you make and/or distribute contains the citation "Based on NTCIP 0000 [insert the standard number] TRF. Used by permission. Original text © AASHTO / ITE / NEMA."
- You may not modify the logical flow of any test procedure, without clearly noting and marking any such modification
- If the TRF excerpt is made from an unapproved draft, add to the citation "TRF excerpted from a draft standard containing preliminary information that is subject to change."

---

## Disclaimer

### Content and Liability Disclaimer

The information in this publication was considered technically sound by the consensus of persons engaged in the development and approval of the document at the time it was developed. Consensus does not necessarily mean that there is unanimous agreement among every person participating in the development of this document.

These materials are delivered "AS IS" without any warranties as to their use or performance. AASHTO / ITE / NEMA and their suppliers do not warrant the performance or results you may obtain by using these materials. AASHTO / ITE / NEMA and their suppliers make no warranties, express or implied, as to noninfringement of third party rights, merchantability, or fitness for any particular purpose.

In no event will AASHTO / ITE / NEMA or their suppliers be liable to you or any third party for any claim or for any consequential, incidental or special damages, including any lost profits or lost savings, arising from your reproduction or use of these materials, even if an AASHTO / ITE / NEMA representative has been advised of the possibility of such damages.

AASHTO, ITE, and NEMA disclaim liability for any personal injury, property, or other damages of any nature whatsoever, whether special, indirect, consequential, or compensatory, directly or indirectly resulting from the publication, use of, application, or reliance on this document.

AASHTO, ITE, and NEMA have no power, nor do they undertake to police or enforce compliance with the contents of this document. AASHTO, ITE, and NEMA do not certify, test, or inspect products, designs, or installations for safety or health purposes.

---

## Trademark Notice

NTCIP is a trademark of AASHTO / ITE / NEMA. All other marks mentioned in this standard are the trademarks of their respective owners.

---

## Acknowledgments

NTCIP 1202 v03 was prepared by the NTCIP Actuated Signal Controller Working Group (ASC WG), which is a subdivision of the Joint Committee on the NTCIP. The NTCIP Joint Committee is organized under a Memorandum of Understanding among AASHTO, ITE, and NEMA.

### Voting and Alternate Voting Members

- **City of Anaheim**: John Thai* (Co-Chair)
- **California Department of Transportation**: Mike Robinson*, Jay Schultz
- **Econolite Control Products, Inc.**: Dustin DeVoe*, Dan Brandesky
- **Florida Department of Transportation**: Matthew DeWitt*, Jeffrey Morgan, Derek Vollmer
- **Minnesota Department of Transportation**: Ray Starr*, Terry Haukom, Peter Skewers
- **Nissan Motor Co.**: Roy Goudy*
- **Oregon Department of Transportation**: Christopher Primm*, Roger Boettcher, Doug Spencer
- **Pillar Consulting**: Ralph Boaz*
- **Q-Free**: Doug Tarico* (Co-Chair), Douglas Crawford
- **Texas A&M University (TTI)**: Kevin Balke*, Hassan Charara, Srinivasa Sunkari
- **TransCore ITS**: Robert Rausch*, David Benevelli, Keith Patton
- **Yunex Traffic**: Jonathan Grant*, Dave Miller, Iouri Nemirovski

*Asterisk indicates voting member*

### Observing Members

- Applied Information, Inc.: Bryan Mulligan, Walt Townsend
- Consensus Systems Technologies: Patrick Chan, AJ Lahiri
- Eberle Design, Inc.: Scott Evans
- Econolite: Gary Duncan, Barry Einsig, Eric Raamot
- McCain Inc.: Donald Maas Jr., Matt Zinn, Mark Simpson
- Southwest Research Institute: Cameron Mott

### Additional Stakeholders

Over 50 additional stakeholders from various organizations provided input or monitored development, representing state DOTs, consulting firms, technology vendors, and research institutions.

### Funding

Recognition is given to the **U.S. Department of Transportation** for providing funding support.

---

## Foreword

NTCIP 1202 v03, an NTCIP standards publication, identifies and defines how a management station may wish to interface with a field device to control and monitor traffic signal controllers and associated detectors in an NTCIP-conformant fashion. NTCIP 1202 v03 uses only metric units.

NTCIP 1202 v03 is titled **Object Definitions for Actuated Signal Controllers (ASC) Interface** to express the multiple sections and annexes that are included in NTCIP 1202 v03. This NTCIP 1200-series standards publication has grown beyond the "object definitions" that were reflected in the title for its predecessors, NTCIP 1202 versions v01 and v02 (2005).

NTCIP 1202 v03 defines data elements for use with Actuated Signal Controller Units. The data is defined using the Simple Network Management Protocol (SNMP) object-type format as defined in RFC 1212 and the defined NTCIP format defined in NTCIP 8004. This data would typically be exchanged using one of the NTCIP 1103 recognized Application Layers (e.g., SNMP).

NTCIP 1202 v03 follows an established systems engineering approach to support procurement processes. The PRL is designed to allow an agency to indicate what user needs are applicable to a procurement, and to select which requirements are to be implemented in a project-specific implementation.

### Keywords

AASHTO, ITE, NEMA, NTCIP, ASC, data, data dictionary, object, MIB, PRL and RTM.

NTCIP 1202 v03 is also an NTCIP Data Dictionary standard. For more information about NTCIP standards, or to acquire the related NTCIP 1202 v03 MIB, visit www.ntcip.org.

---

## Amendments and Errata

### NTCIP 1202 v03A Errata (Flashing Yellow Arrow)

As NTCIP 1202 v03 was about to be published and distributed, a user provided proposed clarifications/corrections associated with experience in implementing the Flashing Yellow Arrow (FYA) functionality described in Sections 5.9.2.7, 7.2.5.3, 7.2.5.11, and 7.2.7.1. These clarifications/corrections constitute the FYA errata and were published as NTCIP 1202 v03A in May 2019.

### NTCIP 1202 v03B Amendment

The NTCIP 1202 v03B Amendment was published in 2023 to address an urgent need to fix errors, clarify definitions, and provide additional guidance for traffic signal controllers to support the SAE J2735 SPaT Message in response to guidance detailed in Connected Transportation Interoperability (CTI) 4501, Connected Intersections (CI) Implementation Guide.

In addition, a project led by the City of Anaheim and sponsored by USDOT developed test procedures and test software to verify the NTCIP 1202 v03A standard. This project resulted in the discovery of various ambiguities and errors in NTCIP 1202 v03A.

### Key Changes in v03B

1. Deprecated user need 2.5.4.2, Connected Vehicle Manager: Management Station – CV Roadside Process Interface, which is now superseded by NTCIP 1218
2. Deprecated support for the CV Roadside Process as an SNMP manager
3. Added User Need 2.6.5 for Managing Security with Other Interfaces
4. Added requirements 3.4.1.4.1 – 3.4.1.4.5 SNMP Requirements to support the SNMP Conformance Group
5. Added requirements H.1.1.11 and H.1.1.12 to support the System Conformance Group
6. Corrected errors with RTM for use of the overlapType object
7. Updated requirements and design content to support the requirements in CTI 4501
8. Updated the Protocol Requirements List to be consistent with CTI 4501
9. Added requirements for Start Time
10. Added allRedControllerFlash (3) for unitStartUpFlashMode
11. Updated object definitions based on 2022 version of SAE J2735
12. Added the Object Types for each object definition in MIB
13. Corrected errors in standard block objects
14. Added two new standard block objects

---

## Approvals

NTCIP 1202 v03 was separately balloted and approved by AASHTO, ITE, and NEMA after recommendation by the Joint Committee on the NTCIP. Each organization has approved NTCIP 1202 v03 as the following standard type, as of the date:

- **AASHTO** — Standard Specification; December 2018
- **ITE** — Software Standard; January 2019
- **NEMA** — Standard; December 2018

---

## History

In 1992, the NEMA 3TS Transportation Management Systems and Associated Control Devices Section began the effort to develop NTCIP. Under the guidance of the Federal Highway Administration's NTCIP Steering Group, the NEMA effort was expanded to include the development of communications standards for all transportation field devices that could be used in an ITS network.

In September 1996, an agreement was executed among AASHTO, ITE, and NEMA to jointly develop, approve, and maintain the NTCIP standards. In late 1998, the Actuated Signal Controller Working Group was tasked with the effort to update the Actuated Traffic Signal Controller Object Definitions document. The first meeting of this working group was held in October 1999.

### Version History

- **NEMA TS 3.5-1996** (1996) – Approved by NEMA; Accepted as a Recommended Standard by the Joint Committee on the NTCIP; Approved by AASHTO and ITE in 1997
  - v01.07a printed with NEMA cover
  
- **NTCIP 1202 v01** – v01.07b printed with joint cover; v01.07c printed to PDF in November 2002; v01.07d printed to PDF for no-cost distribution January 2005

- **NTCIP 1202 Amendment 1** (November 1999) – Accepted as a User Comment Draft Amendment; incorporated into 1202 v02

- **NTCIP 1202 v02.10** (June 2001) – Accepted as a User Comment Draft by the Joint Committee

- **NTCIP 1202 v02.16** (October 2002) – Accepted as a Recommended Standard; Approved by AASHTO in November 2004, approved by ITE in March 2005, and approved by NEMA in November 2004

- **NTCIP 1202:2005 v02.19** (November 2005) – Edited document for publication

- **NTCIP 1202 v03** – Developed to reflect lessons learned, update the document to new documentation formats, and add new features such as support for a connected vehicle interface

- **NTCIP 1202 v03A** (May 2019) – Published with FYA errata

- **NTCIP 1202 v03B** (October 2023) – Published to address errors, clarifications, and support for CTI 4501

---

## Compatibility of Versions

To distinguish NTCIP 1202 v03B (as published) from previous drafts, NTCIP 1202 v03B also includes NTCIP 1202 v03B.35 on each page header. All NTCIP Standards Publications have a major and minor version number for configuration management. The version number SYNTAX is "v00.00a," with the major version number before the period, and the minor version number and edition letter (if any) after the period.

**Note**: NTCIP 1202 v03B differs from NTCIP 1202 v03A in that NTCIP 1202 v03B corrects errors, clarifies definitions, and updates the user needs, requirements, and design content in response to guidance detailed in Connected Transportation Interoperability (CTI) 4501, Connected Intersections (CI) Implementation Guide.

The MIB associated with NTCIP 1202 v03B (as published) is **1202 v0335.MIB** and **1217 v0135.MIB**.

NTCIP 1202 v03B is designated, and should be cited as, **NTCIP 1202 v03B**. Anyone using NTCIP 1202 v03 should seek information about the version number that is of interest to them in any given circumstance. The PRL, RTM, and MIB should all reference the version number of the standards publication that was the source of the excerpted material.

**Compatibility Note**: Compliant systems based on later, or higher, version numbers MAY NOT be compatible with compliant systems based on earlier, or lower, version numbers. Anyone using NTCIP 1202 v03B should also consult NTCIP 8004 v02 for specific guidelines on compatibility.

---

## User Comment Instructions

The term "User Comment" includes any type of written inquiry, comment, question, or proposed revision, from an individual person or organization, about any NTCIP 1202 v03 content. A "Request for Interpretation" is also classified as a User Comment. User Comments are solicited at any time.

User Comments should be submitted to:

**NTCIP Coordinator**  
National Electrical Manufacturers Association  
1300 North 17th Street, Suite 900  
Rosslyn, Virginia 22209-3801  
Email: ntcip@nema.org

### User Comment Format

- Standard Publication number and version:
- Page:
- Section, Paragraph, or Clause:
- Comment:
- Editorial or Substantive?:
- Suggested Alternative Language:

Please include your name, organization, and address in your correspondence.

Previous User Comments and their disposition may be available for reference and information at www.ntcip.org.

---

## Table of Contents Overview

The full table of contents begins on page vii (line 580) and includes detailed sections covering:

- User needs and concept of operations
- Requirements and specifications
- Object definitions and MIB structures
- Protocol requirements lists (PRL)
- Requirements traceability matrix (RTM)
- Standard block objects
- Testing requirements
- Normative and informative annexes
