//download image of buildx (multiple architectures)
docker buildx ls
docker buildx create --name mybuilder --driver docker-container
docker buildx use mybuilder
docker buildx inspect

docker buildx build --platform linux/amd64, linux/arm64, linux/arm/v7 -t <username>/<image>:latest --push .

//example
docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 -t socialcode88/cron-ticker:osopolar --push .
