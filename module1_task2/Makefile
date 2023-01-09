build: ##jjjjj
	hugo -s . -d dist/

clean: ##jjjjj
	rm -rf dist/

post: ##jjjjj
	hugo new posts/$(POST_NAME).md
	sed -i 's/title: .*/title:"$(POST_TITLE)"/' content/posts/$(POST_NAME).md