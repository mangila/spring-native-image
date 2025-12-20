FROM ghcr.io/graalvm/native-image-community:21-muslib

WORKDIR /build

COPY . .

RUN ./mvnw -Pnative native:compile

FROM alpine:latest

COPY --from=0 /build/target/native-image /app

ENTRYPOINT ["/app"]