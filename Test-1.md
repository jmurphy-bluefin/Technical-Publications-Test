# Sandshark Operations Manual
## Notices and Disclaimer
© 2015 Bluefin Robotics Corporation
### Proprietary Material
The information furnished in this document is proprietary to Bluefin Robotics Corporation (Bluefin). Information and descriptions found in this guide may not be copied or reproduced by any means, and may not be disseminated without prior express written permission from Bluefin Robotics Corporation.

### Trademarks
Bluefin Robotics is a registered trademark of Bluefin Robotics Corporation. Witness is a trademark of Bluefin Robotics Corporation. Windows is a trademark of Microsoft Corporation. All brand names and product names used in this manual are trademarks, registered trademarks or trade names of their respective holders.

### Limitation of Liability
The publisher has used their best efforts in preparing this manual. Bluefin Robotics Corporation makes no representation or warranty with respect to the accuracy or completeness of the contents of this manual and specifically disclaims any implied warranties of merchantability or fitness for any particular purpose and shall in no event be liable for any loss of profit or any other commercial damage including but not limited to special, incidental, consequential, or other damages.

The information in this manual is subject to change without notice at the discretion of Bluefin Robotics Corporation.

How to Contact Bluefin Robotics Corporation:

Bluefin Robotics Corporation

553 South Street

Quincy, MA 02169

http://www.bluefinrobotics.com

Telephone: (617) 715-7000

E-mail: support@BluefinRobotics.com

## Revision History

Based on 000-018-604RA September 18, 2015. New document created in wiki 2016-01-26.

# Preface

Welcome to the Operations Manual for the Sandshark. This document is intended to familiarize you with the system and provide you with the information necessary to carry out unmanned underwater vehicle (UUV) operations.

To prevent loss or damage to the UUV, Bluefin has included many safety recommendations in this manual that should be followed carefully and should not be changed. These recommendations are highlighted with leading text indicating Warning, Caution, and Note.

This guide contains references to checklists and other manuals in the documentation set. This includes manuals for open-source software and commercial off-the-shelf (COTS) manuals. Please ensure that you have a full documentation set available before you begin any UUV maintenance, as descriptions of all of the tasks performed in a given procedure may not be covered in this guide. Contact Bluefin if you need extra copies of any manual in this documentation set.

## List of Reference Documents

This section lists the manuals Bluefin provides for the UUV system. Bluefin recommends that operators, supervisors, and technicians responsible for operating and maintaining the UUV become familiar with the contents of these manuals before using the equipment.

**Table: Reference Documents**

| Document Name | Location |
| --- | --- |
| Sandshark Quickstart Card	|  |
| Sandshark Pre-Dive Checklist | Technical-Publications-Test/Images/Sandshark_Pre-Dive_Checklist.jpg |
| Sandshark Dive Log | Technical-Publications-Test/Images/Sandshark_Dive_Log.jpg |
| Sandshark Post-Dive Checklist | Technical-Publications-Test/Images/Sandshark_Post-Dive_Checklist.jpg |
| Sandshark Mobilization Checklist | Technical-Publications-Test/Images/Sandshark_Mobilization_Checklist.jpg |
| qgroundcontrol User Guide | http://qgroundcontrol.org/ |
| ROS User Guide | http://wiki.ros.org |
| ROS Cheat Sheet | http://services.informatik.hs-mannheim.de/~ihme/robotik_2014ws/01_ROScheatsheet.pdf |
| A Gentle Introduction to ROS: | https://cse.sc.edu/~jokane/agitr/ |
| Commercial Off The Shelf (COTS) Manuals | Contact Bluefin |
| Material Safety Data Sheets (MSDS) Package |  |


## Intended Audience

This guide is written for personnel who operate, maintain, troubleshoot, and repair the Sandshark system. Users of the UUV system should possess the following experience:
* Knowledge of underwater navigation and underwater vehicle operation. 
* Experience in the field of undersea systems.
* Experience with marine operations and handling sub-sea equipment.
* Basic understanding of Linux.
* Experience with electrical systems.

## Training

Bluefin has provided this manual to assist you in operating and maintaining the Sandshark system. Users are expected to have undergone Bluefin’s UUV training program. Users operating and maintaining the UUV must be trained in its use. Do not attempt to perform maintenance on or repairs to this system if you have not been trained in operation and maintenance of the UUV. Contact the Marine Operations Department at Bluefin for training details.

## Glossary

* *Shall* is used only when application of a procedure is mandatory.
* *Should* is used only when application of a procedure is recommended.
* *May* and *need not* are used only when application of a procedure is discretionary.
* *Will* is used only to refer to the future, never to indicate any degree of requirement for application of procedure.

### Abbreviations and Product Specific Terms

The abbreviations and product specific terminology used in this manual are described in the table below.

**Table: Glossary**

|Abbreviation or Term|	Description|
|--- | --- |
|COTS	|Commercial off-the-shelf|
|Deployment	|The complete trip, from the time the ship (loaded with an UUV and all support equipment) leaves the dock, until it returns. A deployment may comprise multiple missions containing multiple dives. The deployment leaves from the mobilization/demobilization site.| 
|Dive	|A single operational segment during which the UUV executes a set of uploaded waypoints, returning to the surface once complete. The UUV may surface multiple times in a single dive to acquire GPS positions, but the dive is not complete until all waypoints have been executed, or the dive has been aborted by the UUV or the operator.|
|DVL	|Doppler velocity log|
|GPS	|Global positioning system|
|HAZMAT	|Hazardous materials|
|Mission	|A series of one or more dives the UUV completes to accomplish a larger task. For example, during one dive, the UUV might run a lawnmower pattern over a certain area to collect sonar data, and during the second dive, it may perform the same task in an adjacent area.|
|PMA	|Post-mission analysis|
|PV	|Pressure vessel|

## Classification of Hazards

The warnings, cautions, and notes contained in this manual are defined as follows:

**Warning**

![Warning](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-warning.jpg)	**WARNING: Identifies an operating procedure, practice, condition or statement which, if not strictly observed, could result in injury or death.** 

**Caution**

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Identifies an operating or maintenance procedure, practice, condition, or statement which, if not strictly observed, could result in equipment damage or destruction, loss of mission effectiveness, long-term health hazards, or environmental damage.** 

**Note**

*Note: An essential operating or maintenance procedure, condition, or statement.*

## Warning

###General Warnings

![Warning](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-warning.jpg)	**WARNING: Procedures in this guide may require handling hazardous materials. Personnel shall become familiar with hazards and comply with the guidance in the applicable material safety data sheets (MSDSs).**

![Warning](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-warning.jpg)	**WARNING: Do not put fingers between the propeller blades. Always use a stick or probe to move propeller blades.**

![Warning](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-warning.jpg)	**WARNING: When opening or closing UUV shipping container latches, always make sure that the latches are flush with the side of the shipping containers. Latches that protrude from the shipping container may cause injuries.**

### Battery Warnings

![Warning](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-warning.jpg)	**WARNING: Before operating an UUV Battery, operators must read all warnings provided in this manual.**

**Batteries are defined as hazardous materials for the purpose of shipping and cannot be shipped with the rest of the system. Remove the batteries and ship separately. Only personnel certified in shipping hazardous materials are authorized to pack and ship batteries. Non-certified personnel may repack the batteries in the original shipping box for return to Bluefin Robotics.**

**These conditions should be avoided:**

1. **Do not expose the lithium polymer cell material inside the battery directly to water.**

2. **Do not attempt to overcharge or overdischarge the battery.**

3. **Do not expose the battery to an ambient temperature of more than 55°C (130°F).**

4. **Do not attempt to charge the battery when the ambient temperature is less than 0°C (32°F) or greater than 45°C (113°F).**

**The conditions listed above could cause a condition where the battery cells permanently lose capacity or the cells exceed their safe operating temperature and become a fire hazard.**

**Shipboard operations require the local verification of fire fighting capabilities equivalent to or better than the following:**
* **Sprinkler protected space with a minimum of seven (7) gallons per minute flow rate**

**or**

* **A standard 1.5 inch shipboard firehose.**
 
**or**

* **Lith-X or similar smothering agent including a Class D fire extinguisher with copper based extinguishing media.**

**In the event of fire where lithium ion batteries are present, call 911 or local emergency services and flood the area with water where it is safe to do so. Virtually all fires involving lithium ion batteries can be controlled with water. When water is used, however, hydrogen gas may be released, which can form an explosive mixture with air, so ensure water is only used in well ventilated areas. Where water is not available, LITH-X or Class D copper powder fire extinguishers, sand, dry ground dolomite or soda ash may also be used as smothering agents.**

**Fire fighters should wear self-contained breathing apparatus.**

**Burning lithium polymer batteries can produce toxic fumes including HF, oxides of carbon, aluminum, lithium, copper, and cobalt. Volatile phosphorus pentaflouride may form at a temperature above 110°C (230°F).**

![Warning](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-warning.jpg)	**WARNING: Do not cut into, puncture, drop, or damage the battery.**

**Do not attempt to measure the battery current by directly connecting a meter between the positive and negative terminals. This will cause high current to flow and the internal fuse to blow, potentially resulting in damage to the battery’s electronics.**

**Do not purposely short the battery terminals.**

**NEVER force any probe, wire, or other instrument or hardware in to the battery connectors.**


![Warning](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-warning.jpg)	**WARNING: Batteries are defined as hazardous materials for the purpose of shipping and cannot be shipped with the rest of the system. Remove them and ship them separately in the provided packaging.**

**Only personnel certified in the shipping of hazardous materials are authorized to pack and ship the batteries to locations other than Bluefin Robotics. Non-certified personnel may pack the batteries in their original shipping box and ship them back to Bluefin Robotics.**

## Cautions

### General Cautions

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: The tailcone is designed to operate in water. Do not allow the tailcone to run in air longer than five minutes, because it may overheat.**

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Do not power wash the UUV or its components as this may cause damage to the UUV or its components.**

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Do not use an O-ring that shows any sign of damage or wear.**

**Do not remove a connector by pulling on the cable as this may damage the integrity of the cable.
Cables and connectors that are pinched, compressed, or otherwise under strain in the stowed position may lose their watertight integrity.**

**Do not allow DC-4 Silicone Grease lubricant to come into contact with the connecting faces, pins, or pin sockets of the connectors as this may compromise the electrical connection.**

**Do not bend wet-mateable connectors back and forth to work the connectors together. Bending or squeezing the connectors causes the pins to bend and can damage the pins and connectors.**

### Battery Cautions

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Before using a Bluefin Battery, vehicle operators must read all warnings provided in this manual.
Ensure that the vehicle is powered OFF before removing the battery from the vehicle.**

**Batteries should be stored in a cool place (ambient temperature less than 40°C (75°F)) away from direct sunlight.**

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Use care not to drop batteries when handling. If a battery is damaged, contact Bluefin before using, moving, or shipping it.**

**Do not allow water to enter the battery.**

**Do not place equipment or materials on the battery lid or connectors.**

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Do not charge the batteries in ambient temperatures over 45°C (113°F). Over temperature conditions will terminate the charging cycle. Over temperature conditions may occur when charging the battery in a elevated ambient temperature environment.**

# Introduction

## Sandshark

The Sandshark is a self-propelled, untethered, unmanned underwater vehicle capable of conducting independent survey operations at depths up to 100 meters.

<image>

**Figure: 100m Sandshark**

The UUV system consists of two sections:
* Tail Section — Fixed
* Payload Section — Modular and user-defined

## UUV Components: Tail Section

The tail section is a pressure vessel. Some of its components are commercial off-the-shelf (COTS) components. Their documentation is collected on the Technical Publications CD.

### Cross-Section

<image>

**Figure: Tail Section Cross-Section Showing Components**

### Components

#### Tailcone

The tailcone (part number: 000-017-506) contains a motor inside the pressure vessel and a duct and propeller outside it.
<image>
**Figure: Tailcone**

#### Fins

The 4 articulating fins steer the vehicle. There are 2 sets:
* low speed (part number: 000-017-508)
* high speed (part number: 000-017-509)

The low speed fins are taller than the high speed fins. Use the low speed fins for mission speeds between 1 and 2 knots. Use the high speed fins for mission speeds between 2 and 4 knots.

<image>

**Figure: Installing a High Speed Fin**

#### Battery

The battery (part number 000-016-395) is a 225 Wh Li ion battery. See Chapter 4, "Power" for more information.
<xref>
<image>
**Figure: The Battery Mounted in the Battery Chassis**

#### Antenna

The antenna (part number: 000-016-391) contains the magnetic ON/OFF switch, communication and GPS antennas, status LEDs, and strobe lights.

<image>

**Figure: Antenna**

**Table: LED Status**

|LED | Meaning |
|--- | ---|
| Blue | Vehicle powered (steady) |
| Red | * Test failed (steady) * Mission aborting (flashing) * Misson aborted (steady) |
| Amber	 | Reserved for user-defined payload |
|Green	| * Ready to run (steady) * Running a mission (flashing) |

The visible and infrared strobes are configurable to be:
* Always on 
* Always off
* Flashing at high speed (1x every second)
* Flashing at low speed (1x ever 5 seconds)

#### Echosounder

The Imagenex 852 echosounder (part number: 000-016-370) is exposed at the bottom of the pressure vessel. It reads altitude (how far above the bottom of the body of water the vehicle is running).

#### ADAPT M2M Module

The ADAPT module is a Machine-to-Machine Hardware Platform that uses commercial cell phone technology to connect with general sensor devices. It contains the following sensors: accelerometer sensor, pressure/temperature sensor, gyroscope sensor, E-compass sensor and an ambient light and proximity sensor.
For more information, see the ADAPT M2M Product Guide.

#### Pressure Sensor

The pressure sensor (part number: 000-016-438) is exposed on the front endcap of the tail section. It reads absolute pressure, which converts to depth (how far below the surface of the body of water the vehicle is running).

#### Connectors

The 8-pin payload and 4-pin charge connectors on the pressure vessel endcap are wet-matable Subconn Micro connectors.
<image>
**Figure:  Connectors on Endcap**
<xref> See “External Interface” on page 81.

## UUV Components: Payload Section

### Empty Payload

The empty payload contains mounting points for components, ballast, and foam. Each mounting point is a 4-40 threaded insert, compatible with standard stainless steel hardware.

### DARPA ECO-PUCK Payload

The DARPA ECO-PUCK payload is a plug-and-play environmental monitoring payload. To install, attach the puck to the mounting points in the payload section and mate the cable to the payload connector on the tail section endcap.

## Equipment Requirements

The components required to operate and maintain the UUV are listed in Appendix “Topside Equipment” on page 83. 
<xref>

## Personnel Requirements

The Sandshark is designed to be run by a single operator when launched from shore. Boat-based operations require a second operator for safety. 

## Maintenance Requirements

The maintenance requirements for the Sandshark system include:
* Visual inspection of vehicle components and subsystems for fit, assembly, and external damage. Regularly scheduled diagnostic tests to ensure the vehicle’s functionality.
* Replacing and repairing missing, consumed, or damaged items.

## Preventive Maintenance

Preventive maintenance (PM) occurs at regular intervals, including during each of the operations phases (such as pre-dive and post-dive). PM is performed either afloat or ashore.

## Corrective Maintenance

Corrective maintenance (CM) is performed on an as-needed basis. The need for corrective maintenance is established during PM. For instance, a failed diagnostic check on a fin during pre-dive PM would require replacing the fin. CM is performed either afloat or ashore.

## Format of Maintenance Procedures

The table below describes the type of information found in the preventative and corrective maintenance procedures. 

**Table: Maintenance Procedure Structure** 

|Heading |Description |
|--- | --- |
| Procedure Type	| A short two- or three-word phrase that indicates a preventative, corrective, or assembly procedure. Maintenance procedures always start on a new page. |
| Procedure Name	| The name of the maintenance procedure described (e.g., “Replacing the Dropweight”). |
| Tools and Equipment Required	 | A list of tools and equipment required to perform the maintenance procedure. |
| Background Information | Any important information that helps you perform the procedure. Sometimes this is an important note or basic information about the component on which you are about to perform maintenance.  |
| Description of Work | Step-by-step procedure explaining how to perform the required task.  |

Only qualified UUV maintenance personnel should perform these procedures. A trainee under the direct supervision of a fully qualified, Bluefin trained UUV operator or technician can perform these procedures for qualification and training. If you have questions about maintenance, contact Bluefin Technical Support.

# UUV Operations

Sandshark UUV operations have 4 phases:

1. General Preparation

2. Mission Preparation

3. Operation

4. Post-Mission Activities

General Preparation includes initial system and operations environment setup and awareness of the vehicle’s operational limits and range.

Mission Preparation includes mission planning and preparing the vehicle for the mission onsite.
Operation includes starting, monitoring, and ending a mission.

Post-Mission activities include downloading and analyzing the data, shutting down the vehicle, and rinsing the vehicle with fresh water.

## Setting Up the Operations Environment

The following sections describe the initial system and operations environment setup and configuration. 

### Setting Up IP Addresses

The Sandshark topside equipment includes a Linksys wireless router which the vehicles will automatically connect to when powered on and in range. 

Vehicle IP addresses are dynamically assigned when the operator laptop or vehicle connects to the router. IP addresses assigned by the router start at 192.168.1.100 and increase by 1 for each new device that connects. For example, the second device will have an IP address of 192.168.1.101. Dynamic IP address assignments persist for 24 hours or until the router is power cycled.

The following configuration steps set some IP addresses to static.

1. Verify that the wireless router, operator laptop, and vehicle are powered on.

2. Connect the laptop to the wireless network:

  * Network SSID: adapt

  * Network Password: adapt

3. On the operator laptop, set a static IP address of 192.168.1.200 for the adapt network wireless connection, with a 255.255.255.0 netmask.

4. Connect the operator laptop to the vehicle using the shore cable. The wired IP address of the vehicle defaults to 10.0.7.65. Set the IP address of the operator laptop for the wired network to 10.0.7.200. 

5. Using a terminal, connect to the vehicle (replace the IP address below with the IP address of the vehicle):
ssh root@192.168.1.101

6. Using vi, open:

  * /data/app/bluefin/opt/ros_xc/share/sandshark_common/launch/catkin_all.launch

7. Set the following parameters:

  * sendIPAddress = 192.168.2.200

  * secondarySendIPAddress = 10.0.7.200

8. Restart the vehicle using the magnet.

### Topside Software and SDK

The Sandshark requires an operator laptop running qgroundcontrol with a package of Bluefin modifications. The latest software topside distribution and development kit must be obtained from Bluefin. Installation instructions are distributed with the kit.

The general qgroundcontrol User Guide is available here:

http://qgroundcontrol.org/

Use the following values with the installation instructions:

* gssysID = 254

* name = adapt

* port = 14550

* targethost = 127.0.0.1:14555

### Accelerometer Configuration

The accelerometer configuration procedure uses a tool widget in qgroundcontrol. It requires a flat surface   and a way of supporting the vehicle while in a horizontal orientation. Remove the shore cable. The vehicle must be powered on and communicate with the operator laptop over wifi for this process.

The following steps must be performed once for each vehicle:

1. In qgroundcontrol, open the advanced menu and select tool widgets, then select load custom widget file.

2. Select “calibration.qgw” and click load. It now appears as a tool widget option in the menu.

3. Open the advanced menu and select tool widgets, then select calibration. The widget opens.

4. Place the vehicle in the foam with the top up. The antenna must point straight up and be perpendicular to the ground.

5. Click “Accel”.

6. Click the megaphone button.

7. A log window pops up. Follow the instructions, noting the following.

  * Turn to the left side: the antenna must be parallel to the ground.

  * Turn upside-down: the antenna must be perpendicular to the ground.

  * Turn to the right side: the antenna must be parallel to the ground.

  * Place on nose: remove hands from the vehicle before pressing accel

  * Place on tail: remove hands from the vehicle before pressing accel

### Magnetometer Calibration

The magnetometer configuration procedure uses a tool widget in qgroundcontrol. It requires a large open area without metal objects for a 25 meter or larger radius, and a way of supporting the vehicle while in a horizontal orientation. Remove the shore cable. The vehicle must be powered on and communicate with the operator laptop over wifi for this process.

The following steps must be performed once for each vehicle:

1. In qgroundcontrol, open the advanced menu and select tool widgets, then select load custom widget file.

2. Select “calibration.qgw” and click load. It now appears as a tool widget option in the menu.

3. Open the advanced menu and select tool widgets, then select calibration. The widget opens.

4. Place the vehicle in the foam with the top up. The antenna must point straight up and be perpendicular to the ground.

5. Click “Mag”. The widget begins taking 1000 samples. Pick up the vehicle, hold it in front of you and rotate and spin it through all orientations as the widget takes samples. Continually spin the vehicle along its nose to tail center line. Begin by rotating it around the X, Y, and Z axises, then rotate it through the non-plane space until it finishes taking samples. 

6. Stop when the message “Mag Cal Accepted” appears.

### Shore Cable Usage

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Always turn off the vehicle before connecting the shore cable.**

The shore cable connects the vehicle and the operator laptop and is used for faster transfer of data and large files. The vehicle end connects to the payload connector on the tail section endcap. The laptop end connects to the laptop’s ethernet port.

The vehicle’s wired IP address is set to 10.0.7.65.

## Heat Awareness

### Operating on Deck

Be mindful of heat, especially on a hot day. When running on deck, power off unnecessary payloads. Do not run the tailcone in air for longer than 5 minutes.

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: If the vehicle overheats, pour water over the tailcone section aft of the antenna until it cools.
If extended operation in air is required, a hose can be used to help limit tailcone temperatures.**

### Operating in Water

When running in water, monitor the temperature sensors when able to communicate with the vehicle.

## Range Awareness

The vehicle has a maximum range of 24 nautical miles and maximum speed of 4 knots. Omnidirectional wifi has a range of 100 meters. The vehicle can drive outside the wifi communications range in less than one minute.
Bluefin strongly recommends installing an emergency locator device in the payload section of the Sandshark. Some options include:

* RDF beacon: can be tracked using a handheld RDF unit on the search vessel to provide the relative bearing of the UUV. The RDF beacon only works when the UUV is at the surface. 

* UAT-376 transponder: can be tracked using a handheld dive range interrogator held in the water. Provides relative bearing and distance. The UAT-376 works when the transponder is submerged. It should be mounted as low as possible in the payload to continue working at the surface.

If no emergency locator device is installed, using binoculars and a panel unidirectional wifi antenna can increase the search and communications range.

During testing and the pre-dive checkout, the vehicle should be leashed by tying a line to the vehicle handle and tying the other end down on deck.

## Preparing for a Mission

### Ballasting and trimming the vehicle

The vehicle must be ballasted and trimmed correctly to provide a stable base for data gathering. See “Trim Instructions” on page 91. for detailed trim instructions.
<xref>

User-defined payload modules should fit inside a 4-7/8” OD shell, weigh less than 7.5 lb (3.3 kg), and be shorter than 23 inches (.58 meters) including the nose or shorter than 19 inches (.48 meters) if using the Bluefin nose. 

**Table: Properties of UUV with Empty Payload**
| Property	| Value |
|--- | ---|
| Mass	| 12.5 lb (5.7 kg) |
| Length	| 40 inches (1 meter) |
| Diameter	| 4-7/8” (125 mm) |

###Turning vehicle on

![Warning](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-warning.jpg)	**WARNING: Verify that all hands are clear of the propeller before turning on the vehicle.**

To turn on the vehicle, pass one end of the neodymium magnet over the magnetic switch in the aft upper corner of the antenna. If the green LED does not flash, pass the other end of the neodymium magnet over the switch. The green LED flashes during power up and turns solid when the vehicle is ready to operate.

### Planning a mission

Missions are planned in qgroundcontrol. Missions consist of waypoints the vehicle transits between at a default speed set for the entire mission.

Double-click on the map to create a waypoint. Select “Edit Waypoint” and set a depth and capture radius for the waypoint. The capture radius is how close the vehicle must be to the waypoint before it starts turning to the next waypoint. 7 meters is the Bluefin recommended capture radius value.

When the mission plan is complete, click “Set” in the lower right corner to send it to the vehicle.

Click “Refresh” in the lower right corner and check the “Onboard Waypoints” list. “Onboard Waypoints” are the waypoints loaded in the vehicle’s memory. If they do not match the mission plan, click “Refresh” until they do.

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: qgroundcontrol does not know the vehicle’s operational limits. When the vehicle reaches its operational limits it aborts and surfaces.**

**The vehicle must surface for GPS updates at regular intervals. This distance is configurable, but if updates are set too far apart the vehicle may travel outside the expected operations area. (Default: 90 seconds)
GPS checks override the mission plan.**

### Vehicle Safety Parameters and Limits

The vehicle is pre-programmed with safety parameters and limits. If the Bluefin defaults are not suitable for an application or payload, contact Bluefin for vehicle tuning instructions.

The key limits are:

* Diving: vehicle cannot dive in less than 80 inches (2 meters) of water

* Flight: vehicle’s minimum altitude is 40 inches (1 meter) above the seafloor

* Depth: vehicle cannot dive below 330 feet (100 meters)

* GPS surfacing: Every 90 seconds (configurable)

* Minimum stable speed: 1 knot

* Maximum speed: 4 knots

* Maximum range at 3 knots: 24 nautical miles

* Heat abort: the vehicle will automatically abort and surface if it overheats

* Battery abort: the vehicle will abort and surface at 10% of battery life remaining

### Pre-Dive Checklist

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Always pick up the vehicle by the handle or by gripping the hull. The tailcone, antenna, and fins cannot support the weight of the vehicle.**

The pre-dive checklist is used to check the vehicle status and readiness for a mission. A blank pre-dive checklist is located in “UUV Checklists” on page 71.
<xref>

The pre-dive checklist contains verification tasks on land and in water. Tie a line to the vehicle handle and tie the other end of the line down on deck before putting the vehicle in the water for the pre-dive checklist. remove the line only when the vehicle has passed the checklist.

## Operating the Vehicle

### Dive Log

The dive log (also called the ops mission template) is used to record vehicle mission properties, statuses, and events. A blank dive log is located in “UUV Checklists” on page 71.
<xref>

## Starting a Mission

First, pass the pre-dive checklist and verify that the mission has been uploaded to the vehicle. Untie the line from the vehicle handle that is leashing the vehicle to the deck. In qgroundcontrol, go to the ADAPT tab and press “DIVE”.

<image>
**Figure: DIVE Button**

### Monitoring a Mission

WiFi does not work under water. The vehicle can only be monitored while it is at the surface. The vehicle surfaces regularly (at a configurable interval, default 90 seconds) to acquire a GPS location. If it is within wifi range when it surfaces, then the vehicle status will update in qgroundcontrol and commands can be transmitted to it.

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: WiFi does not work underwater.**
 
 **GPS checks override the mission plan.**

### How to end a mission

To abort a mission, issue an “ASCEND TO SURFACE” command in qgroundcontrol while the vehicle is at the surface and in wifi range.

<image>
**Figure: ASCEND TO SURFACE Button**

### Propulsion Motor Special Considerations

If the propeller does not start moving when it is expected to, insert a stick in the propeller and push it clockwise until it turns on its own. Never use a body part to rotate the propeller.

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Do not touch the propeller with any body part when the vehicle is powered on.**

### Vehicle Location and Recovery

At the end of a mission the UUV is typically located either at the recovery location, by seeing the strobe light, or by using omnidirectional wifi communications from the operator laptop. If the UUV cannot be located through these methods it can be located using the procedures described in “Emergency Procedures” on page 41.
<xref>

Bluefin strongly recommends installing an emergency locator device in the payload section of the Sandshark. Some options include:

* RDF beacon: can be tracked using a handheld RDF unit on the search vessel to provide the relative bearing of the UUV. The RDF beacon only works when the UUV is at the surface. 

* UAT-376 transponder: can be tracked using a handheld dive range interrogator held in the water. Provides relative bearing and distance. The UAT-376 works when the transponder is submerged. It should be mounted as low as possible in the payload to continue working at the surface.

If no emergency locator device is installed, using binoculars and a panel unidirectional wifi antenna can increase the search and communications range.

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Always pick up the vehicle by the handle or by gripping the hull. The tailcone, antenna, and fins cannot support the weight of the vehicle.**

## Post-mission Activities

### Downloading Data

Payload data is stored in /mnt/sdcard on the vehicle. Use scp to copy it from the vehicle to the operator laptop. Instructions for using scp are available here:

http://manpages.ubuntu.com/manpages/precise/en/man1/scp.1.html

Data download is faster over the shore cable than over wifi.

### Viewing ROS Data

The user should use their preferred ROS data tools to view and analyze the ROS data. For options and guidance, see the following websites:

https://cse.sc.edu/~jokane/agitr/

http://www.ros.org/about-ros/

http://www.ros.org/core-components/

### Shutting Down the Vehicle Safely

Pass one end of the neodymium magnet over the magnetic switch in the aft upper corner of the antenna. If the LEDs do not turn off, pass the other end of the neodymium magnet over the switch.

### Freshwater Rinse

At the end of the operations day the vehicle fairing must be rinsed with fresh water. See “Preventive Maintenance Procedure” on page 30.
<xref>

## Preventive Maintenance Procedure: Fresh Water Rinse

### Tools and Equipment Required

* Fresh Water Source

* Water Hose

* Sponge or Cloth Rags

* Towels

### Background Information

The fresh water rinse cleans the exterior of the vehicle after each dive.

### Description of Work

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Do not power wash the AUV or its components as this may cause damage to the AUV or its components.**

*Note: Do not let the fresh water hose run when not in use. Use the minimum necessary for the task. Always secure the hose when it is not being used.*

1. Rinse the outside of all fairings with fresh water.

2. Wipe down surfaces with a sponge or cloth rag.

3. Starting with the tailcone, rinse all component subsystems with fresh water.

4. Separate the tail section from the payload section by removing the ortman key.

5. Rinse the front endcap of the tail section. The depth sensor hole in the center of the lower half must be flushed with fresh water.

This completes the fresh water rinse of the AUV.


# Power

The battery used by the Sandshark is a rechargeable 225 Wh Lithium Ion battery with cells encased in Phase Change Material (PCM), which absorbs excess heat to limit risk of a thermal event.

## Charging the Vehicle

To charge the vehicle, connect the charging brick to the vehicle’s charging connector, as shown in the figure below. The battery charges at a 2 amp rate and will automatically stop charging when it is full. Charging a completely depleted battery takes 4 to 6 hours. The battery can be safely left connected to the charger after charging is completed, but should be taken off the charger after 12 hours.

<image>

**Figure: Charging the Vehicle**

## Battery Details

The battery is a 225 Wh Li Ion battery made of Li Ion cells embedded in PCM, a heat absorbing material. PCM and the control circuitry protect it against over-voltage, over-current, under-voltage, over temperature, and under-temperature events. It automatically cell-balances during charging. It is rated for storage from -25°C to 85°C.

## UN 38.3 Certificate

The battery is UN 38.3 certified. The testing report is included in the technical information package.
Lithium ion batteries must have a UN 38.3 certification to be shipped commercially. They are dangerous goods and must be packed by hazmat-certified personnel for air freight shipment. Non-hazmat certified personnel may pack the batteries for ground shipping, but they must be labeled according to UN specifications.

The battery must be shipped class 9 Hazmat.

## Long Term Storage

### Optimizing Battery Life-Span

Charge and discharge rate, cell voltage, temperature, cell age and number of cycles all contribute to the battery lifetime. The capacity of all batteries reduces over time.

Capacity is dependent on the number of charge and discharge cycles, rate, and temperature. Each cycle reduces the amount of available capacity. Capacity fades faster when cells are maintained at a high state of charge (SOC) and at a higher temperature, or when cells are held at low temperature and low SOC. In general, batteries that are charged and discharged at a lower rate preserve their capacity longer. 

Batteries left uncycled for more than 3 months should be connected to shore power to allow for the cells to rebalance and prevent cell damage.

Worst case conditions that reduce capacity (in order of worst first):

* Storing cells at elevated temperature at 100% SOC.

* Storing cells at a cold temperature at 0% SOC

* Storing cells at cold temperature at 100% SOC.

### Preventing Damage Through Overdischarge

The battery electronics prevent overcharging but cannot prevent over discharging in storage as all lithium polymer cells exhibit self-discharge. Over time, the cells in the battery pack could discharge below a threshold that could cause damage. Additionally, the electronics pack draws a minute amount of current in the inactive state. Ensure that the batteries are monitored monthly. If the voltage drops below 21 V, recharge the batteries to 25-26 V (60% SOC).

## Packing and Shipping the Battery

This procedure applies only to shipments in 2015. A revised procedure is under development. Contact Bluefin for more information.

The battery must be removed from the vehicle and shipped according to UN 3480 regulations.

For air shipment, the battery must be shipped by trained personnel with a Hazmat endorsement.

For ground shipment, the battery can be shipped by non-Hazmat personnel with the labeling listed in the steps below.

1. Verify that the battery has been discharged to shipping/storage capacity (25 V, 60% SOC).

2. Turn the vehicle off.

3. Separate the battery and control housing subsection from the fin housing subsection.
<xref> See “Section Separating Procedure” on page 55.

4. Slide the battery chassis out of the housing.

5. Disconnect the C-Grid connector from the 8-pin mini-fit-jr. socket on the top side of the battery to disable the battery.

<image>

  **Figure: Battery Cables**

6. Disconnect the 3-pin mini-fit-jr connector from the same socket by pressing the clip and pulling straight out.

7. Remove the ribbon cable from battery chassis.

8. Lift the battery out of the chassis.

9. Stow the ends of the cables in the battery chassis. Slide the chassis back into the battery and control housing.

10. Attach the battery and control housing subsection to the fin housing subsection.
<xref> See “Section Attachment Procedure” on page 54.

11. Prepare the shipping box by filling the excess space with honeycomb fiberboard inserts.

<image>
  **Figure: Prepared Shipping Box**

12. Insert the battery in a 3 mil thick plastic bag and roll the top closed.

13. Place the wrapped battery in the shipping box, circuit board facing the side.

14. Fill in any gaps around the battery with smaller honeycomb fiberboard inserts. Verify that the battery cannot move in the box.

15. Place a honeycomb fiberboard insert on top of the battery.

16. Place the shipping paperwork in the box.

17. Close and seal the box with packing tape.

18. Ensure that the shipping box is labeled with the following labels on 2 opposite sides (4  labels per side):

<image>
  **Figure: Class 9 Label (black and white)**

<image>
  **Figure: This Side Up**

<image>
  **Figure: UN 3480 Lithium Battery**

<image>
  **Figure: 24 Hour Emergency Contact Information Label**

19. If the person packing the battery has a Hazmat certificate, apply the following label on 2 opposite sides:

<image>
  **Figure: Cargo Aircraft Only Label (orange)**

20. If the person packing the battery does not have a Hazmat certificate, apply the following label on 2 opposite sides:

<image>
  **Figure: LITHIUM BATTERIES - FORBIDDEN FOR TRANSPORT ABOARD AIRCRAFT AND VESSEL**

21. Write “235 Wh” on the sides with the labels.

22. Apply a shipping label.

23. Ship according to your internal shipping procedures and applicable laws and regulations.

This completes the battery packing and shipping procedure.

## Unpacking the Battery

This procedure applies only to shipments in 2015. A revised procedure is under development. Contact Bluefin for more information.

1. Open the cardboard box and process or file the shipping paperwork.

2. Remove packing material until the battery is visible.

3. Do not touch or hold by the circuit board. Lift the battery out of the box.

4. Save the box and packing material.

5. Insert the battery in the battery chassis with the 8-pin mini-fit-jr connector facing up.The battery circuit board faces 
aft. The large circuit board on the chassis faces aft.

6. Two battery cables are connected to the endcap. Pull the free ends aft.

7. Gently press the 3 pin mini-fit-jr connector into the left side of the 8-pin mini-fit-jr socket on the battery circuit board until it is fully seated and the clip clicks.

<image>
  **Figure: Battery Cables**

8. Gently press the 3-pin C-grid connector into the right side of the 8-pin mini-fit-jr socket.

9. Slide the battery in the battery chassis into the battery and control housing.

10. Attach the battery and control housing subsection to the fin housing subsection.
<xref>See “Section Attachment Procedure” on page 54.

This completes the procedure for unpacking the battery.

# Emergency Procedures

## Introduction

At the end of a mission the UUV is typically located either at the recovery location or by using omnidirectional wifi communications from the operator laptop. If the UUV cannot be located through these methods it can be located using the procedures described in this section.

Locating an UUV that is on the surface or submerged can be a very difficult task under the best of circumstances. Factors contributing to this problem are weather, currents, thermoclines, visibility, and the fact that the low freeboard of an UUV make it difficult to see over large distances. 

To aid in the location of an UUV, a strobe light is installed in the UUV. The strobe light on the UUV antenna flashes (when not disabled by the operator during mission planning) at a configurable rate. The strobe light is normally only visible when the UUV is at the surface. Under favorable conditions (such as: night-time; low ambient light; less than 50 ft water depth; clear water), the strobe light can provide a visual indicator of the UUV’s general location even when the UUV is submerged.

Bluefin strongly recommends installing an emergency locator device in the payload section of the Sandshark. Some options include:

* RDF beacon: can be tracked using a handheld RDF unit on the search vessel to provide the relative bearing of the UUV. The RDF beacon only works when the UUV is at the surface. 

* UAT-376 transponder: can be tracked using a handheld dive range interrogator held in the water. Provides relative bearing and distance. The UAT-376 works when the transponder is submerged. It should be mounted as low as possible in the payload to continue working at the surface.

If no emergency locator device is installed, using binoculars and a panel unidirectional wifi antenna can increase the search and communications range.

## When is an UUV “Missing” ?

For the purposes of this section, the UUV is considered missing if the following conditions apply:

* The UUV cannot be located visually at its expected location (after an aborted or completed mission)

* The UUV is out of range of the omnidirectional wifi communications.

### Loss of Visual Contact on the Surface

One of the most difficult tasks during operations is locating the UUV on the surface after it has completed its mission. Sea-state and weather can make this even more difficult. Recording the expected end of dive location in the Dive Log is imperative in simplifying this task.

Where practical, the search vessel should transit to a point near the expected end of dive location prior to the end of the dive, and a keen lookout should be kept to try to spot the vehicle as soon as it surfaces.

In the event that the UUV is not visible due to sea-state or sun glare and outside the omnidirectional wifi range, the emergency locator (if installed) should be used to determine the relative direction of the vehicle. The ship should then proceed cautiously in that direction with lookouts posted. If there is no emergency locator, use a panel unidirectional wifi antenna and slowly rotate the antenna in a circle until communications are established.

If the UUV cannot be visually located during night operations, the strobe light (assuming it has not been disabled during mission planning) may be sufficiently bright to determine the general vicinity of the UUV.

The strobe is independently powered and designed to operate for several days on its own batteries.

### Loss of Communications 

One of the most common problems anticipated during UUV operations is loss of wifi communications between the search boat and the UUV. This failure can be due to distance, environmental effect or equipment malfunction. 

The range of an omnidirectional wifi antenna is about 100 meters maximum and the range of a panel unidirectional wifi antenna is about 1000 meters maximum, depending on environmental conditions and height of the antenna. The effects of increased sea-state can dramatically decrease the usable range of the system. Sea-state can also submerge the UUV’s antenna more than normal causing the wifi to drop out. To re-establish communications, it may be necessary to close the distance to the last known position of the UUV on the surface or to the projected position that the UUV would be at that point in time during the mission. 

The ways in which the UUV can be located are discussed in the sections that follow.

## Using Search Boat Position and Range to Locate the UUV

If the UUV’s wifi or emergency locators are still powered, even if status updates are not functioning, appropriate topside equipment can be used to obtain direction and position information from these devices. This procedure will describe how to use the search boat’s position and range information to locate the UUV.

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: If contact is made with a missing vehicle, immediately issue a LAND command from qgroundcontrol to bring it to the surface, otherwise it might drive out of wifi range. Note that it could take several minutes for the vehicle to reach the surface depending on the vehicle depth at time of LAND command. The vehicle rises approximately one foot/sec. Immediately note the GPS position where contact is made in case the search boat moves or loses contact and needs to backtrack.**

To locate the UUV using the Search Boat Position and Range: 

1. Set up the operator laptop and launch qgroundcontrol.

2. Set up the topside equipment used to communicate with the emergency locator.

3. Obtain the first range reading from the topside communications equipment.

  *Note: Be aware that the vehicle may be on the bottom and therefore may show ranges no closer than the local water depth.*

4. Make an annotation on the chart of the search boat’s location and draw a circle with a radius equaling the range value around the search boat’s location.

5. Move the search boat to another position and take a new range reading. Make a new annotation as described in the previous step. Assuming the UUV has not moved significantly, there should now be two intersecting circles on the chart.

6.  Turn the search boat 90 degrees and drive to a third location and take a new range reading. Make a new annotation on the chart. There should now be three intersecting circles on the chart. The intersection of the three circles indicates the approximate position of the UUV.  (See Figure below.) 

<image>
  **Figure: Approximate Location of UUV at Intersection of Three Circles**

7. Place a new annotation at the approximate location of the UUV, and annotate it with something meaningful like “Location 1”. This marker will serve as a record of the first approximated location.

8. Drive the search boat to this location, keeping a keen lookout to avoid hitting the UUV with the search boat.
This procedure can be performed again with gradually smaller radius circles in order to accurately locate the UUV. If this procedure is performed correctly, the precise location of the UUV can be obtained in two hours or less. 

## Using the RDF Receiver to Locate the UUV

To locate the UUV using the RDF Receiver, the UUV must be on the surface, and sea state conditions must be favorable. The RDF Receiver tracks the RDF beacon in the UUV’s payload.

To locate the UUV using the RDF Receiver:

1. Slowly rotate the handheld RDF unit at 1-2 rpm until the strongest signal is received.

2. Follow the direction the unit is indicating while monitoring the strength of the reception. Increasing signal strength indicates that the distance to the UUV is closing.

3. Drive the vessel in a straight line. If the signal strength is increasing, continue in this direction. If the signal strength is decreasing, turn the vessel 90 degrees (port or starboard), and drive in a straight line.

4. Continue in this direction as long as the signal strength is increasing. If the UUV is sighted, drive toward it and recover. If the signal strength begins to decrease, the Closest Point of Approach (CPA) has been reached. Go to the next step.

5. Turn the vessel 90 degrees (pick either port or starboard). Observe the signal strength. If the signal strength is increasing, this is the correct direction. Continue closing in on the UUV. If the signal strength is decreasing, this is the wrong direction. Turn the vessel 180 degrees from the current heading, and repeat the previous step.

This procedure should quickly close on the vehicle position. 

## Using the Directional WiFi Antenna to Locate the UUV

To locate the UUV using the diretional wifi antenna, the UUV must be on the surface, and sea state conditions must be favorable.

To locate the UUV using the directional wifi antenna:

1. Slowly rotate the handheld wifi antenna at 1-2 rpm until the UUV conects to qgroundcontrol.

2. Follow the direction the unit is indicating while monitoring the strength of the reception. Increasing signal strength indicates that the distance to the UUV is closing.

3. Drive the vessel in a straight line. If the signal strength is increasing, continue in this direction. If the signal strength is decreasing, turn the vessel 90 degrees (port or starboard), and drive in a straight line.

4. Continue in this direction as long as the signal strength is increasing. If the UUV is sighted, drive toward it and recover. If the signal strength begins to decrease, the Closest Point of Approach (CPA) has been reached. Go to the next step.

5. Turn the vessel 90 degrees (pick either port or starboard). Observe the signal strength. If the signal strength is increasing, this is the correct direction. Continue closing in on the UUV. If the signal strength is decreasing, this is the wrong direction. Turn the vessel 180 degrees from the current heading, and repeat the previous step.

This procedure should quickly close on the vehicle position. 

## Using the Strobe or Other Visual Aids to Locate the UUV

Locating the UUV on the surface at night is probably one of the easiest methods of finding the vehicle. As long as the strobe is functional, the search vessel should be able to spot it from reasonably far distances. Strobe settings can be configured during mission planning. 

The strobe light is normally only visible when the UUV is at the surface. Under favorable conditions (e.g. night-time; low ambient light; less than 50 ft water depth; clear water), the strobe light can provide a visual indicator of the UUV’s general location even when the UUV is submerged.

Other mechanisms for locating the UUV visually at night are the application of highly reflective tape on the topside of the UUV fairings prior to deployment. Using a searchlight, the UUV can be easily spotted if the light shines on the reflective tape. 

Bluefin recommends the use of both the strobe and reflective tape to ensure the ability to locate the UUV visually at night.

# Maintenance Procedures

## Introduction

This chapter explains maintenance procedures required in normal operation.

Corrective maintenance procedures are performed on the vehicle system when operational tests, failure diagnosis, or other observations have detected a failure in the system that can be repaired by the vehicle operator or technician.

The Repair Manual contains only those intermediate level maintenance procedures which can be performed by the technician in a workshop or ISO van in the field. Bluefin-approved parts and procedures must be used to repair the MEH. Using unapproved parts and procedures will void the vehicle warranty.

More complex, or depot level corrective maintenance requires specialized equipment and extensive disassembly of vehicle components. Depot level maintenance is carried out by Bluefin Robotics, either on site or at Bluefin’s facilities.

## Fairings and Ortman Keys

Vehicle fairings are cast aluminum or abs plastic. Each section has ortman key grooves at the ends. When the cylindrical sections are pressed together to connect, the ortman key grooves form a channel for the ortman key. Inserting the teflon ortman key attaches the sections together. The ortman key is inserted through oblong holes in the fairing.

<image>
**Figure: Ortman Key Diagram**

<image>
**Figure: Ortman Key**

<image>
**Figure: Ortman Key Access Hole (Ortman Key End Visible)**

The vehicle can be operated with some damage to fairings, but must not be operated if there is any damage to sealing surfaces on the pressure vessel fairing.

## Procedure: Ortman Key Installation

### Tools and Equipment Required

* Needlenose Pliers

* Ortman Key

### Background Information

Teflon ortman keys are used to attach cylindrical vehicle sections together.

### Description of Work

1. If a section uses o-rings to seal out water, verify that they are there and in good condition.

2. Press the sections together so the ortman grooves line up and form a channel.

3. Insert the ortman key through one of the access holes in the fairing. Push it in. As the front end reaches each of the 4 
access holes, use needlenose pliers to guide it back in the channel and continue pushing the key in until it is fully inserted.

<image>
**Figure: Pliers and Access Hole**

This completes the ortman key installation procedure.

## Procedure: Ortman Key Removal

### Tools and Equipment Required

* Needlenose Pliers

### Background Information

Teflon ortman keys are used to attach cylindrical vehicle sections together.

### Description of Work

1. Grasp an end of the ortman key with needlenose pliers inserted in the access hole.

2. Pull the ortman key free of the vehicle.

This completes the ortman key removal procedure.

## O-Ring and Seal Maintenance

O-rings must be whole and in good condition. Inspect and lightly lubricate with DC-4 before use.

Dynamic seal maintenance cannot be performed by the customer. If a seal is leaking, contact Bluefin.

## Procedure: Attach Sections

### Tools and Equipment Required

* O-rings (BUNA-N, 2-044, 2-046)

* Ortman Keys

* DC-4

* Needlenose Pliers

### Background Information

This procedure applies to all sections and sub-sections attached with ortman keys. The tail section has 4 subsections: the tailcone, the fin housing, the battery and control housing, and the endcap.

### Description of Work

1. If a section has o-rings, verify that they are intact, in place, and lightly lubricated with DC-4. The following o-rings 
are in the tail section:

  * Fin housing aft: 2-044

  * Fin housing fore: 2-046

  * Endcap aft: 2-046

2. Slide the sections together so the ortman grooves align. Verify that the o-rings are not pinched or torn.

3. Install the ortman key.
<xref> See “Ortman Key Installation Procedure” on page 51.

This completes the section attachment procedure.

##Procedure: Separate Sections

### Tools and Equipment Required

* Needlenose Pliers

### Background Information

Sections are attached with an ortman key.

### Description of Work

1. Remove the ortman key.
<xref> See “Ortman Key Removal Procedure” on page 52.

2. Slide the sections apart.

This completes the section separating procedure.

## Procedure: Mate Connectors

###Tools and Equipment Required

* Canned Air

* 3M Silicone Spray

### Background Information

The tail section endcap has 2 Subconn connectors: a MCBH4F and a MCBH8F. They must be mated properly to a cable or dummy cap for vehicle operations in water.

### Description of Work

1. Spray the endcap connector and the cable connector with canned air.

2. Spray a light film of 3M silicone spray on the female connector on the endcap.

3. Align the pins and sockets on the 2 connectors and press the cable’s connector straight into the endcap connector until the faces are flush.

4. Tighten the plastic locking collar down.

This completes the connector mating procedure.

##Procedure: Unmate Connectors

###Tools and Equipment Required

* N/A

## Background Information

The tail section endcap has 2 Subconn connectors: a MCBH4F and a MCBH8F. 

## Description of Work

1. Loosen the plastic locking collar.

2. Grasp the cable by the connector and pull straight out.
This completes the connector unmating procedure.


## Procedure: Seal Tail Section

### Tools and Equipment Required

* Laptop

* Vacuum Pump

* Rare Earth Magnet

* Phillips Head Screwdriver

* O-Rings (BUNA-N; 2-044, 2-046)

* Ortman Keys

* Needlenose Pliers

* DC-4

* ROS Cheat Sheet:
http://services.informatik.hs-mannheim.de/~ihme/robotik_2014ws/01_ROScheatsheet.pdf

### Background Information

The cast aluminum tail section is a pressure vessel and must be properly sealed before operations in water. It has 4 subsections: the tailcone, the fin housing, the battery and control housing, and the endcap. Ideally, it operates with a 1-5 psi vacuum. If the vacuum does not hold, contact Bluefin.

### Description of Work

1. Attach the sections.
<xref> See “Section Attachment Procedure” on page 54.

2. Turn on the vehicle

3. Log in on the vehicle.

4. Monitor the pressure inside the MEH while performing the rest of this procedure. See the ROS cheat sheet for details:
rostopic echo /environmental/environmental

5. Using the Phillips head screwdriver, remove the vent screw on the endcap.

6. Hold the vacuum pump hose to the vent screw hole and pull a 1-5 psi vacuum.

7. Quickly replace and tighten the vent screw.

8. If the vacuum does not hold, contact Bluefin. The vehicle should not be operated in water.
This completes the tail section sealing procedure.

## Procedure: Replace Propeller

### Tools and Equipment Required

* Woodruff Key

* Retaining Ring (000-017-373)

* Retaining Ring Pliers

* Aquashield

* Cotton Swab

## Background Information

The propeller slides onto the propeller shaft and is held in place by a woodruff key and a retaining ring. The propeller’s central hole must be coated in aquashield where it touches the shaft.

This task must be performed on a workbench because the woodruff key falls out when the propeller is removed.

## Description of Work

1. Using retaining ring pliers, open and remove the retaining ring from the propeller shaft.

<image>
  **Figure: Retaining Ring**

<image>
  **Figure: Retaining Ring on Propeller Shaft**

2. Slide the propeller off the shaft. The woodruff key will fall out.

3. Prepare the new propeller by coating the inside of the center hole with aquashield.

4. Insert the woodruff key in the slot on the shaft, curved side in. Hold in place with a finger.

<image>
  **Figure:  Woodruff Key**

5. Align the notch in the propeller’s center hole with the woodruff key and slide it onto the propeller shaft and over the woodruff key. It will hold the woodruff key in place.

6. Using the retaining ring pliers, open a retaining ring and insert it on the shaft to hold the propeller in place. Verify that it is fully seated in the groove on the shaft and closes flat when the pliers are removed. Do not use a bent retaining ring.

This completes the propeller replacement procedure.

## Procedure: ReplaceDuct

### Tools and Equipment Required

* 4 screws: SCS3PL04012

* 3/32” T-Handle Hex Wrench

* Aquashield

* Cotton Swab

### Background Information

The duct slides onto the propeller shaft and is secured to the fairing with 4x 4-40 screws.

### Description of Work

1. Remove the propeller.
<xref> See “Propeller Replacement Procedure” on page 59.

2. Unscrew the 4 screws on the duct with a t-handle hex wrench.

<image> 
  **Figure: Location of Screws on Duct**

3. Slide the duct off the propeller shaft.

4. Apply Aquashield to the threads of the 4 screws.

5. Put 4 screws through the screw holes of the new duct.

6. Slide the duct onto the propeller shaft and align the screws with the mounting holes on the fairing.

7. Using a t-handle hex wrench, engage the 4 screws in the mounting holes, then tighten down in a star pattern.

8. Install the propeller.
<xref>See “Propeller Replacement Procedure” on page 59.

This completes the duct replacement procedure.

## Procedure: Replace Fin

### Tools and Equipment Required

*N/A

### Background Information

The 4 articulating fins are removed and inserted without tools. The two dowels on the fin’s pin connector are used to align the fin with the connector on the vehicle. When fully seated, a small gap remains between the blade of the fin and the vehicle fairing.

### Description of Work

1. Put the vehicle on a workbench on foam with u-shaped cutouts or a support rack.

2. Put one hand on the fairing to stabilize the vehicle.

3. Pull each fin straight out, one at a time.

4. Align the replacement fin so the dowels on the pin match the notch on the connector. Press in gently until the fin is  fully seated.

<image>
  **Figure: Dowels on Fin Pin and Connector Indent**

5. Repeat for each fin.

This completes the fin replacement procedure.




# Troubleshooting

## Introduction

This chapter explains some common causes of vehicle problems and how to correct them.

Corrective maintenance procedures are performed on the vehicle system when operational tests, failure diagnosis, or other observations have detected a failure in the system that can be repaired by the vehicle operator or technician.

This chapter contains only those intermediate level maintenance procedures which can be performed by the technician in a workshop or ISO van in the field. Bluefin-approved parts and procedures must be used to repair the pressure vessel. Using unapproved parts and procedures will void the vehicle warranty.

More complex, or depot level corrective maintenance requires specialized equipment and extensive disassembly of vehicle components. Depot level maintenance is carried out by Bluefin Robotics, either on site or at Bluefin’s facilities.

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Never unseal the pressure vessels outdoors.**

**All procedures in the Repair chapter are intermediate level maintenance. They can be performed in a properly equiped workshop or ISO van.**

**Use only Bluefin-approved parts and procedures. Using unapproved parts and procedures will void the vehicle warranty.**

## Roll and CB-CG Separation

Increase CB-CG separation to reduce roll and pitch instability.
<xref>See “Trim Instructions” on page 91.

## Brownout

Do not let the motor run if the propeller does not turn. Do not run the propeller for more than 5 minutes in air.
<xref> See “Propulsion Motor Special Considerations” on page 27.

## Magnetometer and Accelerometer Calibration

qgroundcontrol will accept any calibration above its minimum standards. Repeat the calibration, noting that:

* Accelerometer: keep the antenna as perpendicular or parallel to the gound as possible.

* Magnetometer: find an area without metal objects in a radius >25 meters, such as a large field.

<xref> See “Accelerometer Configuration” on page 21.

<xref> See “Magnetometer Calibration” on page 22.

## Waypoint Catch Radius

Bluefin suggests a catch radius of 7 meters.

If the vehicle circles and can’t find the waypoint, increase the catch radius.

If the vehicle turns away from the waypoint too soon, decrease the catch radius.

## Aborts and How to Deal With Them

If an abort occurs during a mission, the thruster will stop spinning and the vehicle will float to the surface with the red LED on. To check which abort occurred and at what time it transpired, rostopic echo the /health/last_abort topic. The possible aborts are enumerated in the table below, and corresponding causes and suggested troubleshooting steps for each abort are provided

The trigger value for each abort is configurable via the Parameters menu in QGroundControl. Bluefin recommends not changing these values unless absolutely necessary and after careful deliberation, as the defaults have been picked to prevent harm to the vehicle.

**Table: Aborts, Causes, and Troubleshooting**

| Abort	| Typical Causes	| Troubleshooting / Suggestions |
|--- | --- | --- |
| Over-temperature Abort	| Ambient pressure vessel temperature has risen too high	| This abort triggers if the ambient temperature inside the pressure vessel has exceeded 40°C. This typically only occurs if the vehicle is operated in air for an extended length of time. To cool the pressure vessel, either shut the vehicle down for around ten minutes, or place the vehicle into water |
| High Pressure Abort	| Ambient pressure inside the pressure vessel has risen too high, indicating a leak	| Bluefin typically operates its vehicles with a vacuum in the pressure vessel. The recommended vacuum for this system is an absolute pressure of 85 kPa.  The high pressure abort will occur if a pressure of greater than 90kPa is detected within the pressure vessel, as this indicates that a leak is present.  If Bluefin has stated that your vehicle should be run at with a vacuum, set the Low Pressure abort to 70 kPa so that it does not trigger.
When the high pressure abort occurs, immediately remove the vehicle from the water and check for water intrusion and leaks.  If no obvious issues are detected, use a vacuum pump to decrease the pressure in the pressure vessel until the /environmental/environmental pressure reading is at ~85 kPa.  Ensure that the vehicle can hold pressure for an extended period of time before continuing operations|
| Low Pressure Abort	| Ambient pressure inside the pressure vessel has dropped too low, indicating a leak	| If, due to a known sealing issue with your vehicle, Bluefin has recommended that you operate with positive pressure in the vehicle's pressure vessel rather than a vacuum, this abort will apply instead of the High Pressure one.  In this scenario, the High Pressure abort should be set to 120 kPa so that it does not trigger.  The low pressure abort occurs when the vehicle senses a lower than expected internal pressure, indicating that some air has leaked out of the pressure vessel.
In the event of a low pressure abort, immediately remove the vehicle from the water and check for leaks or water intrusion.  If there are no obvious physical issues with the pressure vessel, use a pump to increase the pressure inside the pressure vessel until the /environmental/environmental pressure reading is at ~108 kPa.  Ensure that the pressure is not dropping at over 1kPa / 10 hours before continuing operations |
| Low Altitude Abort	| Water depth different than expected, operator error when planning the mission	| This abort triggers when the vehicle senses that it is at an altitude lower than 1 meter in order to prevent accidental collisions with the sea floor.  If it occurs, double check that the mission was planned correctly and that the water depth is actually as deep as the charts state. |
| High Depth Abort	| Operator error when planning the mission	| The depth abort triggers when the vehicle reaches a depth greater than 100 meters to prevent the vehicle from exceeding its depth rating.  When the depth abort occurs, double check that the mission was planned correctly. |
| Low Battery Abort	| The battery's percent state of charge has fallen too low to continue the mission	| When the battery percent of charge falls below 5%, the low battery abort will trigger.  When the vehicle comes to the surface, charge the battery before continuing operations |
| Mission Length Abort	| The vehicle was physically stuck during part of the mission, operator error when planning the mission	| The mission length abort triggers when a mission has been running for an amount of time longer than this threshold is set to.  If it occurs, double check that the planned mission can actually be completed within the allotted time slot and adjust it accordingly.  Additionally, the mission data should be checked to ensure that the vehicle is not getting stuck during any point in the mission.  One example would be if a waypoint was planned with a capture radius smaller than necessary, the vehicle might have to loop around it several times before considering it as having been reached |
| Leak Abort	| Water intrusion into the pressure vessel	| This abort occurs when the leak sensor inside of the pressure vessel has detected water intrusion.  Immediately remove the vehicle from the water and verify that no water is entering the pressure vessel before continuing operations |
| Navigation Integrity Abort	| Sudden jerk or twist of the vehicle during a mission, loss of altimeter or depth sensor communications, detection of impossible vehicle dynamics	| Download the vehicle data and view the /navigation/navState publication throughout the mission.  This publication contains a detailed string as to why this abort occurs.  If impossible vehicle dynamics or sudden jerks or twists have occurred, ensure that the area of operations is free of anything that could hit the vehicle during its mission such as a boat or a steep slope on the sea bed.  If any sensor data was lost, power cycle the vehicle and ensure the vehicle comes up in the running state with the green LED on before running another mission |


# UUV Checklists

This appendix contains the following UUV checklists:

* Sandshark Pre-Dive Checklist

* Sandshark Dive Log

* Sandshark Post-Dive Checklist

* Sandshark Mobilization Checklist



# External Interface

This appendix contains information on the external connectors to the pressure vessel.

<image>
**Figure: Pressure Vessel Endcap**

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: During underwater operation, the external connectors must be mated to a cable or dummy cap.**

## Charge Connector

The charge connector is a wet-mateable Subconn Micro MCBH4F. Always install a dust cover or dummy cap when not in use.

<image>
**Figure: Charge Pinout**

## Payload Connector

The payload connector is a wet-mateable Subconn Micro MCBH8F. Always install a dust cover or dummy cap when not in use.

<image>
**Figure: Payload Pinout**

## Payload Integration

For payload integration support, contact Bluefin Robotics at support@bluefinrobotics.com.





# Topside Equipment

This appendix contains information on the topside equipment used to operate and maintain the Sandshark Prototype.

## WiFi Usage

The Linksys wireless router provided with the system has omnidirectional antennas and a range of 100 meters. 

<image>
**Figure: Wireless Router**

## Charging Brick

The charging brick is a standard laptop charging brick with a 4-pin connector to connect to the vehicle.

<image>
**Figure: Charging Brick**

<image>
**Figure: Connector**

## Shore Cable

![Caution](https://github.com/jmurphy-bluefin/Technical-Publications-Test/blob/master/Images/icon-caution.jpg)
 **CAUTION: Always turn off the vehicle before connecting the shore cable.**

The shore cable connects the vehicle and the operator laptop and is used for faster transfer of data and large files. The vehicle end connects to the 8-pin payload connector on the tail section endcap. The laptop end connects to the laptop’s ethernet port.

The vehicle’s wired IP address is set to 10.0.7.65.

## Laptop

The operator laptop is not included in the Bluefin-provided equipment. The customer laptop used to operate the vehicle must run Ubuntu 14.0.4.

## Joystick

The joystick is a Playstation 3 controller or any standard controller with a USB interface. It can be used to drive the vehicle on the surface while in wifi range.

## On/Off Magnets

The hall latch magnetic ON/OFF switch in the aft upper corner of the antenna is operated by neodymium magnets.

To turn on the vehicle, pass one end of the neodymium magnet over the magnetic switch. If the blue LED does not turn on, pass the other end of the neodymium magnet over the switch.

Placing the NORTH side of a magnet over the hall latch will turn ON the vehicle. Placing the SOUTH side of a magnet over the hall latch will turn OFF the vehicle. 

The hall switch responds to magnetic flux densities of 15mT or more. Magnets are provided with the topside equipment. Avoid placing the magnet near the vehicle's tail section as this can affect the on-board compass.

<image>
**Figure: Turning on the Vehicle**

<image>
**Figure: Magnet**

## O-Rings

The table below lists the o-rings in the spares kit.

**Table: O-Ring Spares Kit** 
| Bluefin No.	| Description	| QTY |
|--- | --- | --- |
| 000-019-117	| O-RING, 2-044, 3.739 ID, 3.879 OD, .070 WD, BUNA-N |	
| 000-017-504	| O-RING, 2-046, (4.239ID X .070W) PER MIL-G-21569B CLASS 1, BUNA-N	|

## Tool Kit List

The table below lists the contents of the Tool Kit.

*Note: All hex screws involved in routine maintenance are 3-32.*

**Table: Tool Kit List**
| Supplier	| Supplier PN	| Description	| QTY |
| --- | --- | --- | --- |
| McMaster-Carr	| 7127A37	| SCREWDRIVER, PHILIPS BLADE	| 1 |
| McMaster-Carr	| 5709A52	| HEX SET, BALL END, IMPERIAL	| 1 |
|	|	| Needlenose Pliers	| 1 |
|	|	| Retaining Ring Pliers | * | 	
|	|	| Extension Cord	| 1 |
*Not provided by Bluefin.

## Spares List

The table below lists the contents of the Spares Kit.

**Table: Spares Kit List** 
| Supplier	| Supplier PN	| Description	| QTY |
| --- | --- | --- | --- |
|	|	| Extra #4 hardware	| |
|	|	| Ballast Weights	| |
|	|	| Foam	| |
|	|	| Ortman Keys | |	
|	|	| Rare Earth Magnets | |	
|	|	| Low Speed Fins	| 4 |
|	|	| High Speed Fins	| 4 |
|	|	| Dummy plugs and locking rings	| |


## Consumables List

The table below lists the consumable supplies and vendor information.

**Table: List of Consumables**
| Bluefin Part Number	| Description	| CANNOT SHIP VIA AIR? |
| --- | --- | --- |
| 000-001-461	| LUBRICANT, AQUASHIELD, 8OZ TUBE	| |
| 000-001-245	| ELECTRICAL INSULATING COMPOUND,DOW CORNING 4 | |	
| 000-007-004	| TAPE, ELECTRICAL 3/4" WD X 66'L, BLACK, SCOTCH BRAND	| |
|	| Gorilla Tape | |	
| 000-004-732	| Scotch 23 rubber splicing tape	| |
| 000-006-280	| LUBRICANT, SILICONE, 3M, 13-1/4 OZ, AEROSOL SPRAY CAN	| CANNOT SHIP VIA AIR |
| 000-004-752	| TIE WRAP, 11", BLACK, HEAVY DUTY, PACKAGE  50 | |	
| 000-004-754	| TIE WRAP, 4", BLACK,LIGHT DUTY, PACKAGE 100	| |
| 000-004-757	| TIE WRAP, 5.5 ", BLACK, MED DUT, PACKAGE 100	| |
| 000-006-281	| DUSTER, ELECTRICAL CLEANING, 8 OZ AEROSOL SPRAY CAN	| CANNOT SHIP VIA AIR |


# Trim Instructions

This appendix contains the trim and ballast instructions. 

## Payload Section

Wet payload sections should contain internal mounting points with a zip-tie hole. Use zip-ties to attach foam and ballast weights. Generally, foam should be in the top half of the section and ballast weights in the bottom half. For dense, heavy payloads, foam may need to fill all free space in the section.

Dry payload sections should contain external mounting points similar to the tail section mounting points. See “Tail Section” on page 92.
<xref>

Trim options (inside the hull):

* Add or remove ballast to points on the sides of the bottom hull to correct roll.

* Add ballast to the center bottom of the hull and foam to the center top of the hull to increase CB-CG separation and stabilize the vehicle’s flight.

* Remove ballast from all points to reduce weight.

* Add foam to the top half of the hull to increase buoyancy.

* Add foam or ballast as far forward as possible to correct pitch.

## Tail Section

The tail sections has 3 ballast mounting points on the endcap. Each point can hold 2 ballast disks. The ballast is attached to the endcap with a washer and screw. 

No foam can be added to the tail section.

Trim options:

* Add or remove ballast from the port and starboard points to correct roll.

* Add ballast to the center point to increase CB-CG separation and stabilize the vehicle’s flight.

* Remove ballast from all points to reduce weight.

<image>
**Figure: Ballast Mounting Points**

** Table: Ballast Disks and Harware**
| Part Number	| Description |
| --- | --- |
| 000-016-747	| BALLAST WEIGHT, BRASS, 1.000 DIA, 25G |
|	| WASHER, SPLIT LOCK, .112 NOM (#4), 316SS |
| SCS3PL04024	| SCREW, SKT HD CAP, .112-40 UNC-2A X .75L, 316SS |


