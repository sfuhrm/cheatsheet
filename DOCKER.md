### Docker Cheat Sheet

#### Repository transfer and tagging

* Logging in to a repo, i.e. `hub.docker.com`<br/>
  `docker login $REPO`
* Logging off from a repo<br/>
  `docker logout $REPO`
* Tagging an image, i.e. before uploading to a repo<br/>
  `docker tag $REPO/$SOURCE_NAME:$SOURCE_TAG $REPO/$TARGET_NAME:$TARGET_TAG`
* Pulling an image from a repo<br/>
  `docker pull $REPO/$NAME:$TAG`
* Pushing an image to a repo<br/>
  `docker push $REPO/$NAME:$TAG`

#### Building

* Build an image from local directory<br/>
  `docker build -t$NAME:$TAG .`
* Build an image, with builg arguments (ARG in Dockerfile)<br/>
  `docker build --build-arg='KEY=VALUE' -t$NAME:TAG .`

#### Container lifecycle

* Start a container<br/>
  `docker run $IMAGE`
* Start a container, interactive session<br/>
  `docker run -ti $IMAGE`
* Show active containers<br/>
  `docker ps`
* Show logs of container<br/>
  `docker logs $CONTAINER`
* Kill container<br/>
  `docker container kill $CONTAINER`
* Clean up unused containers<br/>
  `docker container prune`
* Attach to a running container, interactive session<br/>
  `docker exec -ti $CONTAINER /bin/bash`
* Copy files from container filesystem to host filesystem<br/>
  `docker cp $CONTAINER:$SRC_PATH $DEST_PATH`
* Copy files from host filesystem to container filesystem<br/>
  `docker cp $SRC_PATH $CONTAINER:$DEST_PATH`

#### Image maintenance

* Show images<br/>
  `docker image ls`
* Delete image<br/>
  `docker image rm $IMAGE`
* Remove unused images<br/>
  `docker image prune`
* Show sizes of each image layer<br/>
  `docker history --no-trunc $IMAGE`

#### Image import / export

* Export image as tar archive to stdout<br/>
  `docker save $IMAGE`
* Import image from tar archive from stdin<br/>
  `docker load`
