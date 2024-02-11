# Software Requirement Specification (SRS) Document

---

</br></br></br></br>

<div style="text-align:center;">for</div>

</br><h2 style="text-align:center;">HMS-Plus!</h2>

</br></br></br></br></br></br></br></br></br></br>

<div style="margin-left: auto; margin-right: auto; width: 70%">

| Document ID:    | SOFTWARE-REQUIREMENT-SPECIFICATION-V0.2.0 |
| --------------- | ----------------------------------------- |
| Version Number: | 0.5.1                                     |
| Issue Date:     | TBA                                       |
| Classification: | Draft                                     |

</div>

</br></br></br></br></br></br></br></br></br></br>

<p style="text-align:center;">Copyright © 2024, Soumyajit Kolay and Saurav Kumar.</p>

<div style="page-break-after: always; visibility: hidden; color: #000;">\pagebreak</div>

# License

BSD 3-Clause License

Copyright (c) 2024, Soumyajit Kolay and Saurav Kumar.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

---

# Revision History

| Date       | Version | Description                                       | Author(s)       |
| ---------- | ------- | ------------------------------------------------- | --------------- |
| 11-02-2024 | 0.6.1   | Minor Changes in System Features and Requirements | Soumyajit Kolay |
| 11-02-2024 | 0.6.0   | Added Overall Description                         | Soumyajit Kolay |
| 04-02-2024 | 0.5.1   | Updated Interfaces, Removed unneccessary portions | Soumyajit Kolay |
| 04-02-2034 | 0.5.0   | Added external interfaces                         | Saurav Kumar    |
| 04-02-2024 | 0.4.0   | Added Acronyms and Abbreviations                  | Saurav Kumar    |
| 03-02-2024 | 0.3.0   | Added intended audience                           | Saurav Kumar    |
| 01-02-2024 | 0.2.0   | Added Proposal, scope and removed references      | Saurav Kumar    |
| 28-01-2024 | 0.1.1   | Added ToC, License, and Minor Template Changes    | Soumyajit Kolay |
| 27-01-2024 | 0.1.0   | Baseline SRS Template Added                       | Soumyajit Kolay |

<div style="page-break-after: always; visibility: hidden; color: #000;">\pagebreak</div>

# Table of Contents

- [Introduction](#introduction)
  - [Purpose](#purpose)
  - [Intended Audience](#intended-audience)
  - [Project Scope](#project-scope)
  - [Acronyms and Abbreviations](#acronyms-and-abbreviations)
- [Overall Description](#overall-description)
  - [Product Perspective](#product-perspective)
  - [Product Features](#product-features)
  - [User Classes and Characteristics](#user-classes-and-characteristics)
  - [Operating Environment](#operating-environment)
  - [Design and Implementation Constraints](#design-and-implementation-constraints)
  - [User Documentation](#user-documentation)
  - [Assumptions and Dependencies](#assumptions-and-dependencies)
- [System Features](#system-features)
  - [System Feature 1](#system-feature-1)
    - [Description and Priority](#description-and-priority)
    - [Stimulus/Response Sequences](#stimulusresponse-sequences)
    - [Functional Requirements](#functional-requirements)
  - [System Feature 2](#system-feature-2)
- [External Interface Requirements](#external-interface-requirements)
  - [User Interfaces](#user-interfaces)
  - [Hardware Interfaces](#hardware-interfaces)
  - [Software Interfaces](#software-interfaces)
  - [Communication Interfaces](#communication-interfaces)
- [Other Non-Functional Interfaces](#other-non-functional-interfaces)
  - [Performance Requirements](#performance-requirements)
  - [Safety Requirements](#safety-requirements)
  - [Security Requirements](#security-requirements)
  - [Software Quality Attributes](#software-quality-attributes)
  - [Miscellanous Requirements](#miscellanous-requirements)

<div style="page-break-after: always; visibility: hidden; color: #000;">\pagebreak</div>

# Introduction

## Purpose

The purpose of this document is to establish how the application should interact with the end user,
and establish all application requirements functional, and non functional. Once finalized, this
document will state what must be accomplished for the application to be considered finished.

## Intended Audience

The primary audience for the Hotel Management System encompasses professionals within the hospitality industry, specifically targeting hospitality firms ranging from boutique hotels to large-scale resorts. This software solution is meticulously designed to digitally cater to the basic needs of a hospitality organisation.

## Project Scope

This project is intended to be used only for demonstration of our technical skills and our ability to create documented projects. It has no target users and hence the development is planned as per the developers' intuition.

## Acronyms and Abbreviations

| Term      | Description                                  |
| --------- | -------------------------------------------- |
| HMS       | Hotel Management System                      |
| Hotel     | Hotels/Lounges/Resorts/Guest Houses          |
| Rooms     | Rooms of Hotels/Lounges/Resorts/Guest Houses |
| Customers | People staying in Hotel Rooms                |

---

<div style="page-break-after: always; visibility: hidden; color: #000;">\pagebreak</div>

# Overall Description

## Product Perspective

This project serves as a combination of softwares meant to digitalize Hotels, Lounges, Resorts and Guest Houses to help keep a track of their rooms and customers staying in their rooms, and help execute related business functions. This project also serves as a major improvement of "EasyHMS", which was a CLI-based barebones project.

## Product Features

Refer to [System Features](#system-features).

## User Classes and Characteristics

Users are supposed to be managers and/or staff of the Group of Hotels/Lounges/Resorts/Guest Houses. Users should belong to either of the 3 classes:

- _System Administrator:_ would be granted all rights of the Administrator, and the right to add/delete/modify users
- _Administrators:_ would be granted all rights of the Managers, and the right to add/delete rooms
- _Managers:_ would be only able to register new customer and checkout existing customers

## Operating Environment

- _Server:_ A multi-core machine/VM/Container running Java Runtime Environment v17 or later, and PostgreSQL (preferably EDB Distribution) v15 or later. No GPU or GUI capabilities required.
- _Client Machines:_ Preferably a Dual Core Windows/Linux/mac system running Java Runtime Environment v17 or later, with a Monitor, mouse and keyboard. Requires a minimum of integrated GPU connected to a display of (minimum) 1024x768 resolution to support the software's GUI. Touchscreen functionalities might be present to aid the users.

## Design and Implementation Constraints

The lack of real customers to ensure customer acceptance and/or clear requirements might reduce the overall usability of the project. No maintenance or support is guaranteed to be delivered by the developers of this project, apart from the documentation, source code and the binary distribution on a hosted Git Platform.

Limited scalability of the software might reduce the performance or hinder the enterprise-oriented functions if the used for a large Organisation comprising of a huge number of Hotels and/or hotel rooms.

## User Documentation

- Client side user manual
- Server hosting guide

## Assumptions and Dependencies

The would be a finite number of rooms and be used for a small number of Hotels, if not singular.The uptime, server availability and disaster recovery shall be handled by the Organisation(s) using this software product.

---

<div style="page-break-after: always; visibility: hidden; color: #000;">\pagebreak</div>

# System Features

## RDBMS

### RDBMS - Description and Priority

### RDBMS - Stimulus/Response Sequences

### RDBMS - Functional Requirements

## Server

### Server - Description and Priority

### Server - Stimulus/Response Sequences

### Server - Functional Requirements

## Client side GUI

### GUI - Description and Priority

### GUI - Stimulus/Response Sequences

### GUI - Functional Requirements

---

<div style="page-break-after: always; visibility: hidden; color: #000;">\pagebreak</div>

# External Interface Requirements

## User Interfaces

## Hardware Interfaces

Devices capable of Java Runtime Environment v17+ with keyboard, display and mouse.

## Software Interfaces

The following software(s) and/or libraries shall be used for the project:

- _Java Platform with Maven:_ For compilation, building and running the projects.
- _JavaFX:_ To enable GUI on Java Platform.
- _PostgreSQL:_ For RDBMS.
- _Spring Boot Framework:_ For back-end server.
- _PostgreSQL JDBC Driver:_ To connect the Java-based project to RDBMS.

## Communication Interfaces

To enable server-client communication, network is necessary. The server and the client computers chould be connected to the same WLAN/LAN via HTTP(S) and/or required protocols.

---

<div style="page-break-after: always; visibility: hidden; color: #000;">\pagebreak</div>

# Other Non-Functional Interfaces

## Performance Requirements

## Safety Requirements

## Security Requirements

## Software Quality Attributes

## Miscellanous Requirements

[User Documentation](#user-documentation)

---

Copyright © 2024, Soumyajit Kolay and Saurav Kumar.
