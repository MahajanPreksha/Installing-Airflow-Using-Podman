# Steps to install Apache Airflow on Windows using Podman Desktop
1. Install Podman Desktop and further, install Podman and Podman CLI extension.

2. Go to the [releases](https://github.com/astronomer/astro-cli/releases) page and download the setup file as per the system requirements.

3. Rename the downloaded file as `astro.exe`

4. Add the filepath for the directory containing astro.exe as a PATH environment variable.

5. Restart the machine.

6. After restarting, open Command Prompt and run the following command:
`winget install -e --id Astronomer.Astro`
> This will upgrade the Astro CLI present in the machine.

7. Open VS Code and open a folder in which you need to open a new terminal.

8. Run the following commands to initialise and start a VM.

`podman machine init`

`podman machine start`

> Note: WSL2 should be enabled.

9. Run the following command.

`podman run --rm -it postgres:12.6 whoami`

10. Run the following command to change the default container management from Docker to Podman.

`astro config set container.binary podman -g`

11. Create a new directory and navigate into it.

12. Run the following command to create an astro project that contains the set of files necessary to run Airflow, including dedicated folders for DAG files, plugins and dependencies.

`astro dev init`

13. Run the following command to run Airflow [locally](http://localhost:8080/).

`astro dev start`

14. Open http://localhost:8080/ and sign in into airflow.

Default id: admin

Default password: admin
