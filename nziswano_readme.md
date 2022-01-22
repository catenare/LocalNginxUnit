# Why the fork?
* We need to create a custom nginx unit image because wordpress does not support php 8 yet. 
* Creating an image that is php 7.4 friendly.
# Instructions to create custom nginx unit image
- Created branch from 1.26.1 tag

```sh
git checkout 1.26.1
git switch -c wordpress
```
* This is the base branch for building our docker image.

## Steps

```sh
cd pkg/docker/
# make build-php7.4 VERSION_php=7.4
make docker VERSION_php=7.4
# image created: unit:1.27.0-php7.4
```
* Created a github action that builds the image on Github and pushes it to the github docker image repository
* Image will run on both ARM systems
* Use the image as the basis for our Wordpress Docker Image
