# Copyright (c) 2018 Oracle and/or its affiliates. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

DOCKER_REGISTRY ?= wcr.io
DOCKER_IMAGE_NAME ?= oci-volume-provisioner-system-test
DOCKER_IMAGE_TAG ?= 1.0.2

.PHONY: build
build:
	docker build --build-arg http_proxy=${http_proxy} \
		         --build-arg https_proxy=${https_proxy} \
				 -t ${DOCKER_REGISTRY}/${DOCKER_REGISTRY_USERNAME}/${DOCKER_IMAGE_NAME}:${DOCKER_IMAGE_TAG} .

.PHONY: push
push: build
	docker login -u '$(DOCKER_REGISTRY_USERNAME)' -p '$(DOCKER_REGISTRY_PASSWORD)' $(DOCKER_REGISTRY)
	docker push ${DOCKER_REGISTRY}/${DOCKER_REGISTRY_USERNAME}/${DOCKER_IMAGE_NAME}:${DOCKER_IMAGE_TAG}
