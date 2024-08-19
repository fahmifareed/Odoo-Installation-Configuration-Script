
# Odoo Installation & Configuration Script

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)
![Python](https://img.shields.io/badge/python-3.x-blue.svg)
![Platform](https://img.shields.io/badge/platform-Ubuntu-orange.svg)
[![Odoo Version](https://img.shields.io/badge/Odoo-15.0-blue.svg)](https://www.odoo.com)

This is a Python script designed to automate the installation and configuration of Odoo on a local machine or a remote VPS. The script handles everything from installing dependencies to setting up Odoo as a systemd service, making it easy to deploy Odoo with minimal effort.

## 🚀 Features

- **Automated Installation**: Handles the full installation of Odoo and its dependencies on Ubuntu.
- **VPS Support**: Connect to a remote VPS and install Odoo seamlessly.
- **Systemd Integration**: Configures Odoo to run as a service, ensuring it starts automatically on boot.
- **Custom Addons Directory**: Automatically sets up a directory for custom Odoo modules.
- **Python Virtual Environment**: Odoo runs in a dedicated Python virtual environment for better package management.

## 🛠️ Requirements

- **Python 3.x**: Make sure Python 3.x is installed on your system.
- **Paramiko**: A Python library used for SSH connections. Install it with:
    ```bash
    pip install paramiko
    ```
- **Ubuntu**: The script is designed for Ubuntu (18.04, 20.04, 22.04), but it might work on other Debian-based distributions as well.

## 📦 Installation

### Clone the Repository
First, clone this repository to your local machine:
```bash
git clone https://github.com/yourusername/odoo_installer.git
cd odoo_installer
```

### Configure Your Setup
Edit the `config.py` file with your desired settings:

```python
VPS_HOST = "your_vps_ip_or_hostname"
VPS_PORT = 22
VPS_USER = "your_vps_username"
VPS_PASSWORD = "your_vps_password"  # Consider using an SSH key instead of a password for security

ODOO_VERSION = "15.0"
ODOO_PORT = 8069
ODOO_SUPERADMIN = "admin"
ODOO_CONFIG = f"odoo-{ODOO_VERSION}"
ODOO_ADDONS_PATH = "/opt/odoo/custom-addons"
ODOO_DIR = "/opt/odoo/odoo-server"
```

### Run the Script
Run the script to start the installation process:

#### Install Locally:
```bash
python3 odoo_installer.py
```

#### Install on VPS:
```bash
python3 odoo_installer.py
```

When prompted, select whether to install Odoo locally or on the VPS.

## ⚙️ Configuration

The `config.py` file contains all the configuration settings needed for the installation:

- **VPS_HOST**: IP address or hostname of your VPS.
- **VPS_PORT**: SSH port (default is 22).
- **VPS_USER**: SSH username for the VPS.
- **VPS_PASSWORD**: SSH password for the VPS (consider using SSH keys for security).
- **ODOO_VERSION**: The version of Odoo to install (e.g., "15.0").
- **ODOO_PORT**: The port Odoo will run on (default is 8069).
- **ODOO_SUPERADMIN**: The master password for Odoo database management.
- **ODOO_CONFIG**: Name of the configuration file for Odoo.
- **ODOO_ADDONS_PATH**: Directory where custom Odoo modules will be stored.
- **ODOO_DIR**: Directory where the Odoo source code will be installed.

## 🧰 Usage

After installation, you can manage the Odoo service using systemd:

### Start Odoo Service
```bash
sudo systemctl start odoo-15.0.service
```

### Stop Odoo Service
```bash
sudo systemctl stop odoo-15.0.service
```

### Restart Odoo Service
```bash
sudo systemctl restart odoo-15.0.service
```

### Check Odoo Service Status
```bash
sudo systemctl status odoo-15.0.service
```

## 📂 Directory Structure

After installation, the following directories are important:

- **Odoo Server Code**: `/opt/odoo/odoo-server/`
- **Custom Addons**: `/opt/odoo/custom-addons/`
- **Odoo Configuration File**: `/etc/odoo-15.0.conf`
- **Odoo Log File**: `/var/log/odoo/odoo-15.0.log`

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- Script authored by Fahmi Fareed.
- Inspired by various Odoo installation guides and community contributions.

## 🌐 Links

- [Odoo Official Website](https://www.odoo.com)
- [Odoo Documentation](https://www.odoo.com/documentation)

