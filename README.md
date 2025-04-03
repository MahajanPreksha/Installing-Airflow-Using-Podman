# Steps to install Apache Airflow on Windows using Podman Desktop:

Apache Airflow is an Open Source tool developed to programmatically create, schedule and monitor workflows. To install it on a Windows machine, Podman Desktop can be used.

Podman Desktop is an Open Source innovative desktop tool which makes it easy to create, manage and run containerized applications visually.

Podman packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code and runtime. This will help to quickly deploy and scale applications into any environment.

Moreover, Podman CLI is used to run commands in the terminal to help initialise and start the virtual machine (VM).

1.  Install Podman Desktop for Windows from here: [https://podman-desktop.io/downloads/windows](https://podman-desktop.io/downloads/windows) and further, install Podman and Podman CLI extension from the pop-up that appears on the application interface.

2.  Go to the releases page: [https://github.com/astronomer/astro-cli/releases](https://github.com/astronomer/astro-cli/releases) and download the setup file as per the system architecture.
    For 64 bits Windows machine, this file should be downloaded: [https://github.com/astronomer/astro-cli/releases/download/v1.33.2/astro_1.33.2_windows_amd64.exe](https://github.com/astronomer/astro-cli/releases/download/v1.33.2/astro_1.33.2_windows_amd64.exe)
    v1.33.2 version is being used.

3.  Rename the downloaded file as `astro.exe`.

4.  Add the filepath for the directory containing `astro.exe` as a PATH environment variable.

5.  Restart the machine.

6.  After restarting, open Command Prompt and run the following command:
    ```bash
    winget install -e --id Astronomer.Astro
    ```
    This will upgrade the Astro CLI present in the machine.

7.  Open VS Code and open a folder in which you need to open a new terminal.

8.  Run the following commands to initialise and start a VM.
    ```bash
    podman machine init
    podman machine start
    ```
    Note: WSL2 should be enabled.

9.  Run the following command.
    ```bash
    podman run --rm -it postgres:12.6 whoami
    ```

10. Run the following command to change the default container management from Docker to Podman.
    ```bash
    astro config set container.binary podman -g
    ```

11. Create a new directory and navigate into it.

12. Run the following command to create an astro project that contains the set of files necessary to run Airflow, including dedicated folders for DAG files, plugins and dependencies.
    ```bash
    astro dev init
    ```

13. Run the following command to run Airflow locally.
    ```bash
    astro dev start
    ```

14. Open `http://localhost:8080/` and sign in to Apache Airflow.
    Default id: `admin`
    Default password: `admin`
