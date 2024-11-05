MyServer.java
```java
import java.io.*;
import java.net.*;

public class MyServer {
    public static void main(String[] args) {
        try {
            ServerSocket ss = new ServerSocket(6666);
            Socket s = ss.accept(); // establishes connection
            DataInputStream dis = new DataInputStream(s.getInputStream());
            String str = (String) dis.readUTF();
            System.out.println("message= " + str);
            ss.close();
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

MyClient.java
```java
import java.io.*;
import java.net.*;

public class MyClient {
    public static void main(String[] args) {
        try {
            Socket s = new Socket("localhost", 6666);
            DataOutputStream dout = new DataOutputStream(s.getOutputStream());
            dout.writeUTF("Hello Server");
            dout.flush();
            dout.close();
            s.close();
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output**
To execute this program open two command prompts and execute each program at each command prompt as displayed in the below figures.
First run `Myserver.java` file in terminal/cmd


---
---
---
---

# What is a Socket?
- **Socket**: An interface between an application process and the transport layer. The application process can send and receive messages to/from another application process (either local or remote) via a socket.

# Client/Server Communication
At a basic level, network-based systems consist of a server, client, and a communication medium (either wired or wireless network).

- **Client machine**: A computer running a program that makes requests for services.
- **Server machine**: A computer running a program that offers requested services to one or more clients.

In a computer network system, communication occurs through message passing, typically between the client and server. Socket programming is used to facilitate communication between the client and server.

## Simple One-Way Client-Server Communication
In this setup:

- The client sends a message to the server.
- The server reads the message and prints it.

This uses two classes:

- **Socket**: Used for communication between client and server. It allows reading and writing messages.
- **ServerSocket**: Used on the server side. The `accept()` method blocks the console until the client connects. Once connected, it returns an instance of `Socket` on the server side.

# Socket Class
A socket is simply an endpoint for communications between machines. The Socket class is used to create a socket.

# ServerSocket Class
The ServerSocket class is used to create a server socket. This object establishes communication with the clients.

## Creating a Server
To create a server application:

- Create an instance of the ServerSocket class.
- Use a port number (e.g., 6666) for communication.
- The `accept()` method waits for the client to connect and returns a `Socket` instance upon successful connection.

```java
ServerSocket ss = new ServerSocket(6666);
Socket s = ss.accept(); // Establishes connection and waits for the client
```

Creating a Client
To create a client application:

- Create an instance of the Socket class.
- Provide the IP address or hostname of the server and a port number.
- Use "localhost" if the server is on the same system.

```java
  Socket s = new Socket("localhost", 6666);
```
