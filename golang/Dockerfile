FROM golang:latest AS builder
WORKDIR /project
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN go build -o build/fizzbuzz

FROM scratch
WORKDIR /project
COPY --from=builder /project/templates template
COPY --from=builder /project/build/fizzbuzz fizzbuzz
CMD ["./fizzbuzz", "serve"]
