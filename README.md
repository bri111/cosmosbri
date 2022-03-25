# COSMOS: Comprehensive Open-architecture Solution for Mission Operations Systems

COSMOS is a software framework for operating distributed robotic systems, with a particular focus on space systems such as CubeSats, including satellite swarms and constellations. It is a software ecosystem with various applications from the embedded flight software to ground station management software, to the mission operations center user interfaces. COSMOS is developed at the [Hawaii Space Flight Laboratory](https://www.hsfl.hawaii.edu/) and can be deployed in CubeSats, Rovers, Scientific Instruments and more. Let's build the COSMOS for your next amazing application!

<img src="https://user-images.githubusercontent.com/1541868/160047280-010609a7-596a-4eef-a3d7-5ccc59dbb247.PNG" width=100%>

COSMOS is a system that is designed to primarily support the development and operations of one or more small spacecraft and is particularly suited for organizations with limited development and operations budget, such as universities. COSMOS is currently in active development. COSMOS is designed to be seamlessly integrated and compatible with multiple different resources (nodal architecture) or nodes such as satellites, unmanned air systems (UASs), ground control stations, computer stations, etc. and it is being expanded to address simulation scenarios with complex nodal architectures where events can be detected and actions triggered. It has been developed in the new paradigm of the network-of-things where any asset can be connected to the system in a plug and play approach making it very generic for the inclusion and removal of assets. When an asset is connected and is COSMOS compatible, all the system can be informed of its presence and receive telemetry that can be processed to take actions. COSMOS is a suite of software (including external modules) that enables the operations team to interface with the spacecraft, ground control network, payload and other customers in order to perform the mission operations functions including mission planning and scheduling; contact operations; data management and analysis; simulations (including the operational testbed); ground network control; payload operations; flight dynamics; and system management. COSMOS is being designed to easily be adapted for new spacecraft or installation in new mission operations centers (MOCs).

## Getting Started

We recommend installing COSMOS via Docker. By using Docker containers you will get all the COSMOS dependencies automatically resolved. This process works well for users and developers.

* [Install Docker Desktop](https://www.docker.com/get-started/)
* [Install Docker Compose](https://docs.docker.com/compose/install/) (Only needed for a Linux OS. Docker compose is automatically installed on Docker Desktop on Windows and macOS)

Once you have Docker installed we are going to clone the cosmos repository. Open your terminal window, copy and run the following command.

On Windows: clone cosmos to c:/cosmos (recommended path)
```shell
git clone https://github.com/hsfl/cosmos.git c:/cosmos
```

On Linux and macOS: clone cosmos to the home folder ~/cosmos (recommended path)
```shell
git clone https://github.com/hsfl/cosmos.git ~/cosmos
```

To build the cosmos image go into the newly created folder and run the Docker build command (this step may take several minutes to complete):

```bash
cd c:/cosmos
docker build -t cosmos .
```

Once the build has been completed, run the 'cosmos' container:

```
docker run -it --name cosmos cosmos
```

Let's start agent_001 and agent_002 to test some cosmos features:

```
cd bin
./agent_001
```

now open a new terminal window to start agent_002:
```
docker run -it cosmos
cd bin
./agent_002
```

Alternatively you can create the docker container 'cosmos' in detach mode and then easily run each agent from the terminal window:
```
docker run -t -d --name cosmos cosmos
docker exec cosmos /root/cosmos/bin/agent_001
docker exec cosmos /root/cosmos/bin/agent_002
```

## Open the Source Code
- Start Visual Studio Code. [ Docker](https://code.visualstudio.com/)
- Install extensions: 'Docker' and 'Remote Containers'
- Click 'Open a Remote Window' on the bottom left corner of Visual Studio Code. 
- Select 'Attach to Running Container'. Select the cosmos container
- Open 'cosmos folder in container

## How do I continue from here?
**Visit the COSMOS Website to get started:** [https://hsfl.github.io/cosmos-docs/](https://hsfl.github.io/cosmos-docs/). The website contains the getting started guides, tutorials, examples and more!
