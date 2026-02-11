# Pre-Session Instructions

## TASK 1. Complete the [Pre-session Survey](https://forms.office.com/r/Mi4dPaDyMN)
Please complete the [survey](https://forms.office.com/r/Mi4dPaDyMN). It should only take you ~5 minutes and it will help us customize the workshop to your needs and abilities.

<br>

## TASK 2. TVB Install, Setup, and Verification
<details>
 <summary> Click here to expand setup instructions </summary>

  
<br>

### 1. Follow Docker setup instructions 
This workshop uses a containerized software environment. Please install **Docker Desktop** on your computer prior to the workshop.



#### System Requirements
- A **64-bit** operating system  
- At least **4 GB of RAM** recommended  
- Privileges to install software
- At least **4 GB of storage** required

<br>

#### Windows

&emsp;&emsp; i) Download Docker Desktop for Windows: 

&emsp;&emsp; &emsp;&emsp; https://docs.docker.com/desktop/setup/install/windows-install/

&emsp;&emsp; ii) Follow the on-screen installation instructions.

&emsp;&emsp; iii) When prompted, enable **WSL 2** (Windows Subsystem for Linux).

&emsp;&emsp; &emsp;&emsp; _Docker Desktop will guide you through this if it is not already installed._

&emsp;&emsp; iv) Launch Docker Desktop and confirm it is running (you should see "Engine running" in the bottom left corner).


#### macOS

&emsp;&emsp; i) Download Docker Desktop for macOS: 

&emsp;&emsp; &emsp;&emsp; https://docs.docker.com/desktop/setup/install/mac-install/

&emsp;&emsp; ii) Choose the correct installer for your system: _**Apple Silicon (M1/M2/M3)** or **Intel** processor_

> Please note that if you are having issues installing Docker Desktop (e.g. you see a popup saying `You can't use this version of the application "Docker" with this version of MacOS`), you may have to try using an older version for [Intel](https://desktop.docker.com/mac/main/amd64/81317/Docker.dmg?_gl=1*1mdjioc*_gcl_au*ODk4NzU3MjU3LjE3NjgyNDEzMjU.*_ga*MTQ5NzM3OTU3Ni4xNzY4MjQxMzI1*_ga_XJWPQMJYHQ*czE3Njg1OTE1OTgkbzIkZzEkdDE3Njg1OTE3NDAkajQyJGwwJGgw) or [Apple Silicon](https://desktop.docker.com/mac/main/arm64/81317/Docker.dmg?_gl=1*12urgf8*_gcl_au*MzU4MDk1NzUwLjE3NjYwMjE5MzY.*_ga*MzgxMzY2NzY2LjE3NjYwMjE5MTg.*_ga_XJWPQMJYHQ*czE3Njg4NDE3MzMkbzgkZzEkdDE3Njg4NDE3MzUkajU4JGwwJGgw). If needed, other versions can be found [here](https://docs.docker.com/desktop/release-notes/).


&emsp;&emsp; iii) Follow the on-screen installation instructions.

&emsp;&emsp; iv) Launch Docker Desktop and confirm it is running (you should see "Engine running" in the bottom left corner).


#### Linux

&emsp;&emsp; Please see Docker's instructions for setup and usage. You may find it easier to [install Docker Engine using apt](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository) instead of installing Docker Desktop: https://docs.docker.com/engine/install/ubuntu/

> All `docker` commands you run on Linux must be preceded with `sudo`.

<br>


#### Verify Installation

After installation, open a terminal and run:

```bash
docker --version
```
If successful, you should see something along the lines of `Docker version 29.1.3, build f52814d`


<br>

---


<br>

### 2. Pull the Docker image
Once Docker Desktop is installed and running, you will need to download (pull) the workshop Docker image. This image contains all required software and dependencies for the workshop.

> **Important:** For Windows and MacOS users, Docker Desktop must be open and running before you proceed.


<br>

#### Windows
&emsp;&emsp; i) Open your preferred terminal application. You may use Windows PowerShell, Command Prompt, or Windows Terminal.

&emsp;&emsp; ii) Paste and run the following command:

```bash
docker pull lrokos/tvb_node:latest
```

<br>

#### macOS and Linux

&emsp;&emsp; i) Open a **Terminal**.

&emsp;&emsp; ii) Paste and run the following command:

```bash
docker pull lrokos/tvb_node:latest
```


<br>

---

<br>

### 3. Create a tvb folder on your computer

&emsp;&emsp; i) Create a folder called `tvb` on your computer. You may choose to place it in your Documents folder.

&emsp;&emsp; ii) Copy the full filepath to this `tvb` folder

&emsp;&emsp; &emsp;&emsp;    - MacOS and Linux users can right-click their `tvb` folder and then press `Copy`

&emsp;&emsp; &emsp;&emsp;    - Windows users can right-click their `tvb` folder and then press `Copy as path` or `Ctrl+Shift+C`


<br>

---

<br>

### 4. Start your JupyterLab Session

&emsp;&emsp; i) Ensure Docker Desktop is running (disregard if using Docker Engine on Linux).

&emsp;&emsp; ii) Open your preferred terminal application (see Section 2 for instructions on which application to use) if not already open

&emsp;&emsp; iii) Paste and run the following command, substituting `/your/tvb/path/here` with the filepath you copied in Section 3:

```bash
docker run -p 8888:8888 -v /your/tvb/path/here:/tvb_node/tvb lrokos/tvb_node:latest
```

&emsp;&emsp; iii) Your terminal should display a message like the following. Copy either of the three paths from your terminal into your internet browser address bar (try one of the other paths if one doesn't work).

```bash
    To access the server, open this file in a browser:
        file:path.html
    Or copy and paste one of these URLs:
        http://URL
     or http://URL
```

<br>

---

<br>

### 5. Clone a copy of this tvb-node repository onto your computer

&emsp;&emsp; i) In the JupyterLab window in your internet browser, locate the navigation pane on the left side.

&emsp;&emsp; ii) Double click the `tvb` folder to enter it.

&emsp;&emsp; iii) Open a Terminal tab by pressing `Terminal` under the `Other` heading on the right side.

&emsp;&emsp; iv) Running the `pwd` command should output `/tvb_node/tvb`. If not, run `cd /tvb_node/tvb`.

&emsp;&emsp; v) Paste and run the following command: `git clone https://github.com/McIntosh-Lab/tvb-node-mclab.git`

&emsp;&emsp; vi) The tvb-node repository should now exist on your local computer in the `tvb` folder!

<br>

---

<br>

### 6. Verify your installation with the Installation_Test.ipynb notebook

&emsp;&emsp; i) In the JupyterLab window, navigate inside `tvb-node` folder

&emsp;&emsp; ii) Then enter the `Pre-Session_Materials` folder

&emsp;&emsp; iii) Double-click `Installation_Test.ipynb` to launch the notebook.

&emsp;&emsp; iv) Follow the instructions in the notebook to verify your installation.

<br>

---

<br>

### 7. Subsequent Usage

You do not need to reinstall Docker or re-clone `tvb-node` every time you want to use this container to run TVB. You just need to:

&emsp;&emsp; i) Launch Docker Desktop

&emsp;&emsp; ii) Run `docker pull lrokos/tvb_node:latest` on a terminal to update the container 

&emsp;&emsp; iii) Run `docker run -p 8888:8888 -v /your/tvb/path/here:/tvb_node/tvb lrokos/tvb_node:latest` on a terminal to launch the JupyterLab server

&emsp;&emsp; iv) Open the JupyterLab link in a browser

</details>

<br>

## TASK 3. Watch Past Recordings
Please watch the first introductory video to TVB, linked below, from a similar [TVB workshop series](https://github.com/McIntosh-Lab/tvb_study_group/tree/main). We recommend watching the second video if you are unfamiliar with structural connectomes or have questions about connectome generation.
1. [**TVB Foundational Theory**](https://www.youtube.com/watch?v=Su8jnMatJTw) - A (nearly) math-free primer on large-scale modelling in TheVirtualBrain

2. [**Post-processing Considerations _(optional)_**](https://www.youtube.com/watch?v=P9hkfTLyz2k) - Imaging inputs and post-processing considerations for brain network modelling

<br>

## TASK 4. Bring a Laptop to the Session
Please ensure that you bring a computer with at least 4 GB of RAM and 1 GB of storage (after completion of TVB Install, Setup, and Verification) as well as a charger.
