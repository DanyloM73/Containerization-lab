FROM golang:latest
WORKDIR /project
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN go build -o build/fizzbuzz
CMD ["./build/fizzbuzz", "serve"]