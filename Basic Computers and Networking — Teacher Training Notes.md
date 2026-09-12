# Basic Computers and Networking
## Teacher Training — Simple Explanation Notes

---

# Table of Contents

1. [Computer Fundamentals](#1-computer-fundamentals)
2. [Protecting a PC from Lightning and Power Outages](#2-protecting-a-pc-from-lightning-and-power-outages)
3. [Windows Operating System](#3-windows-operating-system)
4. [Linux Fundamentals](#4-linux-fundamentals)
5. [Excel Fundamentals](#5-excel-fundamentals)
6. [PowerPoint Fundamentals](#6-powerpoint-fundamentals)
7. [Web Browsers and Search Engines](#7-web-browsers-and-search-engines)
8. [Connecting a Device to the Internet](#8-connecting-a-device-to-the-internet)
9. [Antivirus and Malware](#9-antivirus-and-malware)
10. [Network Topologies](#10-network-topologies)
11. [Types of Networks](#11-types-of-networks)
12. [TCP/IP, IPv4, IPv6 and OSI Model](#12-tcpip-ipv4-ipv6-and-osi-model)
13. [Physical Routing and Switching Lab](#13-physical-routing-and-switching-lab)
14. [Two Routers and Two Switches](#14-two-routers-and-two-switches)
15. [Static Routing](#15-static-routing)
16. [Dynamic Routing — OSPF and EIGRP](#16-dynamic-routing--ospf-and-eigrp)
17. [VLANs and Inter-VLAN Communication](#17-vlans-and-inter-vlan-communication)
18. [Final Practical Project](#18-final-practical-project)

---

# 1. Computer Fundamentals

## 1.1 What is a Computer?

A computer is an electronic device that:

- Accepts input
- Processes information
- Stores information
- Produces output

The basic computer model is:

```text
INPUT
  |
  v
PROCESSING
  |
  v
OUTPUT
  |
  v
STORAGE
```

### Example

When we type `2 + 3`:

```text
Keyboard
   |
   v
Input
   |
   v
CPU processes the calculation
   |
   v
Result = 5
   |
   v
Monitor
```

---

## 1.2 What is Data?

Data is information that a computer can process.

Examples:

- Name
- Age
- Marks
- Photograph
- Video
- Sound
- Documents

Inside a computer, data is ultimately represented using **binary values**.

Binary uses:

```text
0
1
```

These are called **bits**.

---

## 1.3 Bit and Byte

### Bit

A bit is the smallest unit of digital information.

A bit can be:

```text
0
```

or

```text
1
```

### Byte

```text
1 Byte = 8 bits
```

Example:

```text
10110010
```

This contains 8 bits.

Common storage units:

```text
8 bits       = 1 Byte
1024 Bytes   ≈ 1 KB
1024 KB      ≈ 1 MB
1024 MB      ≈ 1 GB
1024 GB      ≈ 1 TB
```

---

# 2. Protecting a PC from Lightning and Power Outages

## 2.1 Why Does a Computer Need Power Protection?

Computers need stable electrical power.

Problems can occur because of:

- Power cuts
- Voltage fluctuations
- Power surges
- Lightning
- Electrical faults

These can potentially damage computer components or cause data loss.

---

## 2.2 Power Surge

A power surge is a sudden increase in electrical voltage.

For example:

```text
Normal voltage
      |
      |       Surge
      |         /\
______|________/  \________
```

A large surge can damage electronic components.

---

## 2.3 Surge Protector

A surge protector is designed to help protect connected equipment from voltage surges.

Example:

```text
Wall Socket
     |
     v
Surge Protector
     |
     v
Computer
```

---

## 2.4 UPS

UPS means:

**Uninterruptible Power Supply**

A UPS contains a battery.

Example:

```text
Electricity
     |
     v
    UPS
     |
     v
 Computer
```

When electricity goes off:

```text
Power fails
    |
    v
UPS battery
    |
    v
Computer continues temporarily
```

This gives the user time to:

- Save work
- Close applications
- Shut down the computer safely

---

## 2.5 Earthing

Earthing provides a safe path for unwanted electrical current.

Proper electrical installation and grounding are important for safety.

### Safety Rule

Students should **never experiment with live electrical wiring**.

Only demonstrate safe, ready-to-use electrical equipment.

---

## Daily Lab

1. Identify a UPS.
2. Identify a surge protector.
3. Connect a computer through a UPS.
4. Observe the UPS status.
5. With a safe controlled demonstration, interrupt mains power.
6. Observe that the computer continues temporarily.
7. Save a document.
8. Shut down the computer correctly.

---

# 3. Windows Operating System

## 3.1 What is an Operating System?

An Operating System, or OS, is software that manages the computer's hardware and provides an environment for applications to run.

Examples:

- Windows
- Linux
- macOS
- Android
- iOS

Basic structure:

```text
User
 |
 v
Applications
 |
 v
Operating System
 |
 v
Hardware
```

Example:

```text
User
 |
 v
Excel
 |
 v
Windows
 |
 v
CPU / RAM / Storage
```

---

# 3.2 What Does an Operating System Do?

An OS manages:

- CPU
- RAM
- Files
- Storage
- Devices
- Users
- Applications
- Security

---

# 3.3 CPU

CPU means:

**Central Processing Unit**

It executes instructions.

A simplified CPU process is:

```text
Fetch
  |
  v
Decode
  |
  v
Execute
```

The CPU performs calculations and executes program instructions.

---

# 3.4 RAM

RAM means:

**Random Access Memory**

RAM is the computer's temporary working memory.

For example, when we open:

- Chrome
- Excel
- PowerPoint
- VS Code

the operating system loads the required data into RAM.

RAM is generally **volatile memory**.

That means:

> Data stored in RAM is normally lost when power is removed.

---

# 3.5 Storage

Storage keeps data even after the computer is switched off.

Examples:

- HDD
- SSD
- USB drive
- Memory card

### RAM vs Storage

Think of:

```text
RAM = Study table
SSD/HDD = Cupboard
```

You bring books from the cupboard to the table when studying.

Similarly:

```text
Storage
   |
   v
 RAM
   |
   v
 CPU
```

---

# 3.6 Motherboard

The motherboard connects important computer components.

Simplified:

```text
             CPU
              |
       +------+------+
       | Motherboard |
       +------+------+
        /     |      \
      RAM    SSD     GPU
```

---

# 3.7 GPU

GPU means:

**Graphics Processing Unit**

It processes graphics and can perform many parallel computations.

GPUs are used for:

- Gaming
- Graphics
- Video processing
- AI/ML workloads

---

# 3.8 Windows User Interface

Important Windows components:

- Desktop
- Start Menu
- Taskbar
- Search
- File Explorer
- Recycle Bin
- Settings
- Notification area

---

# 3.9 Files

A file stores information.

Examples:

```text
photo.jpg
resume.pdf
marks.xlsx
presentation.pptx
notes.txt
```

---

# 3.10 Folders

Folders organize files.

Example:

```text
School
|
+-- Maths
|   +-- homework.docx
|   +-- marks.xlsx
|
+-- Science
|   +-- project.pdf
|
+-- English
    +-- essay.docx
```

---

# 3.11 File Path

A path tells us where a file is located.

Windows example:

```text
C:\Users\Student\Documents\School\marks.xlsx
```

Important:

```text
Windows uses \
Linux uses /
```

---

# 3.12 File Management

Students should learn:

- Create
- Rename
- Copy
- Move
- Delete
- Restore
- Search
- View properties

---

# 3.13 Users

A computer can have multiple users.

Example:

```text
Administrator
Teacher
Student
```

Different users can have different permissions.

---

# 3.14 Authentication vs Authorization

### Authentication

Answers:

> Who are you?

Example:

```text
Username + Password
```

### Authorization

Answers:

> What are you allowed to do?

Example:

```text
Administrator
    |
    +-- Install software

Student
    |
    +-- Use applications
```

This is an important cybersecurity concept.

---

## Windows Daily Lab

Students should:

1. Explore the Desktop.
2. Open Start Menu.
3. Open Settings.
4. Open File Explorer.
5. Create a `School` folder.
6. Create subject folders.
7. Create a text file.
8. Rename the file.
9. Copy the file.
10. Move the file.
11. Delete the file.
12. Restore it from Recycle Bin.
13. Search for the file.
14. View file properties.
15. Check Windows version.
16. Check available storage.

---

# 4. Linux Fundamentals

## 4.1 What is Linux?

Linux is an operating system based around the Linux kernel.

Linux is widely used in:

- Servers
- Cloud computing
- Networking
- Cybersecurity
- Development
- Embedded systems

---

# 4.2 GUI vs CLI

### GUI

Graphical User Interface.

We interact using:

- Mouse
- Windows
- Icons
- Menus

### CLI

Command Line Interface.

We type commands.

Example:

```bash
ls
```

---

# 4.3 Linux Shell

The shell interprets commands entered by the user.

Simplified:

```text
User
 |
 v
Shell
 |
 v
Kernel
 |
 v
Hardware
```

Examples of shells:

- Bash
- Zsh
- PowerShell

---

# 4.4 Important Linux Commands

## pwd

Shows the current directory.

```bash
pwd
```

---

## ls

Lists files and folders.

```bash
ls
```

---

## cd

Changes directory.

```bash
cd Documents
```

Go to parent directory:

```bash
cd ..
```

---

## mkdir

Creates a directory.

```bash
mkdir school
```

---

## touch

Creates an empty file.

```bash
touch test.txt
```

---

## cp

Copies a file.

```bash
cp test.txt backup.txt
```

---

## mv

Moves or renames a file.

```bash
mv test.txt new.txt
```

---

## rm

Removes a file.

```bash
rm new.txt
```

---

## cat

Displays file contents.

```bash
cat file.txt
```

---

# 4.5 Linux File System

Linux starts from:

```text
/
```

This is called the **root directory**.

Example:

```text
/
|
+-- home
+-- etc
+-- var
+-- tmp
+-- usr
+-- root
```

Important:

```text
/
```

is the filesystem root.

```text
/root
```

is the home directory of the root user.

They are different concepts.

---

# 4.6 Linux Users

Linux supports multiple users.

Check current user:

```bash
whoami
```

Create a user:

```bash
sudo adduser student1
```

Set/change password:

```bash
sudo passwd student1
```

---

# 4.7 Shell Scripting

A shell script is a file containing commands that can be executed as a sequence.

Example:

```bash
#!/bin/bash

echo "Hello Students!"
echo "Welcome to Linux"
```

Save as:

```text
hello.sh
```

Make executable:

```bash
chmod +x hello.sh
```

Run:

```bash
./hello.sh
```

---

## Linux Daily Lab

Students should:

1. Open Terminal.
2. Run `pwd`.
3. Run `ls`.
4. Create a `School` directory.
5. Enter the directory.
6. Create subject directories.
7. Create files.
8. Copy files.
9. Rename files.
10. Delete files.
11. Display file contents.
12. Find their current user.
13. Create a test user.
14. Write a simple shell script.
15. Execute the script.

---

# 5. Excel Fundamentals

## 5.1 What is Excel?

Excel is a spreadsheet application.

It is useful for:

- Calculations
- Data entry
- Data analysis
- Tables
- Charts
- Sorting
- Filtering

Think of Excel as:

> A digital notebook made of rows and columns that can also perform calculations.

---

# 5.2 Workbook vs Worksheet

### Workbook

The complete Excel file.

Example:

```text
marks.xlsx
```

### Worksheet

A sheet inside the workbook.

One workbook can contain multiple worksheets.

---

# 5.3 Rows and Columns

Columns are represented by letters:

```text
A B C D E
```

Rows are represented by numbers:

```text
1
2
3
4
```

A cell is identified using:

```text
Column + Row
```

Example:

```text
A1
B5
C10
```

---

# 5.4 Entering Data

Example:

| Name | Maths | Science | English |
|---|---:|---:|---:|
| Ravi | 80 | 75 | 90 |
| Priya | 90 | 88 | 95 |
| Arun | 65 | 70 | 72 |

---

# 5.5 Formulas

Excel formulas normally start with:

```text
=
```

Example:

```excel
=SUM(B2:D2)
```

---

# 5.6 Common Functions

### SUM

```excel
=SUM(B2:D2)
```

Adds values.

### AVERAGE

```excel
=AVERAGE(B2:D2)
```

Calculates average.

### MAX

```excel
=MAX(B2:D2)
```

Finds highest value.

### MIN

```excel
=MIN(B2:D2)
```

Finds lowest value.

### COUNT

```excel
=COUNT(B2:D2)
```

Counts numeric values.

### IF

```excel
=IF(E2>=40,"Pass","Fail")
```

---

# 5.7 AutoFill

Suppose we enter:

```text
1
2
```

and drag the fill handle.

Excel can continue:

```text
3
4
5
6
7
```

AutoFill can also copy formulas and patterns.

---

# 5.8 Formatting Cells

Students should practice:

- Bold
- Italic
- Font size
- Alignment
- Borders
- Number format
- Cell background
- Column width
- Row height

---

# 5.9 Charts

Charts convert data into visual information.

Examples:

- Column chart
- Bar chart
- Pie chart
- Line chart

Example:

```text
Student Marks
     |
     v
Create Chart
     |
     v
Visual comparison
```

---

# 5.10 Sorting

Sorting rearranges data.

Example:

```text
Marks:

60
90
75
80
```

Sort descending:

```text
90
80
75
60
```

---

# 5.11 Filtering

Filtering displays only data matching a condition.

Example:

> Show students who scored more than 80.

---

# 5.12 Freeze Panes

Freeze Panes keeps selected rows or columns visible while scrolling.

Useful when working with large tables.

---

## Excel Daily Lab

Create a marksheet for 20 students.

Students must:

1. Enter names.
2. Enter subject marks.
3. Calculate total.
4. Calculate average.
5. Find highest mark.
6. Find lowest mark.
7. Calculate Pass/Fail.
8. Format the table.
9. Use AutoFill.
10. Create a chart.
11. Sort by total.
12. Filter students.
13. Freeze the header.
14. Save the workbook.
15. Print the worksheet.

---

# 6. PowerPoint Fundamentals

## 6.1 What is PowerPoint?

PowerPoint is presentation software.

It allows us to create presentations using slides.

---

# 6.2 Slide

A slide is one page/screen of a presentation.

Example:

```text
Presentation
|
+-- Slide 1
+-- Slide 2
+-- Slide 3
+-- Slide 4
```

---

# 6.3 Adding Content

A slide can contain:

- Text
- Images
- Shapes
- Tables
- Charts
- Audio
- Video

---

# 6.4 Themes

A theme provides a consistent visual design.

It can control things such as:

- Fonts
- Background
- Layout
- Overall appearance

---

# 6.5 Transitions

A transition is an effect used when moving from one slide to another.

Example:

```text
Slide 1
   |
   | Transition
   v
Slide 2
```

---

# 6.6 Animations

Animations apply effects to objects inside a slide.

Example:

```text
Text appears
Image enters
Bullet points appear
```

---

# 6.7 Saving and Presenting

Save the presentation.

Then use:

```text
Slide Show / Present
```

to present it to the audience.

---

## PowerPoint Daily Lab

Create a presentation:

# "Cyber Safety for Students"

Create five slides:

1. Title
2. What is Cybersecurity?
3. Strong Passwords
4. Phishing
5. Cyber Safety Rules

Add:

- Images
- Theme
- Transition
- One or two simple animations

Finally:

> Present the slides to the class.

---

# 7. Web Browsers and Search Engines

## 7.1 What is the Internet?

The Internet is a global network of interconnected networks.

It allows devices around the world to communicate.

Simplified:

```text
Computer
   |
Router
   |
Internet
   |
Server
```

---

# 7.2 What is a Web Browser?

A browser is software used to access websites.

Examples:

- Google Chrome
- Microsoft Edge
- Mozilla Firefox
- Safari

---

# 7.3 What is a Search Engine?

A search engine helps users find information on the web.

Examples:

- Google Search
- Bing

Important:

> A browser and a search engine are different things.

Example:

```text
Chrome = Browser

Google Search = Search Engine
```

---

# 7.4 Website

A website is a collection of web pages and resources available through the web.

Example:

```text
https://example.com
```

---

# 7.5 Hyperlink

A hyperlink is a clickable reference that takes us to another location.

It may lead to:

- Another page
- Another website
- A document
- A section of the same page

---

# 7.6 Browser Navigation

Students should understand:

- Address bar
- Back
- Forward
- Refresh
- Tabs
- Bookmarks
- Downloads
- History

---

## Daily Lab

Students should:

1. Open a browser.
2. Search for a topic.
3. Open multiple websites.
4. Identify the address bar.
5. Click a hyperlink.
6. Open a link in a new tab.
7. Go back.
8. Go forward.
9. Refresh a page.
10. Bookmark a useful page.
11. Download a safe educational document.
12. Identify the website domain.

---

# 8. Connecting a Device to the Internet

There are two common ways:

1. Ethernet
2. Wi-Fi

---

# 8.1 Ethernet

Ethernet uses a physical network cable.

Example:

```text
Computer
   |
Ethernet Cable
   |
Router/Switch
   |
Internet
```

---

# 8.2 Wi-Fi

Wi-Fi provides wireless network connectivity.

Example:

```text
Computer
   ))))
 Wi-Fi
   ((((
 Router
   |
Internet
```

---

# 8.3 Connecting Using Wi-Fi

Steps:

1. Open network settings.
2. Turn Wi-Fi on.
3. Select the required network.
4. Enter the password.
5. Connect.
6. Check connectivity.

---

# 8.4 Connecting Using Ethernet

Steps:

1. Connect Ethernet cable.
2. Connect the other end to the switch/router.
3. Check link status.
4. Check network configuration.
5. Test connectivity.

---

# 8.5 What Happens After Connecting?

A device usually needs network configuration such as:

- IP address
- Subnet mask/prefix
- Default gateway
- DNS server

These may be configured manually or obtained automatically using DHCP.

---

# 9. Antivirus and Malware

## 9.1 What is Malware?

Malware means:

**Malicious Software**

It is software designed to perform harmful or unwanted actions.

Examples:

- Virus
- Worm
- Trojan
- Spyware
- Ransomware

---

# 9.2 Virus

A virus is malware that can attach itself to files or programs and spread when the infected content is executed.

---

# 9.3 Worm

A worm can spread between systems, often by exploiting vulnerabilities or network mechanisms.

---

# 9.4 Trojan

A Trojan is malicious software disguised as something legitimate.

Example:

```text
Useful-looking application
          |
          v
      Trojan
          |
          v
Malicious activity
```

---

# 9.5 Ransomware

Ransomware can encrypt or otherwise restrict access to data and demand payment.

---

# 9.6 Antivirus

Antivirus/security software helps detect, block, quarantine, or remove malicious software.

Simplified:

```text
File
 |
 v
Security Software
 |
 +---- Safe ----> Allow
 |
 +---- Suspicious/Dangerous
             |
             v
        Block/Quarantine
```

---

## Windows Security Lab

Students should:

1. Open Windows Security.
2. Check security status.
3. Check antivirus protection.
4. Run a Quick Scan.
5. View scan results.
6. View protection history.
7. Understand quarantine.

### Safety

Do not ask students to download real malware.

Use safe security demonstrations or test files designed specifically for security testing.

---

# 10. Network Topologies

## 10.1 What is Network Topology?

Network topology describes how devices are arranged and connected in a network.

---

# 10.2 Star Topology

All devices connect to a central device, usually a switch.

```text
        PC1
         |
         |
PC2 ---- Switch ---- PC3
         |
         |
        PC4
```

Advantages:

- Easy to manage
- Easy to troubleshoot
- One cable failure normally affects only one device

Disadvantage:

- Failure of the central device can affect connected devices

---

# 10.3 Bus Topology

Devices share a common communication medium.

```text
PC1 --- PC2 --- PC3 --- PC4
```

Older networks used bus-like designs.

---

# 10.4 Ring Topology

Devices form a ring.

```text
PC1 ---- PC2
 |         |
 |         |
PC4 ---- PC3
```

---

# 10.5 Mesh Topology

Devices have multiple connections.

```text
A -------- B
|\        /|
| \      / |
|  \    /  |
|   \  /   |
|    \/    |
C -------- D
```

Mesh provides redundancy but requires more connections.

---

# 10.6 Tree Topology

A hierarchical arrangement.

```text
           Core
          /    \
       Switch Switch
       /  \     /  \
     PC   PC   PC   PC
```

---

## Daily Lab

Give students topology diagrams.

Ask them to identify:

- Star
- Bus
- Ring
- Mesh
- Tree

Then ask:

> Which topology is commonly suitable for a modern school computer lab?

Expected answer:

> A star-based topology using switches.

---

# 11. Types of Networks

Networks can be classified based on their geographical scope.

---

# 11.1 PAN

PAN = Personal Area Network.

Example:

```text
Phone
 |
Bluetooth
 |
Earphones
```

---

# 11.2 LAN

LAN = Local Area Network.

Example:

```text
School Computer Lab
```

A LAN usually covers a limited area such as:

- Room
- Building
- School
- Office

---

# 11.3 MAN

MAN = Metropolitan Area Network.

It generally covers a larger area such as a city or metropolitan region.

---

# 11.4 WAN

WAN = Wide Area Network.

Covers a large geographical area.

The Internet is the best-known example of an interconnected global network.

---

# Easy Memory Trick

```text
PAN → Person
LAN → Local building/site
MAN → Metropolitan/city
WAN → Wide geographical area
```

---

# 12. TCP/IP, IPv4, IPv6 and OSI Model

# 12.1 What is a Protocol?

A protocol is a set of rules used for communication.

Humans need rules to communicate.

Computers also need communication rules.

Examples:

```text
HTTP
HTTPS
TCP
UDP
IP
DNS
DHCP
SSH
```

---

# 12.2 IPv4

IPv4 uses **32-bit addresses**.

Example:

```text
192.168.1.10
```

An IPv4 address contains four octets:

```text
192 . 168 . 1 . 10
 |     |    |    |
octet octet octet octet
```

Each octet ranges from:

```text
0 to 255
```

because:

```text
2^8 = 256
```

possible values exist.

---

# 12.3 IPv6

IPv6 uses **128-bit addresses**.

Example:

```text
2001:db8::1
```

IPv6 provides a vastly larger address space than IPv4.

Simple comparison:

```text
IPv4 → 32 bits

IPv6 → 128 bits
```

---

# 12.4 MAC Address

A network interface usually has a MAC address.

Example:

```text
00:1A:2B:3C:4D:5E
```

MAC addresses are used at the Ethernet/Data Link layer for local network communication.

---

# 12.5 IP Address vs MAC Address

Simple explanation:

```text
MAC → Local network/interface identification
IP  → Logical network addressing
```

Don't think of either as a perfect universal "identity." They serve different networking purposes.

---

# 12.6 TCP

TCP = Transmission Control Protocol.

TCP provides connection-oriented and reliable transport.

It can:

- Establish a connection
- Number data
- Acknowledge received data
- Retransmit lost data

Simplified:

```text
Sender
  |
  | Data
  v
Network
  |
  v
Receiver

Receiver sends acknowledgements
```

---

# 12.7 UDP

UDP = User Datagram Protocol.

UDP is connectionless and provides fewer reliability mechanisms than TCP.

It is useful when applications prefer simplicity, low overhead, or application-controlled reliability.

---

# 12.8 Ports

A port helps identify a service/application endpoint on a host.

Example:

```text
192.168.1.10:443
```

Here:

```text
IP Address = 192.168.1.10
Port       = 443
```

Common ports:

```text
22  → SSH
53  → DNS
80  → HTTP
443 → HTTPS
```

---

# 12.9 OSI Model

OSI stands for:

**Open Systems Interconnection**

The OSI model divides networking into seven conceptual layers.

```text
Layer 7 → Application
Layer 6 → Presentation
Layer 5 → Session
Layer 4 → Transport
Layer 3 → Network
Layer 2 → Data Link
Layer 1 → Physical
```

---

# 12.10 Layer 1 — Physical

Deals with physical transmission.

Examples:

- Copper cable
- Fiber
- Radio signals
- Electrical signals
- Connectors

Example problem:

> Ethernet cable is disconnected.

Think:

> Physical Layer

---

# 12.11 Layer 2 — Data Link

Deals with local network communication.

Examples:

- Ethernet
- MAC addresses
- Frames
- Switches

---

# 12.12 Layer 3 — Network

Deals with logical addressing and routing.

Examples:

- IP
- Routers
- Packets
- Routing

---

# 12.13 Layer 4 — Transport

Deals with transport between endpoints.

Examples:

- TCP
- UDP
- Ports

---

# 12.14 Layers 5–7

### Layer 5 — Session

Manages communication sessions conceptually.

### Layer 6 — Presentation

Conceptually deals with data representation, encoding, encryption and compression.

### Layer 7 — Application

Provides network services used by applications.

Examples:

- HTTP
- DNS
- SMTP
- SSH

---

# 12.15 OSI Memory Trick

From Layer 7 to Layer 1:

```text
Application
Presentation
Session
Transport
Network
Data Link
Physical
```

Mnemonic:

> **All People Seem To Need Data Processing**

---

# 12.16 TCP/IP Model

A simplified TCP/IP model can be represented as:

```text
Application
Transport
Internet
Link
```

Mapping approximately:

```text
OSI                    TCP/IP

Application
Presentation    →      Application
Session

Transport       →      Transport

Network         →      Internet

Data Link
Physical        →      Link
```

The models are useful for understanding different aspects of networking; real protocols do not always fit perfectly into one conceptual layer.

---

# 13. Physical Routing and Switching Lab

Now move from theory to practical networking.

---

# 13.1 Basic Devices

Identify:

### Router

Connects different IP networks.

### Switch

Connects devices within a LAN.

### Network Interface Card

Allows a device to connect to a network.

### Ethernet Cable

Carries Ethernet communication between compatible network interfaces.

---

# 13.2 Basic Network

```text
PC1
 |
Switch
 |
Router
 |
Internet
```

---

# 13.3 Larger Lab

Build:

```text
PC1
 |
Switch1
 |
Router1
 |
Router2
 |
Switch2
 |
PC2
```

---

# 13.4 Physical Lab Tasks

Students should:

1. Identify routers.
2. Identify switches.
3. Identify Ethernet ports.
4. Connect PC to switch.
5. Connect switch to router.
6. Connect router to router.
7. Observe link LEDs.
8. Check interface status.
9. Document the topology.

---

# 13.5 Packet Tracer Alternative

If physical equipment is unavailable, use a network simulator such as Cisco Packet Tracer.

Students can build the same topology virtually.

This is often easier and safer for beginner networking labs.

---

# 14. Two Routers and Two Switches

Build:

```text
                 Router 1
                /        \
             Switch      Router 2
               |            |
              PC1         Switch
                            |
                           PC2
```

A simpler linear representation:

```text
PC1
 |
SW1
 |
R1
 |
R2
 |
SW2
 |
PC2
```

---

# 14.1 Example IP Addressing

PC1 network:

```text
192.168.1.0/24
```

Router-to-router network:

```text
10.0.0.0/30
```

PC2 network:

```text
192.168.2.0/24
```

Example:

```text
PC1
IP      = 192.168.1.10
Gateway = 192.168.1.1
```

R1:

```text
LAN interface = 192.168.1.1
WAN interface = 10.0.0.1
```

R2:

```text
WAN interface = 10.0.0.2
LAN interface = 192.168.2.1
```

PC2:

```text
IP      = 192.168.2.10
Gateway = 192.168.2.1
```

---

# 14.2 What is a Default Gateway?

Suppose PC1 wants to communicate with a device outside its local network.

It sends the traffic to its default gateway.

Example:

```text
PC1
192.168.1.10
    |
    v
Default Gateway
192.168.1.1
    |
    v
Router
```

The default gateway is normally a router interface on the local network.

---

# 14.3 Ping

`ping` tests basic IP connectivity.

Example:

```bash
ping 192.168.2.10
```

Conceptually:

```text
PC1
 |
 | ICMP Echo Request
 v
PC2
 |
 | ICMP Echo Reply
 v
PC1
```

---

# 14.4 Traceroute

Traceroute helps identify the path packets take through routers.

Windows:

```cmd
tracert 192.168.2.10
```

Linux:

```bash
traceroute 192.168.2.10
```

---

# 15. Static Routing

## 15.1 What is Routing?

Routing is the process of deciding where IP packets should be forwarded.

Example:

```text
Network A
   |
  R1
   |
  R2
   |
Network B
```

R1 needs to know how to reach Network B.

---

# 15.2 Routing Table

A router maintains a routing table.

Simplified:

```text
Destination        Next Hop

192.168.1.0/24     Direct
192.168.2.0/24     10.0.0.2
```

The router uses the routing table to determine where traffic should go.

---

# 15.3 Static Routing

Static routing means routes are manually configured.

Concept:

```text
R1

To reach:
192.168.2.0/24

Send traffic to:
10.0.0.2
```

Cisco IOS example:

```text
ip route 192.168.2.0 255.255.255.0 10.0.0.2
```

On R2:

```text
ip route 192.168.1.0 255.255.255.0 10.0.0.1
```

---

# 15.4 Why Do We Need Routes in Both Directions?

Suppose:

```text
PC1 → PC2
```

PC1's packet needs a route from R1 to R2.

But PC2's response also needs a route:

```text
PC2 → PC1
```

Therefore, both directions must have a valid path.

---

# 15.5 Static Routing Lab

Students should:

1. Build two-router topology.
2. Configure IP addresses.
3. Configure PC gateways.
4. Verify interfaces.
5. Configure static routes.
6. Ping PC2 from PC1.
7. Test reverse connectivity.
8. Use `tracert`/`traceroute`.
9. Remove a route.
10. Observe failure.
11. Add the route again.
12. Verify connectivity.

---

# 15.6 Troubleshooting Static Routing

Use this sequence:

```text
1. Is the cable connected?
          |
          v
2. Is the interface UP?
          |
          v
3. Does the device have an IP?
          |
          v
4. Is the subnet correct?
          |
          v
5. Is the default gateway correct?
          |
          v
6. Does the router know the destination network?
          |
          v
7. Is there a return route?
          |
          v
8. Test with ping/traceroute
```

This troubleshooting methodology is more important than simply memorizing commands.

---

# 16. Dynamic Routing — OSPF and EIGRP

# 16.1 Static vs Dynamic Routing

### Static Routing

A network administrator manually configures routes.

```text
Administrator
     |
     v
Router
     |
     v
Route
```

### Dynamic Routing

Routers exchange routing information automatically.

```text
Router 1 <------> Router 2
    ^                  ^
    |                  |
Routing information exchanged
```

---

# 16.2 Why Dynamic Routing?

Imagine:

```text
R1 ---- R2 ---- R3 ---- R4
```

With many routers, manually configuring every route becomes difficult.

Dynamic routing protocols can help routers learn and update routes.

---

# 16.3 Dynamic Routing Protocols

Examples:

- RIP
- OSPF
- EIGRP
- BGP

For this beginner course:

> Focus mainly on OSPF.

EIGRP can be introduced conceptually or used if the lab specifically requires Cisco EIGRP.

---

# 16.4 OSPF

OSPF means:

**Open Shortest Path First**

OSPF is a link-state interior gateway routing protocol.

Very simplified:

```text
R1 <----> R2 <----> R3
 |          |          |
Networks  Networks   Networks
```

Routers exchange information about the network topology and calculate routes.

---

# 16.5 OSPF Area

OSPF uses areas.

The main backbone area is:

```text
Area 0
```

For beginner labs, use a simple single-area design:

```text
R1 ---- R2
 \      /
  Area 0
```

---

# 16.6 Basic OSPF Configuration Concept

Cisco IOS example:

```text
router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
 network 10.0.0.0 0.0.0.3 area 0
```

The exact configuration depends on the router topology and software version.

---

# 16.7 OSPF Lab

Students should:

1. Build two or three routers.
2. Configure IP addresses.
3. Verify interfaces.
4. Configure OSPF.
5. Advertise networks.
6. Check routing tables.
7. Test connectivity.
8. Disconnect a simulated link.
9. Observe routing changes.
10. Restore the link.
11. Verify the network again.

---

# 16.8 EIGRP

EIGRP means:

**Enhanced Interior Gateway Routing Protocol**

It is historically associated strongly with Cisco environments.

For beginner students, explain:

> EIGRP is a dynamic routing protocol that allows routers to exchange routing information and select paths to destination networks.

The main learning objective should be understanding **dynamic route exchange**, not memorizing a large number of commands.

---

# 17. VLANs and Inter-VLAN Communication

# 17.1 What is a VLAN?

VLAN means:

**Virtual Local Area Network**

A VLAN allows a physical switch to be divided into multiple logical networks.

Example:

```text
              Switch
          /      |      \
         /       |       \
      VLAN 10  VLAN 20  VLAN 30
      Students Teachers Admin
```

---

# 17.2 Why VLANs?

Suppose a school has:

```text
Students
Teachers
Administration
```

We may want them logically separated.

Example:

```text
VLAN 10 → Students
VLAN 20 → Teachers
VLAN 30 → Administration
```

---

# 17.3 VLAN and Broadcast Domain

A VLAN normally represents a separate Layer 2 broadcast domain.

Example:

```text
VLAN 10
+-------------+
| Student PCs |
+-------------+

VLAN 20
+-------------+
| Teacher PCs |
+-------------+
```

Broadcast traffic in one VLAN does not normally propagate into another VLAN through ordinary Layer 2 switching.

---

# 17.4 Access Port

An access port normally carries traffic for one VLAN.

Example:

```text
PC
 |
Switch Port
 |
VLAN 10
```

---

# 17.5 Trunk Port

A trunk link can carry traffic for multiple VLANs.

Example:

```text
Switch 1
   ||
   || Trunk
   ||
Switch 2

VLAN 10
VLAN 20
VLAN 30
```

802.1Q tagging is commonly used to identify VLAN traffic on trunk links.

---

# 17.6 Creating VLANs

Cisco IOS example:

```text
vlan 10
 name STUDENTS

vlan 20
 name TEACHERS
```

Assign a port to VLAN 10:

```text
interface fa0/1
 switchport mode access
 switchport access vlan 10
```

Assign another port to VLAN 20:

```text
interface fa0/2
 switchport mode access
 switchport access vlan 20
```

Exact interface names depend on the device.

---

# 17.7 Same VLAN Communication

Example:

```text
PC1
VLAN 10
 |
Switch
 |
PC2
VLAN 10
```

PC1 and PC2 can communicate at Layer 2 if their IP addressing and other configuration are correct.

---

# 17.8 Different VLAN Communication

Example:

```text
PC1
VLAN 10
 |
Switch
 |
PC2
VLAN 20
```

They are in different Layer 2 broadcast domains.

Routing is required for communication between them.

---

# 17.9 Inter-VLAN Routing

Inter-VLAN routing allows devices in different VLANs to communicate through a Layer 3 device.

Example:

```text
VLAN 10
   |
   v
Switch
   |
   v
Router / Layer 3 Switch
   |
   v
VLAN 20
```

---

# 17.10 Router-on-a-Stick Concept

A common beginner lab uses one router interface configured with multiple logical subinterfaces.

Concept:

```text
             Router
               |
             Trunk
               |
             Switch
            /      \
       VLAN 10    VLAN 20
```

Example conceptual configuration:

```text
interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
```

The router provides Layer 3 gateways for the VLANs.

---

# 17.11 VLAN Lab

Create:

```text
VLAN 10 = STUDENTS
VLAN 20 = TEACHERS
```

Connect:

```text
Student PC
     |
   VLAN 10
     |
   Switch
     |
   Router
     |
   VLAN 20
     |
Teacher PC
```

Students should:

1. Create VLAN 10.
2. Create VLAN 20.
3. Name the VLANs.
4. Assign switch ports.
5. Configure IP addresses.
6. Configure the trunk.
7. Configure inter-VLAN routing.
8. Test same-VLAN connectivity.
9. Test inter-VLAN connectivity.
10. Troubleshoot a deliberately incorrect VLAN assignment.

---

# 18. Final Practical Project

## School Network Project

Scenario:

> A school wants to build a small network for students and teachers.

Design:

```text
                       Router
                         |
                    Core Switch
                    /          \
               VLAN 10        VLAN 20
               Students       Teachers
                  |               |
               Switch 1         Switch 2
               /     \          /     \
             PC1     PC2      PC3     PC4
```

---

## Student Tasks

### Task 1 — Draw the Network

Students should identify:

- PCs
- Switches
- Router
- Connections
- VLANs

---

### Task 2 — Create VLANs

```text
VLAN 10 → STUDENTS
VLAN 20 → TEACHERS
```

---

### Task 3 — Configure IP Addresses

Example:

```text
Students:

192.168.10.0/24

Teachers:

192.168.20.0/24
```

---

### Task 4 — Configure Switch Ports

Assign student PCs to VLAN 10.

Assign teacher PCs to VLAN 20.

---

### Task 5 — Configure Routing

Configure inter-VLAN routing.

---

### Task 6 — Test Connectivity

Use:

```bash
ping
```

Test:

```text
Student PC → Student PC
Teacher PC → Teacher PC
Student PC → Teacher PC
```

---

### Task 7 — Troubleshoot

Intentionally create one problem:

- Wrong IP address
- Wrong subnet mask
- Wrong gateway
- Wrong VLAN
- Disabled interface
- Incorrect trunk
- Missing route

Ask students:

> What is wrong?

Then ask them to troubleshoot systematically.

---

# Important Concepts to Remember

## Computer

```text
Input
  ↓
Processing
  ↓
Output
  ↓
Storage
```

---

## Operating System

```text
User
 ↓
Application
 ↓
Operating System
 ↓
Hardware
```

---

## Networking

```text
Device
 ↓
NIC
 ↓
Ethernet/Wi-Fi
 ↓
Switch
 ↓
Router
 ↓
Other Networks
```

---

## Addressing

```text
MAC
 ↓
Layer 2 local communication

IP
 ↓
Layer 3 logical addressing/routing
```

---

## Transport

```text
TCP
 ↓
Reliable, connection-oriented transport

UDP
 ↓
Connectionless, lower-overhead transport
```

---

## Routing

```text
Destination Network
       ↓
Routing Table
       ↓
Next Hop / Interface
       ↓
Packet Forwarded
```

---

## Static vs Dynamic Routing

```text
STATIC

Administrator
     ↓
Manually configured route
```

```text
DYNAMIC

Router ←→ Router
       ↓
Exchange routing information
       ↓
Learn routes
```

---

## VLAN

```text
One physical switch
        ↓
Multiple logical networks
        ↓
VLAN 10
VLAN 20
VLAN 30
```

---

## Inter-VLAN Communication

```text
VLAN 10
   ↓
Layer 3 Device
   ↓
VLAN 20
```

---

# Troubleshooting Mindset

Whenever something doesn't work, don't randomly change configurations.

Follow a structured approach.

```text
1. Physical
      ↓
2. Link
      ↓
3. IP configuration
      ↓
4. Local connectivity
      ↓
5. Default gateway
      ↓
6. Routing
      ↓
7. Application/service
```

Example:

```text
PC1 cannot reach PC2
        |
        v
Is cable connected?
        |
        v
Is interface UP?
        |
        v
Does PC have correct IP?
        |
        v
Correct subnet?
        |
        v
Correct gateway?
        |
        v
Does router know destination?
        |
        v
Is return path available?
        |
        v
Ping / traceroute
```

---

# Teaching Principle

For a 10th-class student, avoid starting with complicated definitions.

Use this pattern:

```text
REAL-LIFE EXAMPLE
       ↓
SIMPLE DEFINITION
       ↓
DIAGRAM
       ↓
TECHNICAL CONCEPT
       ↓
DEMONSTRATION
       ↓
STUDENT LAB
       ↓
QUESTIONS
```

Example:

### Teaching a Router

Don't start with:

> "A router is a Layer 3 packet-forwarding device..."

Start with:

> "Imagine our school has two separate roads. A router is like a traffic officer who decides which road the data should take."

Then introduce:

```text
Network A
   |
Router
   |
Network B
```

Then explain:

> "Technically, a router connects different IP networks and forwards packets based on its routing table."

Then perform the lab.

---

# Core Vocabulary Students Should Know

Before completing this course, students should understand:

```text
Computer
Hardware
Software
CPU
RAM
Storage
Operating System
File
Folder
User
Permission
Application
Browser
Search Engine
Internet
Network
NIC
Ethernet
Wi-Fi
MAC Address
IP Address
IPv4
IPv6
Switch
Router
Packet
Frame
Protocol
TCP
UDP
Port
OSI
TCP/IP
LAN
WAN
Topology
VLAN
Routing
Static Route
Dynamic Routing
OSPF
```

---

# Final Mental Model

The most important thing for the teacher is to understand how all these topics connect.

```text
                    COMPUTER
                       |
          +------------+------------+
          |                         |
       Hardware                  Software
          |                         |
    CPU/RAM/Storage            Operating System
                                    |
                          +---------+---------+
                          |                   |
                       Windows              Linux
                          |
                  Applications
                  /          \
              Excel       PowerPoint
                  |
               Internet
                  |
             Network Card
                  |
             Ethernet/Wi-Fi
                  |
                Switch
                  |
                Router
                  |
             Other Networks
                  |
               Internet
                  |
          +-------+--------+
          |                |
       TCP/UDP             IP
          |                |
        Ports           IPv4/IPv6
                           |
                        Routing
                           |
                +----------+----------+
                |                     |
             Static                Dynamic
             Routing               Routing
                                   |
                              OSPF/EIGRP
                                   
Switching
    |
   VLAN
    |
    +-------- VLAN 10
    |
    +-------- VLAN 20
                 |
           Inter-VLAN Routing
```

The goal is **not to memorize commands**.

The goal is to understand:

> **What is happening, why it is happening, and which device/protocol is responsible for it.**

Once that mental model is clear, the commands become much easier to learn.