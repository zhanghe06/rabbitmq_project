## RabbitMQ

[http://www.rabbitmq.com/](http://www.rabbitmq.com/)

[RabbitMQ Tutorials](http://www.rabbitmq.com/getstarted.html)


## Download

[http://www.rabbitmq.com/download.html](http://www.rabbitmq.com/download.html)


## Install

rabbitmq-plugins, rabbitmq-server, rabbitmqctl


### install rabbitmq plugins

```
sudo rabbitmq-plugins enable rabbitmq_management
```

```
sudo netstat | grep 15672
```

[http://127.0.0.1:15672/](http://127.0.0.1:15672/)

- username: guest
- password: guest


## Command

Start Server
```
sudo rabbitmq-server start  # front-end
or
sudo rabbitmq-server -detached  # back-end
```

Server Status
```
sudo rabbitmqctl status
```

Queue Info
```
sudo rabbitmqctl list_queues
```

Exchange Info
```
sudo rabbitmqctl list_exchanges
```

Binding Info
```
sudo rabbitmqctl list_bindings
```

Connection Info
```
sudo rabbitmqctl list_connections
```

Channel Info
```
sudo rabbitmqctl list_channels
```


## Python Client

[http://www.rabbitmq.com/devtools.html#devops-tools](http://www.rabbitmq.com/devtools.html#devops-tools)

[Pika Python AMQP Client Library](https://pypi.python.org/pypi/pika)

[Pika’s Doc](https://pika.readthedocs.org)


## Run

```
$ python send.py  
[x] Sent 'Hello World!' 
```

```
$ python receive.py  
[*] Waiting for messages. To exit press CTRL+C  
[x] Received 'Hello World!' 
```