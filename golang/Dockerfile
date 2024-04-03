FROM golang:latest AS builder
WORKDIR /project
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o build/fizzbuzz .

FROM scratch
COPY --from=builder /project/build/fizzbuzz /fizzbuzz
CMD ["/fizzbuzz", "serve"]
