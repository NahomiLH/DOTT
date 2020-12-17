FROM golang:1.10-alpine

ENV GOPATH=/go:/app
RUN apk add --update git

WORKDIR /app

COPY Goopfile Goopfile
RUN go get github.com/Pepegasca/goop \
    && goop install

COPY . .
CMD ["ash", "-c", "goop go run api.go convert.go"]
# docker build -t gom . (-t = tagging like gom)
# docker run -ti -p 8000:8000 gom (-p, Publish a container's port(s) to the host, -ti when you run processes in interactive mode, such as when starting a bash shell)
