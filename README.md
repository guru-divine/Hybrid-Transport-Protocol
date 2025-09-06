<p align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/6295/6295417.png" width="100" />
</p>
<p align="center">
    <h1 align="center">Hybrid Transport Protocol</h1>
</p>
<p align="center">
    <em>Emulating End-to-End Reliable Flow Control over Unreliable Communication Channels</em>
</p>
<p align="center">
		<em>Developed with the software and tools below.</em>
</p>
<p align="center">
	<img src="https://img.shields.io/badge/C-A8B9CC.svg?style=flat&logo=C&logoColor=black" alt="C">
</p>
<hr>

##  Quick Links

> - [ Overview](#overview)
> - [ Features](#features)
> - [ Repository Structure](#repository-structure)
> - [ Modules](#modules)
> - [ Getting Started](#getting-started)
>   - [ Installation](#installation)
>   - [ Running MTP](#running-MTP)
> - [ Contributing](#contributing)
> - [ Acknowledgments](#acknowledgments)

---

##  Overview


HTP is a custom transport protocol developed to provide reliable, in-order delivery of messages over the inherently unreliable UDP protocol. HTP employs window-based flow control to ensure data integrity and delivery. It is designed to handle packet loss, delays, and reordering that are common in unreliable communication channels.

---

## Features

- **Reliable Delivery**: Ensures all packets are delivered correctly.
- **In-Order Delivery**: Maintains the order of packets.
- **Window-Based Flow Control**: Manages data flow between sender and receiver.
- **Packet Loss Simulation**: Includes a function to simulate packet loss for testing.
- **Threaded Architecture**: Utilizes threads for efficient handling of sending, receiving, and garbage collection.
- **Shared Memory Synchronization**: Ensures synchronization across multiple sockets.

---

##  Repository Structure

```sh
└── HTP/
    ├── Makefile
    ├── Makefile_initmsocket
    ├── Makefile_libmsocket
    ├── Makefile_users
    ├── README.md
    ├── file_to_transfer.txt
    ├── initmsocket.c
    ├── msocket.c
    ├── msocket.h
    ├── user1.c
    └── user2.c
```

---

## Modules

| File                                                                                         | Summary                                          |
| -------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| [Makefile](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/Makefile)                         | General Makefile for building the project.         |
| [Makefile_initmsocket](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/Makefile_initmsocket) | Makefile for initializing MTP socket.              |
| [Makefile_libmsocket](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/Makefile_libmsocket)   | Makefile for compiling MTP library.                |
| [Makefile_users](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/Makefile_users)             | Makefile for compiling user applications.          |
| [initmsocket.c](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/initmsocket.c)               | Initializes sockets and manages threads for message handling and garbage collection. |
| [msocket.c](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/msocket.c)                       | Core MTP socket implementation.                   |
| [msocket.h](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/msocket.h)                       | Header file for MTP socket.                       |
| [user1.c](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/user1.c)                           | Another example user application utilizing MTP.    |
| [user2.c](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/user2.c)                           | Example user application utilizing MTP.           |
| [file_to_transfer.txt](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/file_to_transfer.txt) | Sample file used for testing file transfer.        |


---

##  Getting Started

***Requirements***

Ensure you have the following dependencies installed on your system:

* **C**: `version above C11`

###  Installation

1. Clone the HTP repository:

```sh
git clone https://github.com/guru-divine/Hybrid-Transport-Protocol
```

2. Change to the project directory:

```sh
cd Hybrid-Transport-Protocol
```

3. Compile the files:

```sh
make
```

3. Start init thread:

```sh
./initmsocket 
```

###  Running HTP

Open another two terminals, one for sending and another for receiving file:

In first terminal,

```sh
./user2 127.0.0.1 8000 127.0.0.1 5000
```

In second terminal,

```sh
./user1 127.0.0.1 5000 127.0.0.1 8000
```
Similarly, you can open as many terminals as you want to run multiple socket pairs simultaneously.

![image](https://github.com/guru-divine/Hybrid-Transport-Protocol/assets/108367037/d298a592-e43a-4d6e-a47e-ed2896beb164)

##  Contributing

Contributions are welcome! Here are several ways you can contribute:

- **[Submit Pull Requests](https://github.com/guru-divine/Hybrid-Transport-Protocol/blob/main/CONTRIBUTING.md)**: Review open PRs, and submit your own PRs.
- **[Join the Discussions](https://github.com/guru-divine/Hybrid-Transport-Protocol/discussions)**: Share your insights, provide feedback, or ask questions.
- **[Report Issues](https://github.com/guru-divine/Hybrid-Transport-Protocol/issues)**: Submit bugs found or log feature requests for Mtp.

<details closed>
    <summary>Contributing Guidelines</summary>

1. **Fork the Repository**: Start by forking the project repository to your GitHub account.
2. **Clone Locally**: Clone the forked repository to your local machine using a Git client.
   ```sh
   git clone https://github.com/guru-divine/Hybrid-Transport-Protocol
   ```
3. **Create a New Branch**: Always work on a new branch, giving it a descriptive name.
   ```sh
   git checkout -b new-feature-x
   ```
4. **Make Your Changes**: Develop and test your changes locally.
5. **Commit Your Changes**: Commit with a clear message describing your updates.
   ```sh
   git commit -m 'Implemented new feature x.'
   ```
6. **Push to GitHub**: Push the changes to your forked repository.
   ```sh
   git push origin new-feature-x
   ```
7. **Submit a Pull Request**: Create a PR against the original project repository. Clearly describe the changes and their motivations.

Once your PR is reviewed and approved, it will be merged into the main branch.

</details>

---

[**Return**](#quick-links)

---
