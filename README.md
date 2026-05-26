# Go<div align="center">

# 🐹 Ultimate Go Cheat Sheet

**Syntax · Concurrency · Types · Interfaces · Testing**  
_Go essentials for backend & system programming_

[![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)](https://go.dev/doc/)
[![Version](https://img.shields.io/badge/1.22+-blue?style=for-the-badge)](https://go.dev/dl/)

</div>

---

## 🧱 1. Basic Syntax & Variables

<div align="center">

| Code | Description |
|------|-------------|
| `package main` | প্যাকেজ ডিক্লেয়ার |
| `import "fmt"` | প্যাকেজ ইম্পোর্ট |
| `func main() { ... }` | এন্ট্রি পয়েন্ট |
| `var name string = "Rahim"` | এক্সপ্লিসিট টাইপ |
| `var age = 25` | টাইপ ইনফারেন্স |
| `city := "Dhaka"` | শর্ট ডিক্লেয়ারেশন (শুধু ফাংশনের ভেতর) |
| `const PI = 3.1416` | কনস্ট্যান্ট |
| `x, y := 10, 20` | মাল্টিপল ভেরিয়েবল |
| `_ = "ignore"` | ব্ল্যাঙ্ক আইডেন্টিফায়ার |

</div>

---

## 📊 2. Data Types

<div align="center">

| Type | Example |
|------|---------|
| `bool` | `true`, `false` |
| `string` | `"Hello"` |
| `int`, `int8`, `int16`, `int32`, `int64` | বিভিন্ন সাইজের ইন্টিজার |
| `uint` | আনসাইন্ড ইন্টিজার |
| `float32`, `float64` | ফ্লোট |
| `byte` (uint8), `rune` (int32) | অক্ষর |
| `nil` | নাল ভ্যালু (pointer, slice, map, channel, func, interface) |

</div>

---

## 🔀 3. Control Flow

<div align="center">

| Code | Description |
|------|-------------|
| `if x > 0 { ... } else { ... }` | কন্ডিশন |
| `if age := 20; age > 18 { ... }` | স্টেটমেন্ট সহ if |
| `switch day { case "Mon": ... default: ... }` | সুইচ (fallthrough দরকার নেই) |
| `for i := 0; i < 5; i++ { ... }` | ক্লাসিক ফর লুপ |
| `for x < 10 { ... }` | while-এর মতো |
| `for { ... }` | ইনফিনিট লুপ |
| `for index, value := range slice { ... }` | রেঞ্জ (slice/map/string) |

</div>

---

## 🛠️ 4. Functions

<div align="center">

| Code | Description |
|------|-------------|
| `func greet(name string) string { return "Hi " + name }` | সাধারণ ফাংশন |
| `func divide(a, b float64) (float64, error) { ... }` | মাল্টিপল রিটার্ন |
| `func swap(a, b string) (string, string) { return b, a }` | একাধিক ভ্যালু রিটার্ন |
| `func add(a, b int) (result int) { result = a + b; return }` | নেকেড রিটার্ন |
| `defer file.Close()` | ফাংশন শেষে এক্সিকিউট |

</div>

---

## 📚 5. Arrays, Slices, Maps

<div align="center">

| Code | Description |
|------|-------------|
| `var arr [5]int` | অ্যারে (fixed size) |
| `arr := [...]int{1,2,3}` | অ্যারে ইনিশিয়ালাইজ |
| `slice := []int{1,2,3}` | স্লাইস (dynamic) |
| `slice = append(slice, 4)` | স্লাইসে যোগ |
| `len(slice)`, `cap(slice)` | দৈর্ঘ্য, ক্যাপাসিটি |
| `s := make([]int, 3, 5)` | মেক দিয়ে স্লাইস |
| `m := map[string]int{"a":1, "b":2}` | ম্যাপ |
| `m["c"] = 3` | যোগ/আপডেট |
| `delete(m, "a")` | ডিলিট |
| `val, ok := m["x"]` | চেক (ok=true/false) |

</div>

---

## 🏗️ 6. Structs, Methods, Interfaces

<div align="center">

| Code | Description |
|------|-------------|
| `type Person struct { Name string; Age int }` | স্ট্রাক্ট ডিফাইন |
| `p := Person{Name: "Rahim", Age: 25}` | ইনস্ট্যান্স তৈরি |
| `func (p Person) Greet() string { ... }` | মেথড (value receiver) |
| `func (p *Person) SetAge(a int) { ... }` | মেথড (pointer receiver) |
| `type Animal interface { Speak() string }` | ইন্টারফেস |
| `func talk(a Animal) { fmt.Println(a.Speak()) }` | ইন্টারফেস প্যারামিটার |

</div>

---

## ⚡ 7. Concurrency (Goroutines & Channels)

<div align="center">

| Code | Description |
|------|-------------|
| `go myFunc()` | গোরুটিন (লাইটওয়েট থ্রেড) |
| `ch := make(chan int)` | আনবাফার্ড চ্যানেল |
| `ch := make(chan string, 2)` | বাফার্ড চ্যানেল |
| `ch <- 42` | চ্যানেলে পাঠানো |
| `val := <-ch` | চ্যানেল থেকে গ্রহণ |
| `close(ch)` | চ্যানেল বন্ধ |
| `for msg := range ch { ... }` | চ্যানেল রেঞ্জ |
| `select { case msg := <-ch1: ... case ch2 <- "hi": ... default: ... }` | সিলেক্ট স্টেটমেন্ট |
| `sync.WaitGroup` | গোরুটিন ওয়েট |
| `sync.Mutex` | মিউটেক্স |

</div>

---

## ⚠️ 8. Error Handling

<div align="center">

| Code | Description |
|------|-------------|
| `if err != nil { return err }` | সাধারণ এরর চেক |
| `errors.New("something wrong")` | নতুন এরর |
| `fmt.Errorf("error: %w", err)` | এরর র‍্যাপিং |
| `defer func() { if r := recover(); r != nil { ... } }()` | প্যানিক রিকভার |

</div>

---

## 📦 9. Packages & Modules

<div align="center">

| Command | Description |
|---------|-------------|
| `go mod init module-name` | নতুন মডিউল শুরু |
| `go get package` | প্যাকেজ ডাউনলোড |
| `go mod tidy` | ডিপেন্ডেন্সি ক্লিন |
| `go build` | বিল্ড |
| `go run main.go` | রান |
| `go test` | টেস্ট |
| `go fmt` | ফরম্যাট |

</div>

---

<div align="center">

### 🐹 Go fast, go safe — keep this handy!  
**Happy Go Coding!**

[![Profile Views](https://komarev.com/ghpvc/?username=your-username&color=00ADD8&style=flat-square)](https://github.com/your-username)

</div>
