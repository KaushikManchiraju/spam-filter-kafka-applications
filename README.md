# Kafka Aapplications for Chatroom Application - [AI System]

These are two kafka applications which are used for listening for events (messages) in the Chatroom in real time, call the ML/AI API, format data in json and separate the messages as ham or spam in real time using Kafka topics.

## Installation

The following steps can be followed for installing the required packages.

Docker is required and on Windows, Docker Desktop can be used. It is highly recommended to make use of WSL2 on Windows.

The applications in this project requires that the cp-all-in-one docker containers are running


```bash
docker-compose up -d
```

```bash
sudo apt install golang-go
```


## Usage

The incoming messages into the application will first arrive at the Kafka Producer application, called sms-event-integration. Run the following command within the /apps/sms-event-integration-directory to launch the application:


```python
go run app.go
```

The filter stream application is a streaming application that listens for new messages to arrive into the new-sms-json-v1 topic, structures the messages into accepted JSON-format for the model API, sends POST-requests to the model API, and then pushes the messages to one of the following Kafka topics based on the predicted result:

Run the following command within the /apps/sms-filter-stream-directory to launch the application:

```python
go run app.go
```



## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
