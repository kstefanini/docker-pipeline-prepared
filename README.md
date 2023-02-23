# Build custom image for pipeline with deps included

## Edit dockerfile to your need then build image
vim Dockerfile
docker build - < Dockerfile
// takes long time, like looooong time, network seems really slower than host

## Push image to docker hub
docker images
// <none>        <none>    e8dcceba6a1e   x minutes ago   xxxMB
docker tag e8dcceba6a1e rorto/php-pipeline-prepared:80
docker push youruser/php-pipeline-prepared:newtag

