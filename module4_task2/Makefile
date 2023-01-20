help: ## Build: Generate the website from the markdown and configuration files in the directory dist/.
	@sed -ne '/@sed/!s/## //p' Makefile

.PHONY: build
build: ## Cleanup the content of the directory dist/
	@sudo apt install ./hugo.deb
	@hugo
	touch awesome-api

clean: ## Post: Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME.
	@rm -rf dist/*

post: ## prints out the list of targets and their usage.
	@hugo new posts/$(POST_NAME).md
	@sed -i '/title:*/c\title: "$(POST_TITLE)"' ./content/posts/$(POST_NAME).md

package: ##  implemented and documented. It should create a file named awesome-website.zip 
	@hugo
	@zip awesome-website.zip ./dist

lint: ##  updated to lint the files README.md and DEPLOY.md with markdownlint command line
	@curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash - && sudo apt-get install -y nodejs
	@sudo npm install -g markdownlint-cli 1>&2
	@markdownlint README.md
	@markdownlint DEPLOY.md

unit-tests: ## run unitest
	@echo "running unit tests"
	touch coverage-units.out


integration-tests: ## run integration test
	@echo "running integration tests"
	touch coverage-integrations.out


validate: ## run validate

.PHONY:
build-docker: ## build-docker
	@docker build -t "awesome:build" ./build

.PHONY: build-dependencies
build-dependencies: ## build dependencies
	@sudo apt install ./hugo.deb

docker-tests: ## will use container-structure-test
	@curl -LO https://storage.googleapis.com/container-structure-test/latest/container-structure-test-linux-amd64 && chmod +x container-structure-test-linux-amd64 && sudo mv container-structure-test-linux-amd64 /usr/local/bin/container-structure-test
	@container-structure-test test --image gcr.io/registry/image:latest \ --config config.yaml

