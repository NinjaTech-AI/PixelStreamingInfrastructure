##
## Avatar MatchMaker Service
##

.PHONY: build/local build/publish run/local login

IMAGE_NAME=avatar-matchmaker
ARTIFACT_REGISTRY=us-central1-docker.pkg.dev/avatar-sandbox/avatar
CURRENT_SHA=$(shell git rev-parse --short=8 HEAD)


login: 
	gcloud auth login

build/local:
	docker build -t ${IMAGE_NAME}:local .

run/local:
	docker run -p 9090:9090 -p 9091:90 ${IMAGE_NAME}:local

#
#https://cloud.google.com/run/docs/building/containers#docker
# Before using this tasks, configure docker to use gcloud auth 
# gcloud auth configure-docker us-central1-docker.pkg.dev
# gcloud auth login

build/publish:
	docker build -t ${ARTIFACT_REGISTRY}/${IMAGE_NAME}:${CURRENT_SHA} .
	docker push ${ARTIFACT_REGISTRY}/${IMAGE_NAME}:${CURRENT_SHA}