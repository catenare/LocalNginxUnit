# Instructions to create custom nginx unit image

- We need to create a custom nginx unit image because wordpress does not support php 8 yet. Need to create an image that is 7.4 friendly.

- Created branch from 1.26.1 tag

```sh
git checkout 1.26.1
git switch -c wordpress
# make this the base branch for building our docker image.
```

## Steps

```sh
cd pkg/docker/
# make build-php7.4 VERSION_php=7.4
make docker VERSION_php=7.4
# image created: unit:1.27.0-php7.4
```

- Push resulting image to github registry

- Use as basis for php docker image with composer
