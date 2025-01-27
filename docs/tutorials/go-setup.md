**First off, I want to go through a few of the markdown extensions:**

### 1. **`pymdownx.highlight`**
**Explanation**:
- The pymdownx.highlight option provides syntax highlighting.

---

### 2. **`pymdownx.inlinehilite`**
**Explanation**:
This extension allows you to highlight parts of inline text by using backticks around the part you want to highlight.

**Example Usage**:
You can check your Go version by running `go version`.


---

### 3. **`admonition`**
**Explanation**:
This extension adds styled call-out boxes for notes, warnings, and examples, making them stand out in the text.

**Example Usage**:
!!! note "Go Installation"
    Make sure that you have a recent version of Go installed.

!!! warning "Docker Is Not Running"
    Docker has to be running in order to use DevContainers.
---

**Prerequisites**:

- Make sure VS Code with the Dev Containers extension is installed.

- Make sure Docker is running.

- Understand the fundamentals of Git and the command-line tools

---
### 1. **`Initialize a new DevContainer`**
Run the following in the terminal: 

mkdir .devcontainer
cd .devcontainer
git init


---

### 2. **`Configure the DevContainer`**
Inside the .devcontainer directory, you want to make a json file inside called 'devcontainer.json':

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

---
### 3. **`Open Project in DevContainer`**
While in VS Code, open the command palette and make sure to search and find "Reopen in Container". When you find it click it.
---

### 4. **`Double check if Go is installed`**
Run the following in the terminal: 

go version

It should output the version if installed, if not there nothing will be found.

### 5. **`Create a New Go Project`**

Run the following in the terminal: 

go mod init hello-comp423

This should create a new Go module.

### 6. **`Make a "Hello COMP423" Program`**

Run the following in the terminal: 

touch main.go

That should create the file and from there input the following program:

package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}


### 7. **`Make a "Hello COMP423" Program`**
Now run the program in the terminal:

go run main.go

This should both compile and run the program

### 8. **`Use "go build" to Both Build and Run the Program`**

Run the following:
go build -o hello-comp423
./hello-comp423

Now anytime you type "./hello-comp423", "Hello COMP423" should pop up.