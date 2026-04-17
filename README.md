# Simple C++ Networking Library

A lightweight, beginner-friendly C++ networking library for Windows, built on top of Winsock2. Designed with multiplayer game development in mind.

## Features

- **Server** — Accept and manage multiple client connections over TCP
- **Client** — Connect to a server and send/receive data
- **Packet** — Serialise and deserialise structured messages
- **Connection** — Track and manage individual client sessions

## Requirements

- Windows 10/11
- MSVC or MinGW (C++17 or later)
- CMake 3.20+

## Building

```bash
cmake -S . -B build
cmake --build build
```

## Running Tests

```bash
cd build
ctest --output-on-failure
```

## License

MIT
