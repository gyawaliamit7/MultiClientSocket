# Socket Programming with Java

Socket Programming helps us to communicate with various computers running on a network. In Java, Socket programming can be either connection-oriented or connectionless. This project focuses on designing a connection-oriented application using the Client-Server model.

In the Client-Server model, the Server has a unique IP Address and port number. The client attempts to establish a connection with the server using this port number and IP address. The server listens and accepts the connection. Once the connection is established, the Server can receive messages from the client and respond back to the client.

## Implementation

### Server

#### `server/Main.java`

Main.java for the Server application binds to a specific port number using the ServerSocket Class. It creates a server socket and listens for a connection with the Client, accepting it. The ServerThread is instantiated and started. All threads are added to an ArrayList to allow multiple clients to send messages to each other.

### `server/ServerThread.java`

ServerThread.java receives sockets and a list of active threads from Main.java via its constructor. When the thread is started from Main, the run method is executed. The BufferedReader is used to receive information from the client, and PrintWriter is used to send information from the Server. The `printToAllClients()` method sends the output to each client in the thread.

### Client

#### `client/Main.java`

Main.java for the Client uses the Socket class to initiate a connection to a server by providing the IP address and port number. The Scanner is used to get input from the user and send the data to the server using the PrintWriter object.

#### `client/ClientThread.java`

ClientThread class is used to listen to responses from the server without getting blocked while reading from a Scanner. It uses BufferedReader to receive information from the client.

This project helps you understand the concepts of networking and the Client-Server model.

Hope this short article was helpful in understanding the fundamentals of networking with Java and the Client-Server model.

