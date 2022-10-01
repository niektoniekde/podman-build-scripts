# Description
This repository keeps scripts wrapping podman build and push
actions around with some variables so there is no need to
remember arguments and their syntax.

Just create an 'env' file and keep the directory structure:
`${NAMESPACE}/${REPOSITORY}/${TAG}`

Each directory under repository directory is dealt as tag.
So if the directory structure looks like this:
``
    niektoniekde/
        rsyslog/
            latest/
            alpine-3.16/
``

Two images will be built using `podman-build-img`:
* niektoniekde/rsyslog:latest
* niektoniekde/rsyslog:alpine-3.16

and also these two images will be push to registry
with `podman-push-img`.
