export GH_USERNAME="kjejac-alt"
export GH_TOKEN="_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--"
export GH_IMAGE_NAME="hello-world"
export GH_VER="1.0.0"
export GH_TAG_NAME="ghcr.io/$GH_USERNAME/$GH_IMAGE_NAME:$GH_VER"

echo $GH_TOKEN | docker login ghcr.io -u $GH_USERNAME --password-stdin

docker tag hello-world:1.0.0 ghcr.io/kjejac-alt/hello-world:1.0.0
docker tag $GH_IMAGE_NAME:latest ghcr.io/$GH_USERNAME/$GH_IMAGE_NAME:$GH_VER

`# docker push $GH_TAG_NAME`
docker push ghcr.io/kjejac-alt/hello-world:1.0.0

LABEL org.opencontainers.image.source https://github.com/OWNER/REPO