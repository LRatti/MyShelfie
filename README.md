# MyShelfie - Digital version

![MyShelfie Board Game Box](https://www.craniocreations.it/storage/media/products/54/112/My_Shelfie_box_ITA-ENG.png)

This project is a digital adaptation of the board game **My Shelfie**, developed for the Software Engineering course at Politecnico di Milano (A.Y. 2022/2023). It fully implements the game's rules and supports multiplayer gameplay over a network.

## Features

This implementation of My Shelfie includes the following features:

-   **Complete Game Rules:** The entire rulebook of the original board game is implemented.
-   **Multiple User Interfaces:** Players can choose between two different interfaces:
    -   **CLI (Command-Line Interface):** A text-based interface for a classic experience.
    -   **GUI (Graphical User Interface):** A rich visual interface built with JavaFX.
-   **Network Play:** Supports multiplayer games over the network using two different protocols:
    -   **RMI (Remote Method Invocation)**
    -   **Socket**
-   **Resilience to Disconnections:** Players who disconnect due to network issues or client crashes can reconnect to the same game and continue playing. The game proceeds by skipping the disconnected player's turns. If only one player remains, the game is paused until another player reconnects or a timeout is reached.
-   **In-Game Chat:** A chat system allows players to communicate with each other during a match, with support for both public messages (to all players) and private messages (to a specific player).

## Getting Started

To run the game, you will need to have Java installed on your machine. You can download the executable JAR file from the project's releases.

[**Download the latest JAR here**](https://github.com/rivitti01/ing-sw-2023-ratti-rivitti-salvatore-sanduleanu/releases/download/MyShelfie/softeng-gc30-1.0-SNAPSHOT-jar-with-dependencies.jar)

### How to Run the Server

First, start the server. Open a terminal and run the following command, replacing the placeholders with your desired configuration:

```bash
java -jar [jar_name].jar [ipAddress] [socketPort] [rmiPort]
```

-   `[jar_name].jar`: The name of the downloaded JAR file (e.g., `softeng-gc30-1.0-SNAPSHOT-jar-with-dependencies.jar`).
-   `[ipAddress]`: The IP address the server will run on.
-   `[socketPort]`: The TCP port for the Socket connection.
-   `[rmiPort]`: The port for the RMI registry.

**Example:**
```bash
java -jar softeng-gc30-1.0-SNAPSHOT-jar-with-dependencies.jar 192.168.1.50 2000 1099
```

### How to Run the Client

Once the server is running, one or more clients can connect to it. Open a new terminal for each client and use the following command:

```bash
java -jar [jar_name].jar [G/T] [R/S] [ipAddress] [socketPort] [rmiPort]
```

-   `[G/T]`: Choose the user interface.
    -   `G` for Graphical User Interface (GUI).
    -   `T` for Text-based/Terminal Interface (CLI).
-   `[R/S]`: Choose the network protocol.
    -   `R` for RMI.
    -   `S` for Socket.
-   The remaining parameters must match the ones used to start the server.

**Example (GUI with Socket):**
```bash
java -jar softeng-gc30-1.0-SNAPSHOT-jar-with-dependencies.jar G S 192.168.1.50 2000 1099
```

**Example (CLI with RMI):**
```bash
java -jar softeng-gc30-1.0-SNAPSHOT-jar-with-dependencies.jar T R 192.168.1.50 2000 1099
```

## Project Structure

The project follows the Model-View-Controller (MVC) architectural pattern:

-   `src/main/java/it/polimi/ingsw/model`: Contains the game logic, including the state of the board, players, cards, and rules.
-   `src/main/java/it/polimi/ingsw/view`: Implements the user interfaces (both CLI and GUI).
-   `src/main/java/it/polimi/ingsw/controller`: Acts as a bridge between the model and the view, processing user input and updating the game state.
-   `src/main/java/it/polimi/ingsw/distributed`: Manages the network infrastructure, with sub-packages for `rmi` and `socket` implementations.

## Disclaimer

My Shelfie is a board game developed and published by Cranio Creations Srl. The graphical assets in this project that are attributable to the tabletop game product are used with the approval of Cranio Creations Srl for educational purposes only. Any distribution, copying, or reproduction of the content and images in any form outside of this project is prohibited, as is the redistribution and publication of the content and images for purposes other than the one mentioned above. Commercial use of this content is also forbidden.

## Authors

-   [**Leonardo Ratti**](https://github.com/LRatti)
-   [**Francesco Rivitti**](https://github.com/rivitti01)
-   [**Alessandro Salvatore**](https://github.com/SAAL01)
-   [**Denis Sanduleanu**](https://github.com/DenSandu)
