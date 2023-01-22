# Go-Hugo Website 

## Prerequisites

Before you begin this tutorial you must:

- [Install Hugo](https://gohugo.io/installation/)
- [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 

Requirements

- Use the theme “ananke” for the website by following the section Note for non-git users at the [Step 3](https://gohugo.io/getting-started/quick-start/#step-3-add-a-theme)
- Usage of Git Submodules is prohibited: there should be no file .gitmodules
- The website title should be “Awesome Inc.”
- The contents consists in a single blog post which title should be “Welcome to Awesome Inc.”, stored in a file named **welcome.md**
- All of the website’s source code is stored under a directory named **module1_task0**
- The command line hugo in **version 0.84.0** must be used
- The website is expected to be generated into the directory **module1_task0/dist/**
- The directory **module1_task0/dist/** must not be committed (it should be absent from the repository)
Here is a simple example of the expected generation process:
```
➜ ls -l dist/ 2>/dev/null | wc -l
0
➜ hugo > /dev/null 2>&1
➜ ls dist/ 2>/dev/null | grep -c 'index.html'
1
```

## Lifecycle

lifecycle is generally staying the same. In this project, you will start to define this lifecycle via the following steps::

- build: Build: Generate the website from the markdown and configuration files in the directory dist/

- clean: Cleanup the content of the directory dist/

- post: Post: Create a new blog post whose filename and title come from the environment variables POST_TITLE and

- help: prints out the list of targets and their usage. 

```
➜ ls -1 ./dist/
➜ make build
➜ ls -1 ./dist/index.html
index.html

➜ ls -1 ./content/posts/
welcome.md
➜ make POST_NAME=who-are-we POST_TITLE="Who are we" post
➜ ls -1 ./content/posts/
welcome.md who-are-we.md

➜ make clean
➜ ls -1 ./dist/
➜
➜ make help
help: prints out the list of targets and their usage.
```


go-build:        Builds the API binary file using go
hugo-build: check                Builds a website using gohugo on the dist folder
build:   Builds all that is needed for website
post:            Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME
check:   Lints and check for dead links on markdowns using markdownlint-cli and markdown-link-check
validate:  Validates dist/index.html using W3C Hbtn validator
run:     Runs the built binary and send everything to awesome.log
stop:    Terminates the execution of awesome-api
clean:   Removes binary and logs
test:    Tests API using go test
lint:    Lints all the go files using golangci-lint
unit-tests:      Runs implemented unit test using go test
integration-tests:       Runs integration test using go test
help:    Show this help message