# Setting up a dev container for Go

* Primary author: [Abhiraam Aremanda](https://github.com/AbhiraamA)
* Reviewer: [Tanveer Thethi](https://github.com/TanveerT12345)

## Prerequisites 🛠️
Before starting, ensure you have the following installed:

* 🐳 [Docker](https://docs.docker.com/engine/install/) for your specific operating system
* 🖥️ [Visual Studio Code](https://code.visualstudio.com/) with the **Dev Containers** extension
* 📂 [Git](https://git-scm.com/downloads) and have a GitHub account


!!! note

    For more information about installing Docker, refer to the [Docker Documentation](https://docs.docker.com/get-docker/).

---
## Step 1: Initialize a Git Repository 🔧

### 1. Start by creating a directory for your project and initializing a Git repository:

| Command                | Description                                          |
|------------------------|------------------------------------------------------|
| `mkdir go-setup`       | Creates a directory named `go-setup`.               |
| `cd go-setup`          | Navigates to the new directory.                     |
| `git init`             | Initializes a Git repository in the current folder. |

Run the following commands in your terminal:
``` bsh title="bsh"
mkdir go-setup
cd go-setup
git init
```

Create a README.md file with a description of your project:
``` bsh title="bsh"
echo "# Go Setup Project" > README.md
git add README.md
git commit -m "Initial commit with README"
```
### 2. Create a Remote Repository on GitHub
1. Log in to your GitHub account and navigate to the Create a New Repository page.

2. Fill in the details as follows:
    * Repository Name: go-setup
    * Description: "A simple Go project to demonstrate Go setup and Dev Containers."
    * Visiblity: Public

3. Leave the options to initialize with a README, .gitignore, or license unchecked.

4. Click Create Repository.

### 3. Link Your Local Repository to GitHub
1. Add the GitHub repository as a remote:
    ``` bsh title="bsh"
    git remote add origin https://github.com/<your-username>/go-setup.git
    ```
    Replace <your-username> with your GitHub username.

2. Rename your branch to main (if not already named main):
    ``` bsh title="bsh"
    git branch -M main
    ```
3. Push your local repository to GitHub:
    ``` bsh title="bsh"
    git push --set-upstream origin main
    ```
4. Verify your repository on GitHub to confirm your local changes have been pushed.


## Step 2: Configure the Dev Container 📦

1. Create a .devcontainer directory:
    ``` bsh title="bsh"
    mkdir .devcontainer
    ```

2. Create a devcontainer.json file in the .devcontainer folder:
    ``` bsh title="bsh"
    touch .devcontainer/devcontainer.json
    ```

3. Add the following devcontainer.json file to the .devcontainer folder:
    ``` json title="json"

    {
        "name": "Go Dev Container",
        "image": "mcr.microsoft.com/devcontainers/go:latest",
        "customizations": {
            "vscode": {
                "extensions": ["golang.go"]
            }
        }
    }
    ```

!!! info
    The golang.go VSCode extension is officially maintained by the Go team. It provides helpful tools like syntax highlighting, debugging, and IntelliSense.

## Step 3: Verify Go Installation 🐹
Once the Dev Container is up and running, check the installed Go version:

Run in your terminal:
``` bsh title="bsh"
go version
```

You should see output similar to:
``` bsh title="bsh"
go version go1.20.0 linux/amd64
```

## Step 4: Create the Hello 423 Program ✨
Now its time to create your first Go program
!!! info
    The go mod command helps initialize, update, and manage the go.mod file for your project. The go.mod file contains metadata about the module, including:

    The module's name (its import path).
    
    The minimum required dependencies and their versions.

1. Initialize the Go Module:
``` bsh title="bsh"
go mod init example.com/hello
```
2. Create the main.go file:
``` bsh title="bsh"
touch main.go
```

    This will create an empty file named main.go in the current directory.

4. Add the Code into the main.go file:
``` go title="go"
package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}
```

## Step 5: Compile and Run the Program 🚀

You can now run or build the program.

| Command           | Description                                                     |
|-------------------|-----------------------------------------------------------------|
| `go run main.go`  | Compiles and runs the code directly in one step.                |
| `go build	`       | Builds a binary file of the program (e.g., hello) for later use.|

1. Run the program directly:
``` bsh title="bsh"
go run main.go
```
    Output:

        Hello COMP423

2. Build and execute the binary:
``` bsh title="bsh"
go build
./hello
```

!!!tip
     Use go build to create a standalone binary for production environments. go run is mainly used during development.

## Step 6: Verify and Push 📝

1. Verify the program runs correctly.

2. Push your repository to GitHub:
``` bsh title="bsh"
git add .
git commit -m "Initial Go setup"
git push origin main
```

## Links to Additional Resources 🔗
* [Go Documentation](https://go.dev/doc/)
* [MkDocs Documentation](https://www.mkdocs.org/)


NOTE: I hope you enjoyed this Go demo! Thank you for visiting this website! 