# -IPC-Using-Message-Queue-in-C


This repository contains a simple demonstration of Inter-Process Communication (IPC) using message queues in C. The demonstration includes two programs: a server and a client. The server sends messages to the message queue, and the client receives these messages from the message queue.

## Files

- `server.c`: The server program that creates the message queue, accepts user input, and sends messages to the queue.
- `client.c`: The client program that reads messages from the queue and prints them to the console.

## Server Code (`server.c`)

The server code creates a message queue, takes user input, and sends messages to the message queue.

### Explanation

1. **Header Files**: Includes necessary header files for message queue operations and standard I/O.
2. **Structure Definition**: Defines a structure `my_msg_st` with a message type and text.
3. **Message Queue Creation**: Creates a message queue with `msgget` using a key.
4. **Message Sending**: Takes user input, assigns a message type, and sends the message to the queue.
5. **Termination**: Checks for the termination condition (input "end") to stop the server.

## Client Code (`client.c`)

The client code receives messages from the message queue and prints them to the console.

### Explanation

1. **Header Files**: Includes necessary header files for message queue operations and standard I/O.
2. **Structure Definition**: Defines a structure `my_msg_st` with a message type and text.
3. **Message Queue Access**: Accesses the message queue with `msgget` using a key.
4. **Message Receiving**: Receives messages from the queue using `msgrcv` and prints them.
5. **Termination**: Checks for the termination condition (received "end" message) to stop the client.

## Compilation and Execution

1. **Compile the Server**: `gcc -o server server.c`
2. **Compile the Client**: `gcc -o client client.c`
3. **Run the Server**: `./server`
4. **Run the Client**: `./client`

### Notes

- Ensure the server is running before starting the client.
- The key used in `msgget` (1234) must be the same for both client and server to access the same message queue.
- Proper error handling is implemented for message queue creation and message sending.
- The demonstration terminates when the message "end" is sent by the server and received by the client.

