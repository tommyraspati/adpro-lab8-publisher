# Message Broker Interaction Details

## How many data your publisher program will send to the message broker in one run?

The provided code snippet does not explicitly include a publisher function; it primarily outlines the setup for a message handler and listener. In systems like this, the number of messages a publisher sends to a message broker in one run typically depends on the implementation specifics of the publisher's part of the system. For instance, the publisher could be configured to send messages continuously, a fixed number of messages, or messages triggered by specific events. Without further details on the publisher's implementation, we cannot specify the exact number of messages sent in one run.

## If the URL "amqp://guest:guest@localhost:5672" is the same in both the publisher and subscriber programs, what does it mean?

The URL "amqp://guest:guest@localhost:5672" being the same in both publisher and subscriber programs indicates:

- **Consistent Access Credentials**: Both the publisher and the subscriber use the same username and password (`guest:guest`), which are the default for accessing the RabbitMQ server. This implies they are accessing the same RabbitMQ server instance.

- **Same Server Location**: The term `localhost` indicates that both the publisher and the subscriber are either running on the same machine as the RabbitMQ server or they are configured to connect to a server running on the local network designated by `localhost`.

- **Standard Communication Port**: The connection through port `5672`, the default port for AMQP communication with RabbitMQ, confirms that they are communicating using the expected protocol.

- **Shared Messaging Environment**: Using the same URL ensures that both the publisher and the subscriber are interacting with the same message broker environment, essential for the messages sent by the publisher to be received by the subscriber correctly.

This setup is typical for development environments, prioritizing simplicity and ease of configuration. In production environments, different credentials and possibly different server setups are common to enhance security and scalability.


![messageImage_1713946427712](https://github.com/tommyraspati/adpro-lab8-publisher/assets/89284213/63979cf9-4e63-41ce-a9e4-7f45a3e3dedc)
When you run a subscriber and then a publisher, you'll see this message in the subscriber terminal. This shows that the publisher successfully sent data to the subscriber through RabbitMQ. The publisher sends data to an exchange. The exchange then routes the message to the appropriate queue based on the binding. The queue temporarily stores the message. The subscriber then waits for messages in the queue and processes them as needed.

