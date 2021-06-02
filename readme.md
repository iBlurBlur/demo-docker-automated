# Build Image Node.js

- docker build . -t iblurblur/my-node:1.0
- docker images
- docker push iblurblur/my-node:1.0

# Commit Container

- docker run --name some-alpine -it alpine
  - apk add --no-cache git
  - git --version
- docker commit some-alpine iblurblur/alpine-git:1.0
- docker images
- docker push iblurblur/alpine-git:1.0

# Re-Tagging an existing local

- docker pull alpine
- docker tag alpine iblurblur/my-alpine:1.0
- docker images
- docker push iblurblur/my-alpine:1.0

# Searching for Repositories

https://docs.docker.com/engine/reference/commandline/search/

- docker search mongo
  mark: AUTOMATED is automated builds
- docker search --filter stars=100 --filter is-official=true --format "table {{.Name}}\t{{.StarCount}}" mongo

---

# Automated builds
docker run -p 1150:8080 --name some-my-node -d iblurblur/my-node
