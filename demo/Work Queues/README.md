## 模拟计算密集型任务的处理（Round-robin dispatching 循环分发）

### 开启两个消费进程

Consumer Console1:
```
python worker.py
```

Consumer Console2:
```
python worker.py
```

### 开启生产进程

Producer Console:
```
python new_task.py First    message.
python new_task.py Second   message..
python new_task.py Third    message...
python new_task.py Fourth   message....
python new_task.py Fifth    message.....
```


## Message acknowledgment 消息确认
（解决 Consumer 异常退出导致数据丢失）

为了防止 Consumer 处理接收到的数据过程中异常退出导致的数据丢失，引入了消息确认机制。
默认情况下，消息确认是打开的（enabled）

如果代码中加入 no_ack = True 则会关闭消息确认

查看未确认的消息（调试 RabbitMQ 占用越来越多的内存）
```
sudo rabbitmqctl list_queues name messages_ready messages_unacknowledged
```


## Message durability 消息持久化
（解决 RabbitMQ Server 异常退出导致数据丢失）

queue 的持久化需要在声明时指定 durable=True：
```
channel.queue_declare(queue='task_queue', durable=True)  
```

需要持久化 Message，即在 Publish 的时候指定一个 properties：
```
channel.basic_publish(exchange='',
                      routing_key="task_queue",
                      body=message,
                      properties=pika.BasicProperties(
                         delivery_mode = 2, # make message persistent
                      ))
```
