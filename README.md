# Computer Networks & IPC Implementations in C

## Overview
This repository contains low-level C implementations of fundamental computer networking protocols, socket programming, and Inter-Process Communication (IPC) mechanisms. It serves as a practical exploration of how data is framed, checked for errors, and transmitted across different transport layers (TCP/UDP).

## Core Concepts Demonstrated
* **Socket Programming:** Client-server architectures using both TCP (Transmission Control Protocol) and UDP (User Datagram Protocol).
* **Data Link Layer Protocols:** Implementation of Bit Stuffing for data framing.
* **Error Detection:** Implementation of Cyclic Redundancy Check (CRC) for network data integrity.
* **Inter-Process Communication (IPC):** Utilizing POSIX message queues for communication between isolated processes.

## Repository Map

Since these implementations are broken down into specific client/server pairs, use the table below to navigate the source files and their corresponding networking concepts.

| Networking Concept | Client File | Server File | Description |
| :--- | :--- | :--- | :--- |
| **TCP Chat Application** | `c1.c` | `s1.c` | Bi-directional communication stream using TCP sockets. |
| **UDP Chat Application** | `C.c` | `S.c` | Connectionless communication using UDP datagrams. |
| **TCP Bit Stuffing** | `bitC.c` | `bitS.c` | Data framing implementation adding non-information bits to break up continuous data streams over TCP. |
| **UDP Bit Stuffing** | `c.c` | `s.c` | Data framing implementation over UDP datagrams. |
| **TCP CRC (Error Check)** | `4c.c` | `4s.c` | Implementation of polynomial division to detect accidental changes to raw data over a TCP connection. |
| **UNIX Sockets (Sorting)** | `Client.c` | `server.c` | IPC using UNIX domain sockets to pass data for sorting operations. |
| **IPC Message Queues** | `r1.c`, `r2.c` | `r3.c` | Utilizing kernel-managed message queues for asynchronous data transfer between independent processes. |
| **IPv4 Header/Structure** | `ip1.c` | N/A | Parsing or structuring IPv4 data. |

## Compilation and Execution

These programs are written in standard C and require a POSIX-compliant environment (Linux/macOS) or WSL on Windows.

To run any client-server pair, open two separate terminal instances.

**1. Compile the server and client:**
```bash
gcc server_file.c -o server_out
gcc client_file.c -o client_out
