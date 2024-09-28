在 Ubuntu 上安装 NGINX 非常简单。你可以按照以下步骤操作来安装并启动 NGINX：

### 1. 更新包列表
首先，确保你的系统软件包列表是最新的：

```bash
sudo apt update
```

### 2. 安装 NGINX
使用以下命令安装 NGINX：

```bash
sudo apt install nginx -y
```

### 3. 启动 NGINX
安装完成后，NGINX 会自动启动。如果没有自动启动，你可以手动启动它：

```bash
sudo systemctl start nginx
```

### 4. 检查 NGINX 状态
确认 NGINX 是否成功启动：

```bash
sudo systemctl status nginx
```

输出结果中应该显示 `active (running)` 表示 NGINX 正在运行。

### 5. 允许 HTTP 和 HTTPS 流量
如果你的服务器有防火墙 (比如 `ufw`)，你需要允许 HTTP 和 HTTPS 流量通过：

```bash
sudo ufw allow 'Nginx Full'
```

这将允许 HTTP (端口 80) 和 HTTPS (端口 443) 的流量。

### 6. 测试 NGINX
安装并启动 NGINX 后，打开浏览器，访问服务器的 IP 地址，看看是否可以看到 NGINX 的默认页面。比如：

```bash
http://your-server-ip
```

你应该看到一个默认的 NGINX 欢迎页面。

### 7. 配置 NGINX
NGINX 的配置文件位于 `/etc/nginx/nginx.conf`，你可以根据需要编辑这个文件，或者在 `/etc/nginx/sites-available/` 下为你的站点创建单独的配置文件。

例如，可以使用以下命令编辑默认的配置文件：

```bash
sudo nano /etc/nginx/sites-available/default
```

编辑完成后，记得重新加载 NGINX 来应用配置更改：

```bash
sudo systemctl reload nginx
```

### 设置开机启动
```bash
sudo systemctl enable nginx
```
