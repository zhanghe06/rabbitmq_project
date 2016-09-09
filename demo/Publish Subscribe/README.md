## 分发到多Consumer（Publish/Subscribe）

### 开启两个消费进程

Consumer Console1 (输出到文件):
```
python receive_logs.py > logs_from_rabbit.log
```

Consumer Console2 (打印到屏幕):
```
python receive_logs.py
```

### 开启生产进程

Producer Console:
```
python emit_log.py
```

### 查看创建的 Queue
```
sudo rabbitmqctl list_bindings
```