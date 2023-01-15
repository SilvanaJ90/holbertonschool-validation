build:	## Build: Generate the website from the markdown and configuration files in the directory dist/.
		hugo -s . -d dist/

clean: ## Cleanup the content of the directory dist/
		rm -rf dist/

post: ## Post: Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME.
		hugo new posts/$(POST_NAME).md
		sed -i 's/title: .*/title:"$(POST_TITLE)"/' content/posts/$(POST_NAME).md


help: ## prints out the list of targets and their usage. 
		cat README.md

package: ## implemented and documented. It should create a file named awesome-website.zip (not committed and deleted by make clean).
		hugo
		zip awesome-website.zip ./dist

lint: ## should be updated to lint the files README.md and DEPLOY.md with markdownlint command line
		markdownlint README.md
		markdownlint DEPLOY.md

unit-tests: ## test file


integration-tests: ## integrate file


validate: ## valide file