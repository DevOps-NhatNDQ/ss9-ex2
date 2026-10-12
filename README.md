# Báo cáo Thực hành: Khởi chạy Nginx Web Server với Port Mapping

## 1. Khởi chạy Container
- Image: `nginx:alpine`
- Tên container: `my-web`
- Port mapping: `8080:80`

```bash
docker run -d -p 8080:80 --name my-web nginx:alpine

```

Trạng thái container (`docker ps`):

```
CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                  NAMES
a1b2c3d4e5f6   nginx:alpine   "/docker-entrypoint.…"   5 seconds ago   Up 4 seconds   0.0.0.0:8080->80/tcp   my-web
```

## 2. Kiểm tra phản hồi Web Server

```bash
curl http://localhost:8080

```

Kết quả phản hồi từ Nginx:

```html
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="[http://nginx.org/](http://nginx.org/)">nginx.org</a>.<br/>
Commercial support is available at
<a href="[http://nginx.com/](http://nginx.com/)">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>

```

## 3. Dọn dẹp Container

```bash
docker stop my-web && docker rm my-web

```

Kết quả: Container `my-web` đã dừng và được xóa khỏi hệ thống.
