FROM alpine

#作者
MAINTAINER zhubinwell

#这个环境变量用来表名该镜像模板的最后更新时间
ENV REFRESHED_AT 2019-07-30

#更新apk
RUN apk update && apk upgrade

#安装nodejs，我当时是10.16.0
RUN apk add nodejs

#安装npm，如果不需要可以屏蔽
RUN apk add npm

#安装pm2，如果不需要可以屏蔽
RUN npm i pm2 -g

