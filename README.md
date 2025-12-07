# jenkins-demo

## About

Very basic pipeline to test a Jenkins installation that runs pipelines in containers.

## Server

The [`server/`](server) directory contains a `Dockerfile` for building a Jenkins 2.528.1 server image.

It also contains a `compose.yaml` for starting the server, alongside a Docker-in-Docker image, with `docker compose`.

To start the server, run:

```sh
cd server && docker compose up -d
```

## Agent

The [`agent/`](agent) directory contains an example `Dockerfile` for building a Jenkins agent container image.

The image is built automatically by Jenkins.

This image contains only `make`, our favourite code building tool, but it can easily be extended to add any software you may need.

## Pipeline

To add this pipeline to Jenkins Version 2.528.1 (2025-11-03):

- New Item
- Pipeline
- Tick "GitHub project", with url <https://github.com/clifford2/jenkins-demo/>
- Under "Pipeline", select "Pipeline script from SCM", and set:
	- Repository URL `https://github.com/clifford2/jenkins-demo.git`
	- Branch specifier: `*/main`
	- Script path: `Jenkinsfile` (default)

Building this pipeline will:

- Use `Jenkinsfile`
- Build an agent image using `agent/Dockerfile` (Debian image with `cmake`)
- Run `make build` inside a container using that image
