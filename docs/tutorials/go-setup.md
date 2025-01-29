Here, this tutorial will show you how to set up Go, specifically in a DevContainer!

**Prerequisites**:

- Make sure VS Code with the Dev Containers extension is installed.

- Install docker and make sure Docker is running.

- Understand the fundamentals of Git and the command-line tools.

---
### 1. **`Create a New Directory and Initialize a new Git Repository`**
Run the following in your computer's terminal: 
```shell
mkdir .devcontainer
cd .devcontainer
git init

- Create a README file:
```shell
echo  "# COMP423 Go Hello World" >> README.md
echo  "[Tutorial Link](https://.github.io/comp423-course-notes/docs/tutorials/go-setup/)" >> README.md
```
---

### 2. **`Configure the DevContainer`**
Inside the .devcontainer directory, you want to make a json file inside called 'devcontainer.json':
```json
{
    "name": "COMP423 Course Notes",
    "image": "mcr.microsoft.com/devcontainers/go:latest",
    "customizations": {
      "vscode": {
        "settings": {},
        "extensions": [
          
          "golang.go"           // Go language extension
        ]
      }
    },
    "postCreateCommand": "go version"
  }
```

---
### 4. **`Open Project in DevContainer`**
While in VS Code, open the command palette (Command + Shift + P for Mac or Ctrl + Shift + P for Windows/Linux) and make sure to search and find "Reopen in Container". When you find it click it.

---

### 5. **`Double Check if Go is Installed`**
Run the following in the terminal: 

```shell
go version
```


!!! note "Go Installation"
    It should output the version if installed, if not there nothing will be found.
---

### 6. **`Create a New Go Project`**

Run the following in the terminal: 

```shell
go mod init hello-comp423
```
This should create a new Go module.
---

### 7. **`Make a "Hello COMP423" Program`**

Run the following in the terminal: 

```shell
touch main.go
```

That should create the file and from there input the following program in the file:
```go
package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}
```
---

### 8. **`Run the Program Using "go run"`**
Now run the program in the terminal:

```shell
go run main.go
```
This should both compile and run the program
---

### 9. **`Use "go build" to Both Build and Run the Program`**

Run the following:

```shell
go build -o hello-comp423
./hello-comp423
```

Now anytime you type **./hello-comp423** in the terminal, "Hello COMP423" should pop up.