# 🚀 Go (Golang) Complete Developer Guide

<div align="center">

<img src="https://go.dev/blog/go-brand/Go-Logo/PNG/Go-Logo_Blue.png" width="220"/>

### ⚡ Learn Go From Beginner To Advanced

Fast • Simple • Concurrent • Scalable Backend Development

</div>

---

# 📖 What is Go?

Go (Golang) is an open-source programming language developed by Google.

It is designed for:

✅ High Performance

✅ Concurrency Support

✅ Simplicity

✅ Scalability

✅ Cloud Native Applications

✅ APIs & Microservices

✅ DevOps & Automation

✅ Distributed Systems

---

# ⚙️ Install Go

### Check Version

```bash
go version
```

### Environment

```bash
go env
```

### GOPATH

```bash
go env GOPATH
```

### GOROOT

```bash
go env GOROOT
```

---

# 📦 Create First Project

### Create Folder

```bash
mkdir hello-go
cd hello-go
```

### Initialize Module

```bash
go mod init github.com/username/hello-go
```

### Create File

```bash
touch main.go
```

### Run Program

```bash
go run main.go
```

### Build Binary

```bash
go build
```

### Build Custom Name

```bash
go build -o app
```

### Execute Binary

Linux/macOS

```bash
./app
```

Windows

```bash
app.exe
```

---

# 👋 Hello World

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello Go!")
}
```

Run:

```bash
go run main.go
```

---

# 📦 Go Modules

### Initialize Module

```bash
go mod init project-name
```

### Download Dependencies

```bash
go mod tidy
```

### Download Package

```bash
go get package-name
```

Example:

```bash
go get github.com/gin-gonic/gin
```

### Update Dependency

```bash
go get -u
```

### Verify Modules

```bash
go mod verify
```

### Vendor Dependencies

```bash
go mod vendor
```

---

# 📂 Project Structure

```text
project/
│
├── cmd/
│   └── app/
│
├── internal/
│   ├── handlers/
│   ├── services/
│   ├── repositories/
│   └── middleware/
│
├── pkg/
│
├── configs/
│
├── routes/
│
├── database/
│
├── models/
│
├── utils/
│
├── tests/
│
├── main.go
│
├── go.mod
│
└── go.sum
```

---

# 🔢 Variables

```go
var name string = "Rahat"

age := 25
```

---

# 🧮 Data Types

```go
int
int64
float32
float64
bool
string
byte
rune
```

---

# 🔀 Conditions

### If

```go
if age >= 18 {
	fmt.Println("Adult")
}
```

### If Else

```go
if age >= 18 {
	fmt.Println("Adult")
} else {
	fmt.Println("Minor")
}
```

---

# 🔁 Loops

```go
for i := 0; i < 5; i++ {
	fmt.Println(i)
}
```

---

# 🧠 Functions

```go
func add(a int, b int) int {
	return a + b
}
```

Usage:

```go
result := add(10,20)
```

---

# 📚 Arrays

```go
numbers := [5]int{1,2,3,4,5}
```

---

# 📜 Slices

```go
nums := []int{1,2,3}
```

Append:

```go
nums = append(nums,4)
```

---

# 🗂 Maps

```go
user := map[string]string{
	"name":"Rahat",
	"city":"Dhaka",
}
```

---

# 🏗 Structs

```go
type User struct {
	Name string
	Age  int
}
```

Create:

```go
u := User{
	Name:"Rahat",
	Age:25,
}
```

---

# 🔗 Pointers

```go
x := 10

ptr := &x

fmt.Println(*ptr)
```

---

# ⚡ Goroutines

```go
go myFunction()
```

Example:

```go
func hello() {
	fmt.Println("Hello")
}

go hello()
```

---

# 📡 Channels

Create Channel

```go
ch := make(chan string)
```

Send

```go
ch <- "Hello"
```

Receive

```go
msg := <- ch
```

---

# 🔒 Mutex

```go
var mu sync.Mutex

mu.Lock()

mu.Unlock()
```

---

# 🌐 HTTP Server

```go
package main

import (
	"fmt"
	"net/http"
)

func home(w http.ResponseWriter, r *http.Request){
	fmt.Fprintf(w,"Welcome")
}

func main(){
	http.HandleFunc("/",home)

	http.ListenAndServe(":8080",nil)
}
```

Run:

```bash
go run main.go
```

Open:

```text
http://localhost:8080
```

---

# 🚀 Gin Framework

Install:

```bash
go get github.com/gin-gonic/gin
```

Example:

```go
package main

import "github.com/gin-gonic/gin"

func main(){

	r := gin.Default()

	r.GET("/",func(c *gin.Context){
		c.JSON(200,gin.H{
			"message":"Hello API"
		})
	})

	r.Run(":8080")
}
```

Run:

```bash
go run main.go
```

---

# 🛢 MySQL

Install Driver

```bash
go get github.com/go-sql-driver/mysql
```

Connection

```go
db, err := sql.Open(
	"mysql",
	"user:password@tcp(localhost:3306)/dbname",
)
```

---

# 🐘 PostgreSQL

Install Driver

```bash
go get github.com/lib/pq
```

---

# 🔥 GORM ORM

Install

```bash
go get gorm.io/gorm
```

MySQL Driver

```bash
go get gorm.io/driver/mysql
```

PostgreSQL Driver

```bash
go get gorm.io/driver/postgres
```

---

# 🔐 JWT Authentication

Install

```bash
go get github.com/golang-jwt/jwt/v5
```

---

# 📄 Environment Variables

Install

```bash
go get github.com/joho/godotenv
```

Example

```go
godotenv.Load()

os.Getenv("DB_HOST")
```

---

# 🧪 Testing

Create Test

```go
func TestAdd(t *testing.T){
	if add(2,3)!=5{
		t.Fail()
	}
}
```

Run All Tests

```bash
go test
```

Verbose

```bash
go test -v
```

Coverage

```bash
go test -cover
```

---

# 📊 Benchmark

```bash
go test -bench=.
```

---

# 🧹 Formatting

Format File

```bash
go fmt
```

Format All

```bash
go fmt ./...
```

---

# 🔍 Static Analysis

```bash
go vet ./...
```

---

# 📦 Generate Docs

Install

```bash
go install golang.org/x/tools/cmd/godoc@latest
```

Run

```bash
godoc -http=:6060
```

---

# 🐳 Docker

Build Image

```bash
docker build -t go-app .
```

Run Container

```bash
docker run -p 8080:8080 go-app
```

---

# ☁️ Deployment

### Linux Server

Build

```bash
GOOS=linux GOARCH=amd64 go build
```

### Windows

```bash
GOOS=windows GOARCH=amd64 go build
```

### macOS

```bash
GOOS=darwin GOARCH=amd64 go build
```

---

# 🐙 Git Commands

Initialize

```bash
git init
```

Add Files

```bash
git add .
```

Commit

```bash
git commit -m "Initial Commit"
```

Remote

```bash
git remote add origin REPOSITORY_URL
```

Push

```bash
git push -u origin main
```

---

# 📚 Popular Go Packages

```bash
go get github.com/gin-gonic/gin
go get github.com/gofiber/fiber/v2
go get gorm.io/gorm
go get github.com/golang-jwt/jwt/v5
go get github.com/go-sql-driver/mysql
go get github.com/lib/pq
go get github.com/joho/godotenv
go get github.com/spf13/viper
go get github.com/spf13/cobra
go get github.com/stretchr/testify
go get github.com/google/uuid
go get github.com/go-playground/validator/v10
go get github.com/redis/go-redis/v9
go get github.com/elastic/go-elasticsearch/v8
go get github.com/prometheus/client_golang
```

---

# 🏆 Go Roadmap

## Beginner

- Go Basics
- Variables
- Data Types
- Loops
- Functions
- Arrays
- Slices
- Maps

## Intermediate

- Structs
- Interfaces
- Error Handling
- Packages
- Modules
- File Handling
- JSON

## Advanced

- Concurrency
- Goroutines
- Channels
- Mutex
- Context
- REST API
- Middleware
- Authentication

## Expert

- Gin/Fiber
- GORM
- Microservices
- Docker
- Kubernetes
- Redis
- gRPC
- Message Queues
- System Design
- Cloud Native Architecture

---

# 👨‍💻 Author

**Md. Moklasur Rahman Rahat**

🚀 Full Stack Developer

💻 Backend Engineer

⚡ Golang Enthusiast

GitHub: **codexvisual**

⭐ Star this repository if it helps you learn Go.
