# 基础镜像，选用稳定nginx版本，和你之前yaml保持一致
FROM nginx:1.30.5

# 作者信息（可选，规范写法）
LABEL maintainer="chenshuai <chenshuai@example.com>"

# 删除容器里nginx默认的站点配置
RUN rm -f /etc/nginx/conf.d/default.conf

# 把本地目录下自定义的nginx配置，拷贝到容器内nginx配置目录
# 同目录准备 nginx.conf 或者 site.conf
COPY ./site.conf /etc/nginx/conf.d/

# 拷贝自定义静态网页（index.html，自己写的页面）
COPY ./index.html /usr/share/nginx/html/

# 暴露端口，仅文档声明，不会真正打开端口
EXPOSE 80

# 容器启动命令，官方nginx原有启动命令，不要改动
CMD ["nginx", "-g", "daemon off;"]
