# Counter-Strike 2 Server (CS2) Docker Container for ARM64

## [Docker Image](https://hub.docker.com/r/teriyakigod/cs2-server)

This repository contains a Dockerfile and instructions to build a Counter-Strike 2 (CS2) server using Docker on ARM64 devices. This allows you to easily set up and run a CS2 server on compatible ARM64 hardware.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Docker: You can download and install Docker for your ARM64 device following the official Docker documentation.

## Building the Docker Container

To build the CS2 server Docker container, follow these steps:

1. Clone this repository to your local system if you haven't already:

   ```bash
   git clone https://github.com/yourusername/cs2-server-docker-arm64.git
   ```

2. Change your working directory to the cloned repository:

   ```bash
   cd cs2-server-docker-arm64
   ```

3. Build the Docker container using the provided Dockerfile:

   ```bash
   docker build -t cs2-server:arm64 .
   ```

## Running the CS2 Server

1. Once you have built the Docker container, you can start the CS2 server container by running the following command:

   ```bash
   docker run -it -p 27015:27015/tcp -p 27015:27015/udp -p 27020:27020/udp -p 27005:27005/udp -p 26900:26900/udp cs2-server:arm64
   ```
   
2. To download server files and/or update run this:
   
   ```bash
   FEXInterpreter ./steamcmd.sh +force_install_dir /opt/cs +login $login +app_update 730 validate +exit
   ```
3. To start the server:
   ```bash
   FEXInterpreter /opt/cs/game/bin/linuxsteamrt64/cs2 -dedicated +map de_dust2
   ```

- `-p` flag: This maps the necessary ports for the CS2 server to communicate over. Adjust these ports as needed.

## Note

- This Docker container is intended for use on ARM64 devices. Ensure your hardware is compatible before building and running the container.
- The server will run in interactive mode (`-it`), which is useful for debugging and monitoring the server. You can detach from the container by pressing `Ctrl + P` followed by `Ctrl + Q`.
- Make sure you have the necessary SteamCMD login credentials to download and update the CS2 server files.
- You may want to customize the server settings and configurations according to your preferences. Check the CS2 server documentation for more details.
