# C++ Qt Chat Application

Welcome to the **C++ Qt Chat Application**! This project demonstrates a real-time chat system built using C++, the Qt framework, and Qt Creator. It consists of two main components: **Server** and **Client** applications. The client application can connect to the server, allowing multiple clients to chat, send/receive files, and broadcast messages.

---

## Features

- **Multi-Client Chat**: Multiple clients can connect to the server and engage in real-time chat.
- **File Sharing**: Clients can send and receive files directly within the chat interface.
- **Broadcast Messaging**: Clients can broadcast messages to all connected clients.
- **Qt TCP/IP Socket Communication**: Built using Qt’s TCP/IP socket classes for reliable network communication.

---

## Tech Stack

- **Programming Language**: C++
- **Framework**: Qt (using Widgets, Core, Network modules)
- **Build Tool**: CMake
- **IDE**: Qt Creator

---

## Directory Structure

### Server Application

```plaintext
├── chatprotocol.cpp
├── chatprotocol.h
├── clientchatwidget.cpp
├── clientchatwidget.h
├── clientchatwidget.ui
├── clientmanager.cpp
├── clientmanager.h
├── CMakeLists.txt
├── icons/
├── icons.qrc
├── main.cpp
├── mainwindow.cpp
├── mainwindow.h
├── mainwindow.ui
├── servermanager.cpp
└── servermanager.h
```

### Client Application

```plaintext
├── chatitemwidget.cpp
├── chatitemwidget.h
├── chatitemwidget.ui
├── chatprotocol.cpp
├── chatprotocol.h
├── clientmanager.cpp
├── clientmanager.h
├── CMakeLists.txt
├── main.cpp
├── mainwindow.cpp
├── mainwindow.h
└── mainwindow.ui
```

---

## Build and Run

### Prerequisites

- **Qt**: Install the Qt framework (version 5 or 6).
- **Qt Creator**: For development and building the project.
- **CMake**: Version 3.5 or higher.

### Steps to Build

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/chat-application.git
   cd chat-application
   ```

2. **Open Project in Qt Creator**:
   - Launch **Qt Creator** and open the project.
   - Select the `CMakeLists.txt` file of either the Server or Client directory.

3. **Configure and Build**:
   - Qt Creator will configure the project automatically if CMake is set up correctly.
   - Choose **Build** from the menu to compile the Server and Client applications.

4. **Run the Applications**:
   - Start the **Server** application first to listen for incoming connections.
   - Then, start multiple instances of the **Client** application to simulate multiple users.

---

## Usage

1. **Start the Server**: The server will begin listening for client connections.
2. **Connect Clients**: Open the Client application, enter the server IP and port, and connect.
3. **Chat and Share Files**: 
   - Send messages between clients connected to the same server.
   - Use the file sharing feature to send and receive files.
   - Broadcast a message to all connected clients.

---

## CMake Configuration

The CMake configuration files for each application are located in their respective directories.

### Server `CMakeLists.txt`

```cmake
cmake_minimum_required(VERSION 3.5)
project(Server VERSION 0.1 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
find_package(QT NAMES Qt6 Qt5 COMPONENTS Widgets REQUIRED)
find_package(Qt${QT_VERSION_MAJOR} COMPONENTS Widgets Core Network REQUIRED)
set(PROJECT_SOURCES main.cpp mainwindow.cpp mainwindow.h mainwindow.ui ...)
target_link_libraries(Server PRIVATE Qt${QT_VERSION_MAJOR}::Widgets Qt${QT_VERSION_MAJOR}::Core Qt${QT_VERSION_MAJOR}::Network)
```

### Client `CMakeLists.txt`

```cmake
cmake_minimum_required(VERSION 3.5)
project(Client VERSION 0.1 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
find_package(QT NAMES Qt6 Qt5 COMPONENTS Widgets REQUIRED)
find_package(Qt${QT_VERSION_MAJOR} COMPONENTS Widgets Core Network REQUIRED)
set(PROJECT_SOURCES main.cpp mainwindow.cpp mainwindow.h mainwindow.ui ...)
target_link_libraries(Client PRIVATE Qt${QT_VERSION_MAJOR}::Widgets Qt${QT_VERSION_MAJOR}::Core Qt${QT_VERSION_MAJOR}::Network)
```

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

---

## Acknowledgments

This project utilizes the power of the Qt framework for its intuitive and cross-platform-friendly UI and robust network handling.