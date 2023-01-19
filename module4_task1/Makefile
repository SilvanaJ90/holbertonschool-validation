help: ## Show help command
	@sed -ne '/@sed/!s/## //p' Makefile

.PHONY: build
build:  ## Create Website
	@sudo apt install ./hugo.deb
	@hugo
	@touch awesome-api

clean:  ## Delete content of dist folder
	@rm -rf dist/*

post:  ## Create a post
	@hugo new posts/$(POST_NAME).md
	@sed -i '/title:*/c\title: "$(POST_TITLE)"' ./content/posts/$(POST_NAME).md

package: ## zip website
	@hugo
	@zip awesome-website.zip ./dist

lint: ## lint with markdown
	@apt install curl -y
	@curl --silent --location https://deb.nodesource.com/setup_16.x | bash -
	@apt install nodejs -y
	@npm install -g markdownlint-cli 1>&2
	@markdownlint README.md
	@markdownlint DEPLOY.md

unit-tests: ## test file
	@echo "running unit tests"
	touch coverage-units.out

integration-tests: ## integrate file
	@echo "running integration tests"
	touch coverage-integrations.out

validate: ## valide file

.PHONY:
build-docker: ## build-docker
	@docker build -t "awesome:build" ./build

.PHONY: build-dependencies
build-dependencies: ## build dependencies
	@sudo apt install ./hugo.deb


integration-tests: ## run integration test
	@echo "running integration tests"
	touch coverage-integrations.out


validate: ## run validate

build-docker: ## build-docker
	@docker build -t "awesome:build" ./build