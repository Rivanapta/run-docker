# Menggunakan versi Go yang tersedia
FROM golang:1.21-alpine

# Set WORKDIR
WORKDIR /myapp

# Periksa versi Go (opsional, hanya untuk debugging versi Go)
RUN go version

# Copy AUTHORS.md
COPY AUTHORS.md .

# Copy go.mod dan go.sum
COPY go.mod go.sum ./

# Install dependencies
RUN go mod download

# Copy kode aplikasi
COPY . .

# Build aplikasi dengan nama "my-go-app"
RUN go build -o my-go-app

# Copy LINKS.md setelah build (tidak mempengaruhi build tetapi penting untuk dokumentasi)
COPY LINKS.md .

# Expose port 80 untuk aplikasi
EXPOSE 80

# Jalankan aplikasi
CMD ["./my-go-app"]
