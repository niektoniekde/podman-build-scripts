# Description
This repository keeps scripts wrapping podman build and push actions around with some variables so there is no need to remember arguments and their syntax.
 
Just create an 'env' file and keep the directory structure:  
`${NAMESPACE}/${REPOSITORY}/${TAG}` 
 
Each directory under repository directory is dealt as tag.  
So for example if the directory structure looks like this:
```
  niektoniekde/
    rsyslog/
      latest/
      alpine-3.16/
```

Two images will be built using `podman-build-img`:
* **niektoniekde/rsyslog:latest**
* **niektoniekde/rsyslog:alpine-3.16**

and also these two images will be push to registry with `podman-push-img`.

# Usage
* ``podman-build-img <file.env>``
* ``podman-push-img <file.env>``

## Expected variables
* ``$REGISTRY`` - registry where images will be pushed.
* ``$NAMESPACE`` - namespace where repositories reside, eg. your login name at Docker Hub.
* ``$REPOSITORY`` - repository name.
* ``$REGISTRY_AUTH_FILE`` - auth file to registry provided to podman by ``--authfile`` argument. 
