# Setting up a dev container for Go

* Primary author: [Abhiraam Aremanda](https://github.com/AbhiraamA)
* Reviewer: [Tanveer Thethi](https://github.com/TanveerT12345)

## Prerequisites 🛠️
Before starting, ensure you have the following installed:

* 🐳 Docker
* 🖥️ [Visual Studio Code](https://code.visualstudio.com/) with the **Dev Containers** extension
* 📂 Git

NOTE:
    For more information about installing Docker, refer to the [Docker Documentation](https://docs.docker.com/get-docker/).

---
## Step 1: Initialize a Git Repository 🔧
Start by creating a directory for your project and initializing a Git repository:

| Command                | Description                                          |
|------------------------|------------------------------------------------------|
| `mkdir go-setup`       | Creates a directory named `go-setup`.               |
| `cd go-setup`          | Navigates to the new directory.                     |
| `git init`             | Initializes a Git repository in the current folder. |

Run the following commands in your terminal:

    mkdir go-setup
    cd go-setup
    git init

## Step 2: Configure the Dev Container 📦

1. Create a Create a .devcontainer directory:

        mkdir .devcontainer

2. Add the following devcontainer.json file to the .devcontainer folder:

        {
            "name": "Go Dev Container",
            "image": "mcr.microsoft.com/devcontainers/go:1.20",
            "customizations": {
                "vscode": {
                    "extensions": ["golang.go"]
                }
            }
        }

INFO: The golang.go VSCode extension is officially maintained by the Go team. It provides helpful tools like syntax highlighting, debugging, and IntelliSense.

## Step 3: Verify Go Installation 🐹
Once the Dev Container is up and running, check the installed Go version:

Run in your terminal:

    go version

You should see output similar to:

    go version go1.20.0 linux/amd64

## Step 4: Create the Hello 423 Program ✨
Now its time to create your first Go program

1. Initialize the Go Module:

        go mod init example.com/hello

2. Create the main.go file:

        touch main.go

    This will create an empty file named main.go in the current directory.

4. Add the Code into the main.go file:

        package main

        import "fmt"

        func main() {
            fmt.Println("Hello COMP423")
        }

## Step 5: Compile and Run the Program 🚀

You can now run or build the program.

| Command           | Description                                                     |
|-------------------|-----------------------------------------------------------------|
| `go run main.go`  | Compiles and runs the code directly in one step.                |
| `go build	`       | Builds a binary file of the program (e.g., hello) for later use.|

1. Run the program directly:

        go run main.go

    Output:

        Hello COMP423

2. Build and execute the binary:
        go build
        ./hello

NOTE: Use go build to create a standalone binary for production environments. go run is mainly used during development.

## Step 6: Verify and Push 📝

1. Verify the program runs correctly.

2. Push your repository to GitHub:

        git add .
        git commit -m "Initial Go setup"
        git push origin main

## Links to Additional Resources 🔗
* [Go Documentation](https://go.dev/doc/)
* [MkDocs Documentation](https://www.mkdocs.org/)






