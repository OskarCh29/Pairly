FROM oskarch29/pairly-java-builder:25 AS builder

WORKDIR /workspace

COPY . .

RUN ./gradlew bootJar --no-daemon

FROM oskarch29/pairly-java-runtime:25

COPY --from=builder /workspace/build/libs/*.jar app.jar

ENTRYPOINT ["java", "-jar", "app.jar"]