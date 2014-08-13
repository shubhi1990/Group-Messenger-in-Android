Group-Messenger-in-Android
==========================

Project includes implementation of total and causal ordering using B-multicast among 5 emulators with JAVA ME


The requirements includes:

Creating a content provider for storing all the messages and abstract in key-value table.

Provider implements insert and query.

App multicast every user-entered message to all app instances (including the one that is sending the message). In the rest of the description, “multicast” always means sending a message to all app instances.

App uses B-multicast.

An algorithm is implemented that provides a total-causal ordering.

The ports & sockets are given:
  App opens one server socket that listens on 10000.
  
  5 AVDs are required for communication. The redirection ports are 11108, 11112, 11116, 11120, and 11124.
  
  5 ports are hard coded and used to set up connections.

Every message is stored in provider individually by all app instances. Each message is stored as a <key, value> pair. The key is the final delivery sequence number for the message (as a string); the value is the actual message (again, as a string). The delivery sequence number starts from 0 and increase by 1 for each message.

