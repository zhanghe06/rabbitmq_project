## Routing 消息路由

### 开启两个消费进程

Consumer Console1 (warning error 等级的日志输出到文件):
```
python receive_logs_direct.py warning error > logs_from_rabbit.log
```

Consumer Console2 (全部等级的日志打印到屏幕):
```
python receive_logs_direct.py info warning error
```

### 开启生产进程

Producer Console:
```
python emit_log_direct.py
```
