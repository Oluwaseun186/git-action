#INstall docker action
this github action install using official dcoker installation commands.

##Usage
To us this action in your repository, create a workflow (e.g, `.github/workflows/install-docker.yaml`) and the following content:

```yaml
name: Install docker
on: [push]
jobs:
  install-docker:
    runs-on: ubuntun-latest
    steps:
     -name: checkout repository
      uses: actions/checkout@v2
     -name: Install Docker
      uses: oluwaseun7/install-docker-actions@v1
     -name: Run docker image
      run:  docker build -t my-image:1
     -name: version
      run:  docker --version
     -name: Run tests
      run:  docker run my-image:1 test