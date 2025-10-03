# RCR Foundations: UNIX, Git, Raspberry Pi and More

Welcome to **RCR Foundations**, a collection of concise, practical guides designed to bring learners up to speed on the tools and techniques required for modern robotics and engineering courses.  Each guide is a self‑contained Markdown file and may be reused across multiple courses as pre‑work or reference material.  This repository is intentionally modular so that you can dive directly into the topics you need without wading through a single monolithic document.

## Contents

| Area | Description |
| --- | --- |
| **[UNIX](unix/README.md)** | Become productive at the command line. Covers terminal basics, navigation, text editors, permissions, and shell scripting. |
| **[Git](git/README.md)** | Learn version control from the ground up: why Git matters, how to set it up, commit, branch and merge, work with remotes and GitHub, and use GitHub CLI. |
| **[Raspberry Pi 5 + Ubuntu 24](rpi-ubuntu/README.md)** | Flash Ubuntu 24 onto a Raspberry Pi 5, complete first‑boot setup, manage packages, configure remote development with VS Code, build servers, and troubleshoot common issues. |
| **[Microcontrollers](microcontrollers/README.md)** | Install Arduino CLI, add Teensy board support, compile sketches, and upload firmware using the Teensy loader CLI. |
| **[Docker](docker/README.md)** | Set up Docker Engine on Ubuntu 24 ARM64 (Pi 5) using the official apt repository and learn basic container usage. |
| **[Data Labeling](data-labeling/README.md)** | Learn data annotation fundamentals and set up Label Studio on your Raspberry Pi for creating high-quality labeled datasets for machine learning projects. |
| **[Imaging & Flashing](imaging/README.md)** | Flash disk images onto Raspberry Pi microSD cards using Raspberry Pi Imager or `dd`, and flash firmware onto Teensy microcontrollers. |
| **[Windows Tools](windows/README.md)** | Use PuTTY as an SSH terminal on Windows; learn copy/paste semantics and how to manage sessions. |
| **[Development Tools](dev-tools/README.md)** | Install and configure GitHub CLI on Linux, macOS and Windows; set up the Cursor AI code editor on personal machines (Mac/Windows). |

## Who this is for

These guides were written for adult learners and professionals who may be new to the tools but bring curiosity and motivation.  The material starts at the beginner level and scales up to intermediate usage.  While developed for the RCR (Rose City Robotics) curriculum, the guides are intentionally generic so they can serve any robotics, control or embedded systems course.

## How to use this repository

1. **Choose your topic.**  Navigate to the appropriate folder listed above.  Each folder’s `README.md` explains the purpose of the sub‑documents and suggests an order to read them.
2. **Follow the numbered guides.**  Files are numbered to indicate a learning progression.  Work through them sequentially or jump straight to the section you need.
3. **Keep the resources handy.**  Each topic folder includes a `resources.md` file with links to authoritative external references, tutorials and videos, many of which informed these guides.
4. **Look at the wiki.**  If you mirror these files into a GitHub wiki, you can provide top‑level navigation for students on GitHub.  See [`wiki-instructions.md`](wiki-instructions.md) for details on publishing a wiki from this repository.

## Installing tools on personal vs. Pi machines

Most of the microcontroller development and robotics code will run on your **Raspberry Pi 5 running Ubuntu 24**.  This includes the Arduino CLI, Teensy board support, Docker, Label Studio, and server software.  Tools such as **GitHub CLI** and the **Cursor AI editor** should be installed on your **own laptop or desktop (macOS or Windows)**.  When a guide requires installation on a personal machine versus on the Raspberry Pi, it calls this out explicitly.

## Contributing

Contributions are welcome!  Please open an issue to discuss your proposed change, then submit a pull request.  Keep lessons short, practical and beginner‑friendly.  Use US English, sentence‑case headings, and fenced code blocks with language hints.

## License

All content in this repository is licensed under the Creative Commons Attribution 4.0 International (CC BY 4.0).  You are free to share and adapt the material so long as you provide appropriate credit.
