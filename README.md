# CExec

CExec is a simple client-server application built in C on Linux. It allows a client to send C source code to a server, where the code is compiled using GCC and executed. The server then sends the program's output and any compilation errors back to the client.

The project was built to understand how client-server communication, process management, and system-level programming work in Linux.

## Features

- Send C source code from a client to a server over TCP.
- Compile programs using GCC on the server.
- Execute compiled programs and capture their output.
- Return compilation errors and execution results to the client.
- Handle multiple clients using POSIX threads.
- Use Linux system calls and process management APIs.
- Validate filenames and paths before working with files.

## Technologies Used

- C
- Linux and POSIX APIs
- TCP sockets
- GCC
- POSIX threads
- Process management using `fork()`, `exec()`, and `waitpid()`

## How It Works

1. The client sends C source code to the server over a TCP connection.
2. The server receives and stores the source code.
3. GCC compiles the program.
4. The server executes the compiled program and captures its output.
5. The result or compilation error is sent back to the client.

## Running the Project

Clone the repository and move into the project directory.

```bash
git clone <repository-url>
cd CExec
```

Compile the client and server using GCC. Replace the filenames below with the actual source filenames in the project.

```bash
gcc server.c -o server -pthread
gcc client.c -o client
```

Start the server in one terminal:

```bash
./server
```

Run the client in another terminal:

```bash
./client
```

Make sure the server address and port configured in the client match the server configuration.

## Purpose

This project helped me learn how network communication, multithreading, file handling, and process execution work together in a Linux environment.

It is a learning project focused on understanding the fundamentals rather than relying on an existing code execution service.
