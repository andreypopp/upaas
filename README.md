# μPaaS

**WORK IN PROGRESS**

Nano-Platform-as-a-Service utilizes Docker containers and gitreceive to build
and run applications.

It is heavily based on Dokku but doesn't use Heroku buildpacks, instead it is
uses stacks declared directly as Dockerfiles and build instructions declared as
Makefiles.

## Quickstart

On a server:

    % git clone https://github.com/andreypopp/upaas.git
    % cd upaas
    % make install

On a developer machine:

    % cat ~/.ssh/id_dsa.pub \
      | ssh <server> "sudo gitreceive upload-key <user>"

Deploy sample Node.js app:

    % git clone https://github.com/andreypopp/node-js-sample.git
    % cd node-js-sample
    % git remote add paas git@<server>:node-js-sample
    % git push paas master

Done!

## Make you app ready for μPaaS

Currently an application must have the following files in the repository root:

  * **Procfile** which defines how to run the app
  * **.stack** which contains a single line with a name of the stack to use for
    running the app

Optionally the following files can be also provided:

  * **Makefile.upaas** which specify **build** target with instructions on how
    to build the app. If no such files is provided stack's build instuctions
    will be used instead
