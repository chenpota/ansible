# ansible

This repositroy shows an ansible demo using docker containers.

## Docker registry

    $ docker pull registry:2
    $ docker run -v ${PWD}/docker_registry:/var/lib/registry -d -p 5000:5000 --name registry registry:2

## Docker sample image

    $ make -C docker_sample build push clean

## Managed node

    $ make -C docker_managed-node
    $ docker run -v /var/run/docker.sock:/var/run/docker.sock --name managed-node -p 12345:22 --rm -d docker_managed-node:ubuntu16.amd64

## Control machine

    $ make -C docker_control-machine
    $ docker run --name control-machine --network host -v ${PWD}/ansible:/ansible --rm -ti docker_control-machine:ubuntu16.amd64

## Demo ansible in control machine

    $ ansible-playbook -i ansible/hosts ansible/site.yml
