docker container cp Nginx:/etc/nginx/nginx.conf D:\project\ChatGPT\dev-ops/nginx/conf
docker container cp Nginx:/etc/nginx/conf.d D:\project\ChatGPT\dev-ops/nginx/conf/conf.d
docker container cp Nginx:/usr/share/nginx/html/index.html D:\project\ChatGPT\dev-ops/nginx/html

在创建之前要把之前创建的容器删掉docker rm -f nginx

docker run --restart always --name nginx -d -p 80:80 -v D:\project\ChatGPT\dev-ops/nginx/log:/var/log/nginx -v D:\project\ChatGPT\dev-ops/nginx/html:/usr/share/nginx/html -v D:\project\ChatGPT\dev-ops/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v D:\project\ChatGPT\dev-ops/nginx/conf.d:/etc/nginx/conf.d  -d nginx:latest
