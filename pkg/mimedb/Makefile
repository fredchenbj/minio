# Generate db.go from db.json downloaded nodejs mime-db project.
# NOTE: Autogenerated db.go needs to be vet proofed. \
	Manually edit json -> JSON for all variable names
all: download build

# Download db.json from NodeJS's mime-db project. It is under MIT license.
download:
	@mkdir db
	@wget -nv -q https://cdn.rawgit.com/jshttp/mime-db/master/db.json -O db/db.json


# After generating db.go, clean up downloaded db.json.
build: download
	@go run util/gen-db.go db/db.json > db.go
	@rm -f db/db.json
	@rm -rf db
	@echo Generated \"db.go\".
