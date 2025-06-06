# 智能家居监控系统

这是一个基于Python的智能家居监控系统，包含本地GUI界面和Web界面，支持通过内网访问控制。

## 功能特点

- 实时显示温度、湿度和光线数据
- 支持灯光控制（开关、自动模式）
- 支持窗帘控制（开关、极限设置）
- 支持空调控制
- 提供本地GUI界面和Web界面
- 支持内网访问控制

## 系统要求

- Python 3.7+
- Windows/Linux/MacOS
- 串口设备（Arduino等）

## 安装步骤

1. 克隆或下载本项目到本地

2. 安装依赖包：
```bash
pip install -r requirements.txt
```

3. 修改配置：
   - 在 `sensor_control.py` 中修改 `SERIAL_PORT` 为你的串口设备
   - 根据需要调整其他阈值参数

## 运行系统

1. 启动Flask服务器（Web界面）：
```bash
python app.py
```

2. 启动本地GUI界面：
```bash
python sensor_control.py
```

3. 访问Web界面：
   - 本地访问：http://localhost:5000
   - 内网访问：http://<本机IP>:5000

## 内网穿透设置

要实现外网访问，可以使用以下工具之一：

1. ngrok
```bash
ngrok http 5000
```

2. frp
```bash
frpc -c frpc.ini
```

3. 花生壳
- 下载并安装花生壳客户端
- 添加内网映射，将本地5000端口映射到外网

## 使用说明

### 本地GUI界面
- 显示实时传感器数据
- 提供所有控制按钮
- 支持窗帘极限设置

### Web界面
- 实时显示传感器数据
- 提供所有控制功能
- 响应式设计，支持移动设备访问

## 注意事项

1. 确保串口设备正确连接
2. 检查串口权限设置
3. 内网穿透时注意网络安全
4. 建议在内网环境中使用

## 故障排除

1. 串口连接失败
   - 检查串口设备是否正确连接
   - 确认串口号是否正确
   - 检查串口权限

2. Web界面无法访问
   - 确认Flask服务器是否运行
   - 检查防火墙设置
   - 验证端口是否被占用

3. 数据不同步
   - 检查网络连接
   - 重启应用程序
   - 检查串口通信是否正常 