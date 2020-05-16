# Go Service Dynamodb

Service type for AWS Lambda Dynamodb

## Table of Contents

- [Setup](#setup)
- [Build](#build)

## Setup

Snap install is the easiest for me to install Go lang as I am running on Ubuntu 18.04

https://snapcraft.io/install/go/ubuntu

```sh

sudo snap install --classic --channel=1.11/stable go

```

Go to root directory and invoke installation of Go packages, `-v` for verbose


```sh

go get -v 

```

## Build

You may follow the steps to build [here](https://docs.aws.amazon.com/lambda/latest/dg/golang-package.html)

We are on service arch that all resources are in one lambda. When building, build the whole folder rather that one lambda per resource


```sh

go build -o main books

```

`main` will be the executable we will be zipping, and the books is the directory of go files we built

```sh

zip main.zip main

```

Upload the `main.zip` to your lambda and ensure that `Handler` is `main`

