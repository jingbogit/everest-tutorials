## Docker

### Terminology

- **Dockerfile** Text file that contains instructions for how to build a Docker image.

- **Image** Package with all of the dependencies and information needed to create a container.

- **Container** Instance of a Docker image, with states: e.g. `created`, `restarting`, `running`, `exited`, etc

- **Docker Engine** Client-server application: daemon + REST API + docker CLI

- **Compose File** YAML file for defining multi-container applications

---

##### ENTRYPOINT vs CMD
- ENTRYPOINT is the fixed part of the command
- CMD is the variable part (usually the parameters)

##### EXEC vs SHELL form of ENTRYPOINT / CMD
- EXEC: JSON arrays, no variable substitution, command PID is 1, get unix signals directly (recommended)
- SHELL: `/bin/sh -c `

---

##### Multi-stage build
- Suited for compiled languages
- Minifying / transpiling dynamic languages in build stage
```
FROM golang:1.10 as builder
RUN go build src/*.go

FROM alpine:3.7
COPY --from=builder /go/src/app/main .
CMD ["./main"]
```

---

##### Mount sources
- Bind mounted sources when running the container
- Suited for dynamic languages
- No need to rebuild or restart container when sources are updated
```
docker run -v ${pwd}/src:/src
```
