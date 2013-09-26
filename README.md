# μPaaS

Nano-Platform-as-a-Service utilizes Docker containers and gitreceive to build
and run applications.

It is heavily based on Dokku but doesn't use Heroku buildpacks, instead it is
uses stacks declated directly as Dockerfiles and build instructions declated in
Makefiles.
