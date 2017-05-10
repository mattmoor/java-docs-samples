FROM maven:3.5-jdk-8 AS builder
COPY . /workspace/
WORKDIR /workspace/flexible/helloworld
RUN mvn package

FROM gcr.io/convoy-adapter/bazel:jetty-demo
WORKDIR /jetty
COPY --from=builder /workspace/flexible/helloworld/target/flexible-helloworld-1.0-SNAPSHOT.war /jetty/webapps/helloworld.war
