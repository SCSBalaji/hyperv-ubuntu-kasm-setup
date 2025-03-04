# Ubuntu VM in Hyper-V with Kasm Workspaces

A complete guide for setting up an Ubuntu virtual machine in Microsoft Hyper-V and installing Kasm Workspaces for secure containerized streaming of applications and desktops.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [Creating the Ubuntu VM](#creating-the-ubuntu-vm)
  - [Configuring VM Settings](#configuring-vm-settings)
  - [Installing Ubuntu](#installing-ubuntu)
  - [Updating Ubuntu](#updating-ubuntu)
  - [Disabling Secure Boot](#disabling-secure-boot)
  - [Installing Kasm Workspaces](#installing-kasm-workspaces)
- [Usage](#usage)
- [Troubleshooting & FAQs](#troubleshooting--faqs)
- [Additional Resources](#additional-resources)

## Features

- **Secure Containerized Environment**: Run applications and browsers in isolated containers
- **Browser Isolation**: Separate browsing activities from your local system for enhanced security
- **Remote Work Support**: Access applications and desktops from anywhere through a web browser
- **Development and Testing**: Create consistent development environments for web applications
- **Data Privacy**: Ensure compliance with data protection regulations through isolated workflows
- **High Performance**: Stream applications and desktops with optimized performance

## Prerequisites

- **Hardware Requirements**:
  - CPU with virtualization support (Intel VT-x/AMD-V)
  - Minimum 4 GB RAM (8+ GB recommended)
  - At least 30 GB free disk space
  
- **Software Requirements**:
  - Windows 10/11 Pro, Enterprise, or Education with Hyper-V feature enabled
  - Ubuntu Server or Desktop ISO (20.04 LTS or newer recommended)
  - Internet connection for downloading packages

## Installation

### Creating the Ubuntu VM

1. Open Hyper-V Manager
2. Click on "New" → "Virtual Machine"
3. Provide a name for your virtual machine
4. Choose Generation 2 for UEFI support
5. Allocate memory (minimum 4 GB recommended)
6. Configure networking
7. Create a virtual hard disk (minimum 30 GB recommended)
8. Choose "Install an operating system later"
9. Click "Finish" to create the VM

### Configuring VM Settings

1. Before starting the VM, select it and click "Settings"
2. Navigate to the "Security" tab
3. Under "Secure Boot", change the template from "Microsoft Windows" to "Microsoft UEFI Certificate Authority"
4. Allocate at least 2 virtual processors under "Processor" settings
5. Mount the Ubuntu ISO file under "SCSI Controller" → "DVD Drive" → "Image file"
6. Click "OK" to save settings

### Installing Ubuntu

1. Start the VM
2. Follow the on-screen Ubuntu installation wizard:
   - Select your language and keyboard layout
   - Choose installation type (normal or minimal)
   - Set up your location
   - Create a user account and password
   - Wait for installation to complete
3. Remove the installation media when prompted and restart

### Updating Ubuntu

1. Open the terminal in Ubuntu
2. Update and upgrade the system:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
3. Perform a full upgrade:
   ```bash
   sudo apt update && sudo apt full-upgrade -y
   ```

### Disabling Secure Boot

1. If needed, shut down the VM
2. In Hyper-V Manager, go to VM settings → "Security"
3. Uncheck the "Enable Secure Boot" option
4. Click "OK" to save changes
5. Start the VM again

### Installing Kasm Workspaces

1. Install curl (if not already installed):
   ```bash
   sudo apt update && sudo apt install -y curl
   ```

2. Navigate to the temporary directory:
   ```bash
   cd /tmp
   ```

3. Download Kasm Workspaces:
   ```bash
   curl -O https://kasm-static-content.s3.amazonaws.com/kasm_release_1.16.1.98d6fa.tar.gz
   ```

4. Extract the package:
   ```bash
   tar -xf kasm_release_1.16.1.98d6fa.tar.gz
   ```

5. Run the installer:
   ```bash
   sudo bash kasm_release/install.sh
   ```

6. Follow the on-screen prompts to complete installation

## Usage

1. After installation completes, you'll see a URL and credentials displayed in the terminal
2. Open a web browser and navigate to the URL (typically https://your-ubuntu-vm-ip)
3. Log in with the credentials provided during installation
4. From the dashboard, you can:
   - Launch containerized applications and workspaces
   - Manage users and sessions
   - Configure system settings
   - Monitor resource usage

## Troubleshooting & FAQs

### Q: What is Kasm Workspaces?
A: Kasm Workspaces is a container streaming platform for delivering browser, desktop, and application workloads to the web browser, designed for security, privacy, and performance.

### Q: Why should I use Kasm Workspaces?
A: It provides enhanced security through isolation, ensures privacy of browsing data, offers high-performance streaming of applications, and supports flexible use cases from secure browsing to remote work.

### Q: How do I access Kasm Workspaces after installation?
A: Open a web browser and navigate to the IP address or hostname of your Ubuntu VM. The default port is 443 (https).

### Q: I can't connect to the Kasm web interface
A: Check the following:
- Ensure the VM's network adapter is properly configured
- Verify that port 443 is not blocked by a firewall
- Check that the Kasm services are running: `sudo /opt/kasm/bin/status`

### Q: How do I update Kasm Workspaces?
A: Refer to the official Kasm documentation for update instructions.

### Q: The VM is running slowly
A: Try increasing the allocated memory and processors in the VM settings.

## Additional Resources

- [Kasm Workspaces Documentation](https://www.kasmweb.com/docs/latest/)
- [Ubuntu Documentation](https://help.ubuntu.com/)
- [Microsoft Hyper-V Documentation](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/)
- [Kasm Workspaces GitHub Repository](https://github.com/kasmtech/workspaces-core)
- [Kasm Workspaces Community Forum](https://forum.kasmweb.com/)
