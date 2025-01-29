Here, this tutorial will show you how to set up Go, specifically in a DevContainer!

**Prerequisites**:

- Make sure VS Code with the Dev Containers extension is installed.

- Install docker and make sure Docker is running.

- Understand the fundamentals of Git and the command-line tools.

---
### 1. **`Create a New Directory and Initialize a New Git Repository`**
Go to your computer's terminal and go to one of your preferred directories. Run the following: 
```shell
mkdir comp423-first-project-go
cd comp423-first-project-go
git init
```
Create a README file and have it link back to this site:
```shell
echo  "# COMP423 Go Hello World" >> README.md
echo  "[Tutorial Link](https://jharrison21.github.io/comp423-course-notes/)" >> README.md
```

Now go ahead and stage and commit your README.
```shell
git add README.md
git commit -m "1st README Commit"
```
---
### 2. **`Establishing GitHub Connection`**
- Once logged in on GitHub, click your profile pic. Click the **Create New** tab, then  click **New Repository**.
- Fill the repository name, description, and visibility options.
- Click **Create Repository**
- Go back to your terminal and add your newly created GitHub Repo as a remote
```shell
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
```
Push your local repo
```shell
git push --set-upstream origin main
```
Now your repo should be completely set up!
---

### 3. **`Configure the DevContainer`**
- Open VS Code and open your preferred directory from earlier. 
- Inside there, go to the comp423-first-project-go directory and make a .devcontainer directory in the root. 
- Now make json file inside  .devcontainer called 'devcontainer.json':
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
    If installed, it should output the version, otherwise, no version number will show.
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
This is one way to both compile and run the program
---

### 9. **`Use "go build" to Both Build and Run the Program`**

Another way to compile and run the program is to run the following:

```shell
go build -o hello-comp423
./hello-comp423
```

Now anytime you type **./hello-comp423** in the terminal, "Hello COMP423" should pop up.