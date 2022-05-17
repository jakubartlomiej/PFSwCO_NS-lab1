# PFSwCO_NS-lab1

Link do DockerHub [jakubartlomiej](https://hub.docker.com/r/jakubartlomiej/lab1/tags)

P5.1

Wywołane komendy: 

1. docker run --rm --privileged multiarch/qemu-user-static --reset -p yes

```
Setting /usr/bin/qemu-alpha-static as binfmt interpreter for alpha
Setting /usr/bin/qemu-arm-static as binfmt interpreter for arm
Setting /usr/bin/qemu-armeb-static as binfmt interpreter for armeb
Setting /usr/bin/qemu-sparc-static as binfmt interpreter for sparc
Setting /usr/bin/qemu-sparc32plus-static as binfmt interpreter for sparc32plus
Setting /usr/bin/qemu-sparc64-static as binfmt interpreter for sparc64
Setting /usr/bin/qemu-ppc-static as binfmt interpreter for ppc
Setting /usr/bin/qemu-ppc64-static as binfmt interpreter for ppc64
Setting /usr/bin/qemu-ppc64le-static as binfmt interpreter for ppc64le
Setting /usr/bin/qemu-m68k-static as binfmt interpreter for m68k
Setting /usr/bin/qemu-mips-static as binfmt interpreter for mips
Setting /usr/bin/qemu-mipsel-static as binfmt interpreter for mipsel
Setting /usr/bin/qemu-mipsn32-static as binfmt interpreter for mipsn32
Setting /usr/bin/qemu-mipsn32el-static as binfmt interpreter for mipsn32el
Setting /usr/bin/qemu-mips64-static as binfmt interpreter for mips64
Setting /usr/bin/qemu-mips64el-static as binfmt interpreter for mips64el
Setting /usr/bin/qemu-sh4-static as binfmt interpreter for sh4
Setting /usr/bin/qemu-sh4eb-static as binfmt interpreter for sh4eb
Setting /usr/bin/qemu-s390x-static as binfmt interpreter for s390x
Setting /usr/bin/qemu-aarch64-static as binfmt interpreter for aarch64
Setting /usr/bin/qemu-aarch64_be-static as binfmt interpreter for aarch64_be
Setting /usr/bin/qemu-hppa-static as binfmt interpreter for hppa
Setting /usr/bin/qemu-riscv32-static as binfmt interpreter for riscv32
Setting /usr/bin/qemu-riscv64-static as binfmt interpreter for riscv64
Setting /usr/bin/qemu-xtensa-static as binfmt interpreter for xtensa
Setting /usr/bin/qemu-xtensaeb-static as binfmt interpreter for xtensaeb
Setting /usr/bin/qemu-microblaze-static as binfmt interpreter for microblaze
Setting /usr/bin/qemu-microblazeel-static as binfmt interpreter for microblazeel
Setting /usr/bin/qemu-or1k-static as binfmt interpreter for or1k
Setting /usr/bin/qemu-hexagon-static as binfmt interpreter for hexagon
```
2. docker buildx create --name buildix-builder
3. docker buildx use buildix-builder
4. docker buildx inspect --bootstrap

Name:   buildix-builder
Driver: docker-container
```
Nodes:
Name:      buildix-builder0
Endpoint:  unix:///var/run/docker.sock
Status:    running
Platforms: linux/amd64, linux/amd64/v2, linux/386, linux/arm64, linux/riscv64, linux/ppc64le, linux/s390x, linux/mips64le, linux/mips64
```
5. docker buildx build . -t jakubartlomiej/lab1:bx --platform linux/amd64,linux/arm64,linux/amd64/v2,linux/s390x --push 
```
[+] Building 212.8s (29/29) FINISHED                                                                                                                                                                       
 => [internal] load build definition from Dockerfile                                                                                                                                                  0.0s
 => => transferring dockerfile: 217B                                                                                                                                                                  0.0s
 => [internal] load .dockerignore                                                                                                                                                                     0.0s
 => => transferring context: 2B                                                                                                                                                                       0.0s
 => [linux/s390x internal] load metadata for docker.io/library/node:alpine                                                                                                                            0.8s
 => [linux/amd64 internal] load metadata for docker.io/library/node:alpine                                                                                                                            0.8s
 => [linux/arm64 internal] load metadata for docker.io/library/node:alpine                                                                                                                            0.8s
 => [linux/amd64/v2 internal] load metadata for docker.io/library/node:alpine                                                                                                                         0.8s
 => [linux/amd64 1/5] FROM docker.io/library/node:alpine@sha256:f4d6916c5625853e81994b5cb53ad3eb27e5fec9451c579d298fee0c508fe621                                                                      0.0s
 => => resolve docker.io/library/node:alpine@sha256:f4d6916c5625853e81994b5cb53ad3eb27e5fec9451c579d298fee0c508fe621                                                                                  0.0s
 => [internal] load build context                                                                                                                                                                     0.0s
 => => transferring context: 91B                                                                                                                                                                      0.0s
 => [linux/arm64 1/5] FROM docker.io/library/node:alpine@sha256:f4d6916c5625853e81994b5cb53ad3eb27e5fec9451c579d298fee0c508fe621                                                                      0.0s
 => => resolve docker.io/library/node:alpine@sha256:f4d6916c5625853e81994b5cb53ad3eb27e5fec9451c579d298fee0c508fe621                                                                                  0.0s
 => [linux/s390x 1/5] FROM docker.io/library/node:alpine@sha256:f4d6916c5625853e81994b5cb53ad3eb27e5fec9451c579d298fee0c508fe621                                                                      0.0s
 => => resolve docker.io/library/node:alpine@sha256:f4d6916c5625853e81994b5cb53ad3eb27e5fec9451c579d298fee0c508fe621                                                                                  0.0s
 => [linux/amd64/v2 1/5] FROM docker.io/library/node:alpine@sha256:f4d6916c5625853e81994b5cb53ad3eb27e5fec9451c579d298fee0c508fe621                                                                   0.0s
 => => resolve docker.io/library/node:alpine@sha256:f4d6916c5625853e81994b5cb53ad3eb27e5fec9451c579d298fee0c508fe621                                                                                  0.0s
 => CACHED [linux/s390x 2/5] WORKDIR /usr/app                                                                                                                                                         0.0s
 => CACHED [linux/s390x 3/5] COPY ./package.json ./                                                                                                                                                   0.0s
 => CACHED [linux/s390x 4/5] RUN npm install                                                                                                                                                          0.0s
 => CACHED [linux/s390x 5/5] COPY ./ ./                                                                                                                                                               0.0s
 => CACHED [linux/arm64 2/5] WORKDIR /usr/app                                                                                                                                                         0.0s
 => CACHED [linux/arm64 3/5] COPY ./package.json ./                                                                                                                                                   0.0s
 => CACHED [linux/arm64 4/5] RUN npm install                                                                                                                                                          0.0s
 => CACHED [linux/arm64 5/5] COPY ./ ./                                                                                                                                                               0.0s
 => CACHED [linux/amd64 2/5] WORKDIR /usr/app                                                                                                                                                         0.0s
 => CACHED [linux/amd64 3/5] COPY ./package.json ./                                                                                                                                                   0.0s
 => CACHED [linux/amd64 4/5] RUN npm install                                                                                                                                                          0.0s
 => CACHED [linux/amd64 5/5] COPY ./ ./                                                                                                                                                               0.0s
 => CACHED [linux/amd64/v2 2/5] WORKDIR /usr/app                                                                                                                                                      0.0s
 => CACHED [linux/amd64/v2 3/5] COPY ./package.json ./                                                                                                                                                0.0s
 => CACHED [linux/amd64/v2 4/5] RUN npm install                                                                                                                                                       0.0s
 => CACHED [linux/amd64/v2 5/5] COPY ./ ./                                                                                                                                                            0.0s
 => exporting to image                                                                                                                                                                              212.0s
 => => exporting layers                                                                                                                                                                               0.0s
 => => exporting manifest sha256:ba809f99d1c1c8392f5da4d1f35494c4528a73e0297daf6821185410756c79a1                                                                                                     0.0s
 => => exporting config sha256:3c24cec560d6178cd5c4468a66ba8fac482c5413a22a5409abfee3cb741b5214                                                                                                       0.0s
 => => exporting manifest sha256:6022f6897a939f90373636421fca8742551a798d1cbbe2688655de112bd3c4ed                                                                                                     0.0s
 => => exporting config sha256:91ee7b40aa0cfedcfd6daf0fb6e5fda280cfad6f7a0d07ff0bd912a3f45851fc                                                                                                       0.0s
 => => exporting manifest sha256:ef930494ac88b82470f8b5e8e1e256bd2d1f11c02eafe351302b390d44d3c074                                                                                                     0.0s
 => => exporting config sha256:28fb2678646716f41256198e9dc2ec3f807918488e7a10648deb76f69bc18ba3                                                                                                       0.0s
 => => exporting manifest sha256:6bced76ce5a64c14962cf573be92057d5c97e7753d61166913cfb0ba9456c106                                                                                                     0.0s
 => => exporting config sha256:dfd0c2e9e0782b0051512e08f17c38d7b8f1aee0d7d1f8eac28f827c65592644                                                                                                       0.0s
 => => exporting manifest list sha256:f6c3c645f3427fdbffd8b953eff588ad9c52facc6726ca8115432c9bd0aefbdd                                                                                                0.0s
 => => pushing layers                                                                                                                                                                               208.8s
 => => pushing manifest for docker.io/jakubartlomiej/lab1:bx@sha256:f6c3c645f3427fdbffd8b953eff588ad9c52facc6726ca8115432c9bd0aefbdd                                                                  3.1s
 => [auth] jakubartlomiej/lab1:pull,push token for registry-1.docker.io   
 ```
 6. docker buildx imagetools inspect jakubartlomiej/lab1:bx
```
Name:      docker.io/jakubartlomiej/lab1:bx
MediaType: application/vnd.docker.distribution.manifest.list.v2+json
Digest:    sha256:f6c3c645f3427fdbffd8b953eff588ad9c52facc6726ca8115432c9bd0aefbdd
           
Manifests: 
  Name:      docker.io/jakubartlomiej/lab1:bx@sha256:ba809f99d1c1c8392f5da4d1f35494c4528a73e0297daf6821185410756c79a1
  MediaType: application/vnd.docker.distribution.manifest.v2+json
  Platform:  linux/amd64
             
  Name:      docker.io/jakubartlomiej/lab1:bx@sha256:6022f6897a939f90373636421fca8742551a798d1cbbe2688655de112bd3c4ed
  MediaType: application/vnd.docker.distribution.manifest.v2+json
  Platform:  linux/arm64
             
  Name:      docker.io/jakubartlomiej/lab1:bx@sha256:ef930494ac88b82470f8b5e8e1e256bd2d1f11c02eafe351302b390d44d3c074
  MediaType: application/vnd.docker.distribution.manifest.v2+json
  Platform:  linux/amd64/v2
             
  Name:      docker.io/jakubartlomiej/lab1:bx@sha256:6bced76ce5a64c14962cf573be92057d5c97e7753d61166913cfb0ba9456c106
  MediaType: application/vnd.docker.distribution.manifest.v2+json
```


D5.1

1.docker buildx build . -t jakubartlomiej/lab1:nginx --platform linux/amd64,linux/arm64,linux/amd64/v2 --push 

Wykorzystałem Dockerfile z zadania P5.1 zmieniając drugi wiersz: 
```
# Specify a base image
FROM nginx:latest

WORKDIR /usr/app

# Install some depenendencies
COPY ./package.json ./
RUN npm install
COPY ./ ./

# Default command
CMD ["npm", "start"]
```
