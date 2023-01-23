help: Build: Generate the website from the markdown and configuration files in the directory dist/.
build: Cleanup the content of the directory dist/
clean: Post: Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME.
post: prints out the list of targets and their usage.
package:  implemented and documented. It should create a file named awesome-website.zip 
lint:  updated to lint the files README.md and DEPLOY.md with markdownlint command line
unit-tests: run unitest
integration-tests: run integration test
validate: run validate
build-docker: build-docker
build-dependencies: build dependencies
docker-tests: will use container-structure-test