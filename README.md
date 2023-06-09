Задание: необходимо создать Dockerfile, основанный на любом образе (вы в праве выбрать самостоятельно).
В него необходимо поместить приложение, написанное на любом известном вам языке программирования (Python, Java, C, С#, C++).
При запуске контейнера должно запускаться самостоятельно написанное приложение.
```
rust@GB:~/dockfile$ nano Dockerfile

FROM openjdk:8-jdk-alpine
ADD exception_les2.jar /
ENTRYPOINT ["java","-jar","exception_les2.jar"]

rust@GB:~/dockfile$ sudo docker build -t docker-java:1.0 .
[+] Building 0.7s (7/7) FINISHED
 => [internal] load build definition from Dockerfile                                                                                             0.0s
 => => transferring dockerfile: 475B                                                                                                             0.0s
 => [internal] load .dockerignore                                                                                                                0.1s
 => => transferring context: 2B                                                                                                                  0.0s
 => [internal] load metadata for docker.io/library/openjdk:8-jdk-alpine                                                                          0.5s
 => [internal] load build context                                                                                                                0.0s
 => => transferring context: 40B                                                                                                                 0.0s
 => [1/2] FROM docker.io/library/openjdk:8-jdk-alpine@sha256:94792824df2df33402f201713f932b58cb9de94a0cd524164a0f2283343547b3                    0.0s
 => CACHED [2/2] ADD exception_les2.jar /                                                                                                        0.0s
 => exporting to image                                                                                                                           0.0s
 => => exporting layers                                                                                                                          0.0s
 => => writing image sha256:a110a2607c41e3d24e66fe5193c11f4991733c1ece477ff56d8556f46cae4a7b                                                     0.0s
 => => naming to docker.io/library/docker-java:1.0                                                                                               0.0s
rust@GB:~/dockfile$ sudo docker run -t docker-java:1.0
Укажите индекс элемента массива, в который Вы хотите записать единицу(1)
Введите число:
9
rust@GB:~/dockfile$
rust@GB:~/dockfile$ sudo docker ps -a
CONTAINER ID   IMAGE             COMMAND                  CREATED          STATUS                       PORTS     NAMES
f52a5d2b7fb3   docker-java:1.0   "java -jar exception…"   24 seconds ago   Exited (130) 5 seconds ago             friendly_perlman
```

