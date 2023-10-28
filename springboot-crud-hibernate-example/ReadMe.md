```sh
mvn clean package -DskipTests
clear && rm *.log & mvn spring-boot:run
# mvn spring-boot:build-image
```
https://stackoverflow.com/a/71102144/2795764
https://docs.docker.com/cloud/aci-integration/

```sh
docker build -t springboot-crud-h2:1.1 .
docker build --platform -t springboot-crud-h2:1.1 .

# Build for ARM64 
docker build --platform=linux/arm64 -t springboot-crud-h2:1.1-arm64 .

# Build for AMD64
docker build --platform=linux/amd64 -t springboot-crud-h2:1.1-amd64 .


--platform
docker run -p 8080:8080 springboot-crud-h2:1.0
docker run -p 80:80 springboot-crud-h2:1.1-arm64

docker run -p 80:80 springboot-crud-h2:1.1
```
```sh
docker tag springboot-crud-h2:1.1 sagarmhatre/springboot-crud-h2:1.1
docker push sagarmhatre/springboot-crud-h2:1.1

docker tag springboot-crud-h2:1.1-amd64 sagarmhatre/springboot-crud-h2:1.1-amd64
docker push sagarmhatre/springboot-crud-h2:1.1-amd64

docker login azure
docker context create aci sagaracicontext

# docker --context sagaracicontext run -p 80:8080 springboot-crud-h2:1.0

docker --context sagaracicontext run -p 80:80 sagarmhatre/springboot-crud-h2:1.1-amd64
```
