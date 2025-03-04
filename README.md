# Step-by-Step Guide to Setting Up an Ubuntu VM in Hyper-V and Installing Kasm Workspaces

## Step 1: Create Ubuntu VM in Hyper-V
1. Open Hyper-V Manager.
2. Click on "New" -> "Virtual Machine".
3. Follow the wizard to create a new VM. Choose Ubuntu as the operating system.

## Step 2: Configure VM Settings
1. Before starting the VM, go to VM settings.
2. In the "Security" tab, under "Secure Boot", change the template from "Microsoft Windows" to "Microsoft UEFI Certificate Authority".

## Step 3: Start the VM and Install Ubuntu
1. Start the VM.
2. Follow the on-screen instructions to install Ubuntu.

## Step 4: Update and Upgrade Ubuntu
1. Open the terminal in Ubuntu.
2. Run the following commands to update and upgrade the system:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
   This command updates the list of available packages and their versions and installs newer versions of the packages you have.

3. Run the following command to perform a full upgrade:
   ```bash
   sudo apt update && sudo apt full-upgrade -y
   ```
   This command performs a full upgrade, which may remove some packages if necessary.

## Step 5: Disable Secure Boot
1. If secure boot is enabled in the Hyper-V VM, disable it from Hyper-V Manager.
2. Go to VM settings -> "Security".
3. Uncheck the "Enable Secure Boot" option.

## Step 6: Restart the VM
1. Restart the VM to apply the changes.

## Step 7: Install Curl
1. Open the terminal in Ubuntu.
2. Run the following command to install `curl`:
   ```bash
   sudo apt update && sudo apt install -y curl
   ```
   This command updates the package list and installs `curl`, a tool to transfer data from or to a server.

## Step 8: Download and Install Kasm Workspaces
1. Change to the `/tmp` directory:
   ```bash
   cd /tmp
   ```
   This command changes the current directory to `/tmp`, a directory for temporary files.

2. Download the Kasm Workspaces release package:
   ```bash
   curl -O https://kasm-static-content.s3.amazonaws.com/kasm_release_1.16.1.98d6fa.tar.gz
   ```
   This command downloads the Kasm Workspaces release package to the `/tmp` directory.

3. Extract the downloaded package:
   ```bash
   tar -xf kasm_release_1.16.1.98d6fa.tar.gz
   ```
   This command extracts the contents of the tar.gz file.

4. Run the installer:
   ```bash
   sudo bash kasm_release/install.sh
   ```
   This command runs the Kasm Workspaces installer.

## FAQ

### What is Kasm Workspaces?
[Kasm Workspaces](https://www.kasmweb.com/) is a container streaming platform for delivering browser, desktop, and application workloads to the web browser. It is designed for security, privacy, and performance.

### What are the uses of Kasm Workspaces?
- Secure Remote Work
- Browser Isolation
- Web Development and Testing
- Secure Access to Internal Applications
- Data Privacy and Compliance

### Why should I use Kasm Workspaces?
- **Security**: Provides a secure environment for accessing the internet and internal applications.
- **Privacy**: Ensures that browsing data and activities are isolated.
- **Performance**: Offers high-performance streaming of applications and desktops.
- **Flexibility**: Supports various use cases, from secure browsing to remote work.

### How do I access Kasm Workspaces after installation?
Once installed, you can access Kasm Workspaces by opening a web browser and navigating to the IP address or hostname of your server. The default port is 443.

### How do I update Kasm Workspaces?
To update Kasm Workspaces, follow the instructions provided in the official [Kasm documentation](https://www.kasmweb.com/docs/latest/).

## Conclusion
You have now successfully created an Ubuntu VM in Hyper-V and installed Kasm Workspaces. Follow the on-screen instructions to complete the setup of Kasm Workspaces.
