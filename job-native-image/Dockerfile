FROM ghcr.io/graalvm/native-image-community:21-muslib AS builder

WORKDIR /build

COPY . .

RUN ./mvnw -Pnative native:compile

FROM scratch AS runner

COPY --from=0 /build/target/job-native-image /app

ENTRYPOINT ["/app"]