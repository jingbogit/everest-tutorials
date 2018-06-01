# Continuous Integration

CI runs preset pipelines every time your push code to git. We have a docker hosted in the office. 

### create docker image

You may need permissions to create new image. Use existing ones when possible. 

Sample dockerfile for centos-webgl-dev-docker image:

```
FROM centos:7

#install git
RUN yum update -y
RUN yum install -y git

# ssh
RUN yum install -y vim openssh-clients

# make gcc
RUN yum install -y make gcc*

# install NODE v8
RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
RUN source ~/.bashrc \
  && nvm install v8.10.0 \ 
  && node --version \
  && npm -g i yarn 

CMD source /etc/profile && bash

```

### create a yml file

yml is written under your repo. A sample CI file `.gitlab-ci.yml` for altizure.gl-engine:

```
image: centos-webgl-dev-docker

before_script:
  # Install ssh-agent if not already installed, it is required by Docker.
  # (change apt-get to yum if you use a CentOS-based image)
  # - 'which ssh-agent || ( yum update -y && yum install openssh-client -y )'

  # Run ssh-agent (inside the build environment)
  - eval $(ssh-agent -s)

  # Add the SSH key stored in SSH_PRIVATE_KEY variable to the agent store
  - ssh-add <(echo "$SSH_PRIVATE_KEY")

  # For Docker builds disable host key checking. Be aware that by adding that
  # you are suspectible to man-in-the-middle attacks.
  # WARNING: Use this only with the Docker executor, if you use it with shell
  # you will overwrite your user's SSH config.
  - mkdir -p ~/.ssh
  - '[[ -f /.dockerenv ]] && echo -e "Host *\n\tStrictHostKeyChecking no\n\n" > ~/.ssh/config'
  - source /root/.bashrc

engine:
  stage: build
  script:
    - pwd
    - ls -l
    # clone the tools and bundle
    - git pull origin beta
    - git checkout beta
    - yarn
    - yarn lint && echo "Lints passed."
    - yarn debug && yarn release && "Build passed."
    - yarn test && echo "Tests passed."
    - echo "Done"


```

### Secret Variable

In gitlab settings -&gt; CI/CD -&gt; secret variables, set your ssh key. So git won't ask for password during the pipeline.

![](/assets/novice-ci-secret-variables.png)

