# Golang Api
## Creating Hello world api from mux package using golang
### Prerequisites
> - Go installed on your system
> - A code editor -> VScode
### Project setup
```linux
mkdir mux-api-project
cd mux-api-project
```
### create a file
```linux
touch main.go
```
### Managing dependencies
```linux
go mod init github.com/<your-github-username>/mux-api-project
```
### install mux
```linux
go get github.com/gorilla/mux
```
### Importing functions
```go
package main

import (
    "fmt"
    "log"
    "net/http"

    "github.com/gorilla/mux"
)
```
### Main logic
```go
func main() {
    r := mux.NewRouter()

    r.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        w.Write([]byte("Hello World!"))
    })
    fmt.Println("Server is starting at port 8080")
    log.Fatal(http.ListenAndServe(":8080", r))
}
```
### Execution
```linux
go run main.go
```
### You will get promoted with a message in the terminal. Something like this
> open a web browser and navigate to http://localhost:8080
### output will be 
