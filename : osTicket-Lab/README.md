# osTicket Help Desk Deployment

## Overview
This project involved deploying osTicket, an open-source help desk ticketing system, to gain hands-on experience with the full lifecycle of IT support ticket management — from user submission through resolution.

## Environment
- **Web Server Stack:** XAMPP (Apache, PHP, MySQL)
- **Application:** osTicket v1.17
- **Database Management:** phpMyAdmin

## What I Built

### Environment Setup
- Installed and configured XAMPP to run Apache, MySQL, and PHP locally
- Created and configured the osTicket database through phpMyAdmin
- Deployed the osTicket application files and completed the guided installation process

### Ticket Lifecycle Practice
Simulated a real end-user support scenario from start to finish:
- Received a submitted ticket (user locked out of their account)
- Assigned the ticket to myself and set an appropriate priority level based on urgency
- Responded to the user acknowledging the issue and provided a resolution
- Followed up to confirm the issue was resolved
- Documented the resolution and closed the ticket

### Staff Control Panel
- Configured and navigated the osTicket Staff Control Panel (SCP)
- Reviewed ticket queues, statuses, and assignment workflows

## Troubleshooting Highlights

**IIS/PHP Configuration Issues:** Initially attempted to deploy osTicket using Windows Server 2022 with IIS, which resulted in several configuration conflicts including FastCGI module errors and a DLL compatibility issue between PHP and the installed Visual C++ Runtime. After extensive troubleshooting, pivoted to a XAMPP-based deployment on Windows 10 for a more streamlined setup — a practical lesson in choosing the right tool for the environment and knowing when to change approach.

**Database Configuration:** Resolved a MySQL root password requirement during the osTicket installer setup by configuring authentication through phpMyAdmin's User Accounts panel.

## Skills Demonstrated
- Web server stack deployment (Apache, PHP, MySQL)
- Help desk ticketing system configuration and administration
- Ticket triage, prioritization, and full lifecycle management
- Troubleshooting cross-platform software compatibility issues
- Adapting approach when initial technical strategy encounters obstacles
