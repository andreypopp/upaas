# μPaaS

**WORK IN PROGRESS**

Nano-Platform-as-a-Service utilizes Docker containers and gitreceive to build
and run applications.

It is heavily based on Dokku but doesn't use Heroku buildpacks, instead it is
uses stacks declared directly as Dockerfiles and build instructions declared as
Makefiles.

## Make you app ready for μPaaS

Currently an application must have the following files in the repository root:

  * **Procfile** which defines how to run the app
  * **Makefile** with **build** target which describes how to build an app
    (install runtime dependencies and so on)
  * **.stack** which contains a single line with a name of the stack to use for
    running the app

In the future **Makefile** will be provided by stack you will not have to write
it unless you need to customize build process.
