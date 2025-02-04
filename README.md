# Frappe & ERPNext Auto-Installer for WSL

Welcome to the automated installer for Frappe and ERPNext (with optional HRMS support) on Windows Subsystem for Linux (WSL)! This script simplifies the setup process, allowing you to quickly begin development or testing in your WSL environment.

---

## Prerequisites

Before you begin, ensure that you have the following:

- **WSL Installed:** Windows Subsystem for Linux must be installed on your Windows system.
- **Compatible Linux Distribution:** Ubuntu 22.04 LTS (or another compatible Linux distribution) should be running within your WSL environment.
- **Single Instance:** Make sure no other WSL instances are running Frappe benches. This prevents conflicts during installation and runtime.

---

## Installation Steps

1. **Open Your WSL Terminal:** Start by opening your terminal within your WSL environment.
2. **Place the Script:** Copy the `install.sh` file into your WSL file system.
3. **Make the Script Executable:**  
   ```bash
   chmod +x install.sh
   ```
4. **Run the Installer with Superuser Permissions:**  
   ```bash
   sudo ./install.sh
   ```

---

## Using the Installer

The installation script will prompt you with a series of questions to configure your Frappe (and optionally ERPNext/HRMS) installation. Once installed, you can access your site as follows:

- **Access URL:** Open your web browser and navigate to:  
  `http://localhost:8000`
- **Login Credentials:**  
  - **Username:** `Administrator`
  - **Password:** Use the administrator password you set during the installation process.

---

## Important Considerations

- **Single WSL Instance:** Ensure that you do not have multiple WSL instances running Frappe benches concurrently, as this can lead to conflicts and prevent `bench start` from functioning properly.
- **MariaDB Service:** Due to WSL limitations, the installer manually starts the MariaDB service. Verify that MariaDB is active when you require database access.
- **Permissions:** If you experience permission issues, check that the relevant directories and files are owned by the appropriate user and group (e.g., `mysql:mysql` for MariaDB data directories).

---

## Troubleshooting Tips

- **Bench Start Failures:**  
  - Confirm that no other benches are running.
  - Ensure the MariaDB service is active.
- **MariaDB Connection Issues:**  
  - Verify that MariaDB is running and listening on `127.0.0.1`.
- **Port Conflicts:**  
  - If port `8000` is occupied, you can start the bench on a different port by executing:  
    ```bash
    bench start --port 8001
    ```

---

## Contributing

We welcome contributions to improve this installer! If you have suggestions, encounter issues, or want to contribute code, please open an issue or submit a pull request on GitHub.

Enjoy your new Frappe and ERPNext setup on WSL, and happy coding!