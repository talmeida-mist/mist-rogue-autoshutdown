# Disclaimer

This project was independently developed and is not affiliated with or officially supported by Hewlett Packard Enterprise (HPE), Juniper Networks, or Mist Systems.

All use of this repository and its workflows is at your own risk. The author and the aforementioned companies assume no responsibility or liability for any damages or issues arising from its use.

# Mist Rogue Auto-Shutdown

## Overview
The Mist Rogue Auto-Shutdown workflow is designed to automate the shutdown of rogue devices on your network using n8n. This process helps maintain network integrity and security by removing unauthorized devices swiftly and efficiently.

## Features
- **Automated Device Detection:** Automatically detects rogue devices on the network.
- **Email Notifications:** Sends alerts when rogue devices are detected and actions are taken.
- **Customizable Workflow:** Users can tailor the workflow to fit their specific network needs.
- **Logging and Tracking:** Keeps detailed logs of actions taken for auditing and troubleshooting purposes.

## Prerequisites
- **n8n Installation:** Ensure that you have n8n installed and configured on your server.
- **Access to Network Devices:** The workflow requires access permissions to monitor and manage devices on your network.
- **Email Service Configuration:** Set up email credentials for sending notifications.

## Quick Start Guide
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/talmeida-mist/mist-rogue-autoshutdown.git
   cd mist-rogue-autoshutdown
   ```
2. **Import the Workflow into n8n:**
   - Open n8n and use the import functionality to load the workflow file.
3. **Configure Workflow Settings:**
   - Adjust the settings as per your network environment and requirements.
4. **Test the Workflow:**
   - Run the workflow manually to ensure it detects rogue devices and sends notifications correctly.
5. **Schedule the Workflow:**
   - Set the workflow to run on a schedule that meets your monitoring needs.

## Workflow Logic
- The workflow begins with device detection and checks against a list of authorized devices.
- If a rogue device is found, it triggers the shutdown command and sends an email notification to the specified admins.
- Logging is updated with each action taken for transparency and review.

## Email Notifications
- Email alerts include details about the detected rogue device, actions taken, and a summary of the incident.
- Ensure the email settings in n8n are configured to send these notifications properly.

## Customization Options
- Change the parameters that define what constitutes a rogue device.
- Customize email templates to fit your organization's communication style.
- Integrate additional actions based on organizational policies for dealing with rogue devices.

## Troubleshooting
- **Rogue Device Not Detected:** Ensure that the n8n instance has the proper network permissions.
- **Email Notifications Not Sent:** Check email configuration settings and ensure service is operational.
- **Workflow Fails to Run:** Review logs for errors, and ensure the n8n server is running correctly.

If issues persist, consult n8n's documentation or seek assistance from the community.

---

For more information and updates, visit the [repository](https://github.com/talmeida-mist/mist-rogue-autoshutdown).
