# Cyber Kill Chain

The kill chain model is a cybersecurity framework that outlines the seven stages of a cyberattack: reconnaissance, weaponization, delivery, exploitation, installation, command and control (C2), and actions on objectives. 
This intelligence-driven approach emphasizes proactive defense by understanding and disrupting an attacker's activities at any stage, rather than simply reacting to compromises. 
The model proposes that interrupting even one phase can block an entire attack, providing defenders with multiple opportunities to counter threats. 
By aligning defensive capabilities with each stage of the kill chain and utilizing various indicators (atomic, computed, and behavioral), organizations can enhance their security posture and challenge the notion that attackers inherently have an advantage in cybersecurity.
Reference Hutchins et al 2011: Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains 

# MITRE ATT&CK Framework

The MITRE ATT&CK Framework is a comprehensive knowledge base that catalogs adversary tactics, techniques, and procedures (TTPs) used in cyberattacks.
 It serves as a globally accessible resource for cybersecurity professionals, providing a common language and structure for understanding and describing cyber threats. 
The framework is organized into a matrix of tactics (representing the "why" or objectives of an attack) and techniques (detailing the "how" or methods used to achieve those objectives). This structure allows organizations to assess their security posture, identify gaps in their defenses, and develop more effective threat detection and response strategies.
MITRE ATT&CK enables security teams to prioritize their efforts, improve threat intelligence, and enhance cybersecurity resilience by offering detailed information on known adversary behaviors.
Reference: MITRE. (2024). MITRE ATT&CK®. Retrieved October 28, 2024, from https://attack.mitre.org/

## How would you compare the Cyber Kill Chain and ATT&CK Enterprise matrix? Who do you think could benefit from these models?

The Cyber Kill Chain and MITRE ATT&CK Enterprise matrix are both valuable frameworks in cybersecurity, but they differ in their approach and level of detail. The Cyber Kill Chain presents a linear, seven-stage model of cyberattacks, providing a high-level overview of the attack process. In contrast, the ATT&CK Enterprise matrix offers a more complex  approach, with 14 tactics and different techniques and sub-techniques, covering a wide range of adversary behaviors

The Cyber Kill Chain is used for developing a high-level understanding of attack stages and creating defensive strategies. It is an effective tool for communicating cybersecurity concepts to non-technical stakeholders, such as executives and decision-makers. On the other hand, the ATT&CK framework is more beneficial for threat hunters, analysts, security architects, and red teams. Its detailed tactics and techniques can inform advanced threat hunting, guide robust security architecture design, and provide a framework for simulating real-world adversary behaviors in security assessments

Both models offer valuable insights for various stakeholders in the cybersecurity ecosystem. While the Cyber Kill Chain's simplicity can be valuable for high-level strategic planning and communication, the ATT&CK framework generally offers a more comprehensive and flexible approach to understanding and addressing modern cyber threats. Organizations may benefit from using both models in complementary ways: the Cyber Kill Chain for broad strategic planning and the ATT&CK matrix for detailed tactical and operational cybersecurity activities
#Reference : MITRE ATT&CK vs Cyber Kill Chain

## Pick a security incident and learn about it. Write briefly about it. Point out the concepts of threat actor, exploit, vulnerability, and (business) impact. (You can find writeups about security incidents from Darknet Diaries and Krebs)
The incident I have chosen is EP 148: Dubsnatch

The Dubsnatch incident involves a teenage music enthusiast, known as Professor Dubstep, who exploited vulnerabilities in online systems to access unreleased music tracks and insider information from the electronic dance music (EDM) industry.

-Threat Actor
The primary threat actor in this case was Professor Dubstep, a 13-year-old fan of electronic music who initially had no malicious intent but gradually became involved in more questionable activities.

-Exploits and Vulnerabilities
Professor Dubstep exploited several vulnerabilities:
Bitly URL Shortener Flaw: By adding a '+' to the end of shortened links, users could access the public profile of the account that created the link, revealing all their shortened URLs.
Weak Access Controls: Management accounts often shared internal documents using the same Bitly accounts used for public promotions, inadvertently exposing sensitive information.
Social Engineering: Professor Dubstep manipulated other collectors by creating fake "unreleased" tracks to trade for genuine unreleased music.

-Business Impact
The incident had several potential impacts on the music industry:
Premature Exposure: Unreleased tracks and promotional plans were accessed before their intended release dates.
Loss of Competitive Advantage: Internal memos and promotion plans being exposed could give competitors insight into marketing strategies.
Reduced Track Value: As noted by Professor Dubstep, when an unreleased track leaks online, "it's over for that track forever," potentially damaging an artist's or label's revenue prospects.

While the full extent of the damage is not detailed in the provided information, the incident highlights the need for improved security practices in the music industry, especially regarding the handling of unreleased material and internal communications.

## Install Debian on Virtualbox. Report your work, including the environment (including host OS, the real physical computer used), the steps you took, and their results.

Environment
Host OS: Windows 10 Home
Physical Computer: LAPTOP-8OIJK58N
Processor: AMD Ryzen 3 3200U with Radeon Vega Mobile Gfx (2.60 GHz)
RAM: 4 GB (3.42 GB usable)
System Type: 64-bit operating system, x64-based processor

Installation Steps and Results

1. Download Debian ISO

I downloaded the latest Debian 12 AMD64 Netinst ISO from the official Debian website (debian.org). The Netinst version is ideal for my setup as it requires an internet connection during installation but results in a smaller initial download.

Note: The Debian ISO file I downloaded is not meant to be installed directly on my Windows system. It's designed to be used as a virtual disk image within VirtualBox to install Debian in a virtual environment. So after downloading the Debian ISO, my next step is to download and install VirtualBox on my Windows 10 system. Once VirtualBox is installed, I will create a new virtual machine and use the Debian ISO during the setup process of that virtual machine.


2. Install VirtualBox

I downloaded and installed VirtualBox 7.1.4 from (virtualbox.org), selecting the Windows host version.

Note: After a successful download I got an error while trying to install the virtual box installer.
VirtualBox cannot be installed because you do not have Microsoft Visual C++ 2019 Redistributable Package. Please download it before installing VirtualBox.
I downloaded and installed both x86 and x64 versions of the multi-installer Visual C++ 2015, 2017, 2019, and 2022 redistributable. Restarted my PC after the installation and I was able to install it properly. Note: Don't install the ARM64 https://learn.microsoft.com/en-US/cpp/windows/l…
I used the Microsoft community to get this advice which worked

3. Create a New Virtual Machine

I launched VirtualBox selected expert mode and created a new virtual machine with the following settings:
- Name: Debian Nasirumbilornah
- Type: Linux
- Version: Debian (64-bit)
- Memory: 2024 MB (considering the host system has 4 GB RAM)
- Hard disk: Created a virtual hard disk, dynamically allocated, 20 GB in size

Note: Configurations of the Virtual Machine Settings are already done. I had to check and confirm the following before starting VM. 
- System > Processor: Allocated 1 CPU core
- Storage: Attached the downloaded Debian ISO to the virtual optical drive
- Network: Enabled NAT for internet connectivity

4. Start Installation
I started the virtual machine and began the Debian installation process:
I selected to install from the boot menu
Choose the language(English), location, and keyboard layout. 
Created a user name (Lornah123) 
Created login name (Lornah)and password.
 Note: At this point, I am able to access my VM
#Reference https://terokarvinen.com/2021/install-debian-on-virtualbox/ 
