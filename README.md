# My Shelfie - Digital Edition

![My Shelfie Board Game Box](https://www.craniocreations.it/storage/media/products/54/112/My_Shelfie_box_ITA-ENG.png)

This project is a digital adaptation of the board game "My Shelfie" by Cranio Creations, developed as the final project for the Software Engineering course at Politecnico di Milano (A.Y. 2022/2023). It's a multiplayer game that supports network play through both RMI and Socket protocols, featuring both a Command-Line Interface (CLI) and a Graphical User Interface (GUI).

## ✨ Features

- **Complete Rule Set:** Implements all the core rules of the "My Shelfie" board game.
- **Multiple Interfaces:** Play using either a rich Graphical User Interface (GUI) built with JavaFX or a classic Command-Line Interface (CLI).
- **Network Play:** Supports multiplayer games over the network using two different protocols:
    - **RMI** (Remote Method Invocation)
    - **Socket** communication
- **Resilience to Disconnections:** Players who get disconnected due to network issues or client crashes can reconnect to the ongoing game. The game proceeds by skipping the disconnected player's turns, and if only one player remains, the game pauses until another player reconnects or a timeout is reached.
- **In-Game Chat:** A full-featured chat allows players to communicate during the game. Messages can be sent to everyone or privately to a specific player.

## 🚀 How to Run

### Prerequisites
- Java Development Kit (JDK) 19 or later.

### Download
You can download the executable JAR file, which includes all dependencies, from the [GitHub Releases page](https://github.com/rivitti01/ing-sw-2023-ratti-rivitti-salvatore-sanduleanu/releases/download/MyShelfie/softeng-gc30-1.0-SNAPSHOT-jar-with-dependencies.jar).

### 1. Running the Server
The server must be started first to allow clients to connect. Open your terminal and run the following command:

```bash
java -jar [jar_file_name].jar [ipAddress] [socketPort] [rmiPort]
```
- `[jar_file_name].jar`: The name of the downloaded JAR file (e.g., `softeng-gc30-1.0-SNAPSHOT-jar-with-dependencies.jar`).
- `[ipAddress]`: The IP address the server will bind to. Use your machine's local network IP to allow others on the same network to connect.
- `[socketPort]`: The TCP port for Socket connections.
- `[rmiPort]`: The port for RMI connections.

**Example:**
```bash
java -jar softeng-gc30-1.0-SNAPSHOT.jar 192.168.1.10 2000 1099
```

### 2. Running the Client
Once the server is running, players can join by launching the client.

```bash
java -jar [jar_file_name].jar [UI_Type] [Network_Type] [ipAddress] [socketPort] [rmiPort]
```
- `[UI_Type]`: Choose the user interface.
    - `G`: Graphical User Interface (GUI)
    - `T`: Text-based/Command-Line Interface (CLI)
- `[Network_Type]`: Choose the network protocol.
    - `R`: RMI
    - `S`: Socket
- `[ipAddress]`: The IP address of the running server.
- `[socketPort]`: The server's Socket port.
- `[rmiPort]`: The server's RMI port.

**Example (GUI with Socket):**
```bash
java -jar softeng-gc30-1.0-SNAPSHOT.jar G S 192.168.1.10 2000 1099
```

**Example (CLI with RMI):**
```bash
java -jar softeng-gc30-1.0-SNAPSHOT.jar T R 192.168.1.10 2000 1099```

## 🧪 Testing
The project includes a comprehensive suite of unit tests written with JUnit to ensure code quality and correctness. You can view the test coverage report [here](https://github.com/rivitti01/ing-sw-2023-ratti-rivitti-salvatore-sanduleanu/blob/main/documents/image.png).

## ⚖️ Disclaimer
My Shelfie is a board game developed and published by Cranio Creations Srl. The graphical content in this project that is attributable to the original board game is used with the approval of Cranio Creations Srl for educational purposes only. The distribution, copying, or reproduction of the content and images in any form outside of this project, as well as the redistribution and publication of the content and images for purposes other than the one mentioned above, is prohibited. Commercial use of said content is also forbidden.

## 👥 Authors
This project was developed by:
- [**Leonardo Ratti**](https://github.com/LRatti)
- [**Francesco Rivitti**](https://github.com/rivitti01)
- [**Alessandro Salvatore**](https://github.com/SAAL01)
- [**Denis Sanduleanu**](https://github.com/DenSandu)
