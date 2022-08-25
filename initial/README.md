➜  initial git:(main) ✗ docker build . --platform=linux/amd64 -t maven-1

```
[+] Building 194.4s (16/16) FINISHED
 => [internal] load build definition from Dockerfile                                                                                0.0s
 => => transferring dockerfile: 1.01kB                                                                                              0.0s
 => [internal] load .dockerignore                                                                                                   0.0s
 => => transferring context: 2B                                                                                                     0.0s
 => [internal] load metadata for docker.io/library/openjdk:8-jdk-alpine                                                             1.7s
 => [internal] load metadata for docker.io/library/alpine:latest                                                                    1.7s
 => [stage-1 1/2] FROM docker.io/library/openjdk:8-jdk-alpine@sha256:94792824df2df33402f201713f932b58cb9de94a0cd524164a0f22833435  12.3s
 => => resolve docker.io/library/openjdk:8-jdk-alpine@sha256:94792824df2df33402f201713f932b58cb9de94a0cd524164a0f2283343547b3       0.0s
 => => sha256:c2274a1a0e2786ee9101b08f76111f9ab8019e368dce1e325d3c284a0ca33397 70.73MB / 70.73MB                                   10.8s
 => => sha256:94792824df2df33402f201713f932b58cb9de94a0cd524164a0f2283343547b3 1.64kB / 1.64kB                                      0.0s
 => => sha256:44b3cea369c947527e266275cee85c71a81f20fc5076f6ebb5a13f19015dce71 947B / 947B                                          0.0s
 => => sha256:a3562aa0b991a80cfe8172847c8be6dbf6e46340b759c2b782f8b8be45342717 3.40kB / 3.40kB                                      0.0s
 => => sha256:e7c96db7181be991f19a9fb6975cdbbd73c65f4a2681348e63a141a2192a5f10 2.76MB / 2.76MB                                      2.3s
 => => sha256:f910a506b6cb1dbec766725d70356f695ae2bf2bea6224dbe8c7c6ad4f3664a2 238B / 238B                                          1.6s
 => => extracting sha256:e7c96db7181be991f19a9fb6975cdbbd73c65f4a2681348e63a141a2192a5f10                                           0.1s
 => => extracting sha256:f910a506b6cb1dbec766725d70356f695ae2bf2bea6224dbe8c7c6ad4f3664a2                                           0.0s
 => => extracting sha256:c2274a1a0e2786ee9101b08f76111f9ab8019e368dce1e325d3c284a0ca33397                                           1.1s
 => [build 1/8] FROM docker.io/library/alpine@sha256:bc41182d7ef5ffc53a40b044e725193bc10142a1243f395ee852a8d9730fc2ad               0.0s
 => [internal] load build context                                                                                                   0.0s
 => => transferring context: 2.15kB                                                                                                 0.0s
 => CACHED [build 2/8] RUN apk --update --no-cache add openjdk7 curl                                                                0.0s
 => CACHED [build 3/8] RUN mkdir -p /usr/share/maven /usr/share/maven/ref  && curl -fsSL -o /tmp/apache-maven.tar.gz https://apach  0.0s
 => CACHED [build 4/8] WORKDIR /data                                                                                                0.0s
 => CACHED [build 5/8] COPY src /data                                                                                               0.0s
 => [build 6/8] COPY pom.xml /data                                                                                                  0.0s
 => [build 7/8] RUN mvn compile                                                                                                    99.7s
 => [build 8/8] RUN mvn package                                                                                                    92.8s
 => [stage-1 2/2] COPY --from=build /data/target/gs-maven-0.1.0.jar target/gs-maven-0.1.0.jar                                       0.0s
 => exporting to image                                                                                                              0.0s
 => => exporting layers                                                                                                             0.0s
 => => writing image sha256:7e14438478779358b07d081cf44e7b720428aace12b1596e4b88a456ac702d00                                        0.0s
 => => naming to docker.io/library/maven-1
 ```
 
 ➜  initial git:(main) ✗ docker push <REPO_NAME>:maven-1
