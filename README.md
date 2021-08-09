# simple-nsq-go
A simple NSQ implementation using Go for learning purposes.

## Background Information:
NSQ is an open source, distributed, real time messaging platform used by services to communicate with each other. When a client/server receives a message it runs a specified handler that handles the received/sent message.

Core components include:

	• Nsqd -> daemon (a thing that runs in the bg) that receives, queues, delivers messages to clients.

	• Nsqlookupd -> daemon used to manage topology info. Used to discover nsqd producers for specific topics.
	
	• Nsqadmin -> Web UI to view cluster stats in real time and perform admin tasks.

Nsqd instances can handle multiple streams of data at one time. The NSQ system follows a Pub-sub pattern, of which channels subscribe to a topic, and topics are created upon publish. The "producers" are the ones that are responsible for creating topics and publishing messages, and the "consumers" are the ones who create channels that subscribe to a topic and uses those messages for their own respective purposes.

## Running:
--- OPTIONAL ---
1. go mod init name/...

2. go mod tidy

--- MUST ---

3. go mod tidy

4. docker-compose up -d (sets up the necessary nsq binaries).

5. go build producer.go

6. go build consumer.go

7. Run ./consumer once.

8. Run ./producer multiple times, or create a for loop.

## Stopping:

1. docker-compose stop

2. Ctrl+C all terminal/cmd prompt instances.

## Misc:
View logs: docker-compose logs

View docker status and mapped ports: docker-compose ps

