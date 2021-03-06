# xrlj-eureka-server

https://spring.io/guides/gs/spring-boot-docker/

## 生成Docker镜像并push到私服

1.给可执行文件赋权

    chmod +x docker-image-push.sh
    
2.运行该文件

    ./docker-image-push.sh    

## 执行

### dev

    docker run --restart=always --name eureka-server -e "SPRING_PROFILES_ACTIVE=dev" -e "EUREKA_INSTANCE_IP-ADDRESS=192.168.0.3" -p 1111:1111 -v /apps/eureka-server/tmp:/tmp -v /apps/eureka-server/logs:/logs -d 192.168.0.3:8082/xrlj/eureka-server:0.0.1
   

### test

    $ docker run -e "SPRING_PROFILES_ACTIVE=prod" -p 8080:8080 -t springio/gs-spring-boot-docker
    
    ----------------------
    
    docker run --restart=always --name eureka-server-test -e "SPRING_PROFILES_ACTIVE=test" -p 1111:1111 -d ip:8082/xrlj/eureka-server:0.0.1
    
    ------------------------------------
    
    docker run --restart=always --name eureka-server-test -e "SPRING_PROFILES_ACTIVE=test" -e "EUREKA_INSTANCE_IP-ADDRESS=ip" -p 1111:1111 -v /apps/eureka-server/tmp:/tmp -v /apps/eureka-server/logs:/logs -d ip:8082/xrlj/eureka-server:0.0.1