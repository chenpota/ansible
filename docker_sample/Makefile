IMAGE_NAME=localhost:5000/docker_sample:ubuntu16.amd64

.PHONY: all
all: build

.PHONY: build
build:
	docker build \
		-t ${IMAGE_NAME} \
		--no-cache \
		--pull \
		.

.PHONY: push
push:
	docker push ${IMAGE_NAME}

.PHONY: clean
clean:
	docker rmi ${IMAGE_NAME} || true
