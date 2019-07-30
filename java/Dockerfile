# using alpine-glibc instead of alpine  is mainly because JDK relies on glibc
FROM docker.io/jeanblanchard/alpine-glibc

#作者
MAINTAINER zhubinwell

#将jre打包
ADD jre8.tar.gz /usr/java/jdk/

#设置java环境变量
ENV JAVA_HOME /usr/java/jdk
ENV PATH $JAVA_HOME/bin:$PATH

#这个环境变量用来表名该镜像模板的最后更新时间
ENV REFRESHED_AT 2019-07-30

#切换镜像目录，进入/usr目录
WORKDIR /usr

#在/usr/下创建tomcat目录，用来存放tomcat
RUN mkdir tomcat

#将宿主机的tomcat目录下的文件拷至镜像的/usr/tomcat目录下
ADD tomcat9 /usr/tomcat/

#设置tomcat环境变量
ENV CATALINA_HOME /usr/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH

#公开端口
EXPOSE 8080

#增加可执行权限
RUN chmod a+x /usr/tomcat/bin/*.sh

#设置启动命令，此处不启动tomcat，加入工程后再启动
#CMD ["/usr/tomcat/bin/catalina.sh","run"]

