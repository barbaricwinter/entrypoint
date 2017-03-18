# entrypoint

This is the main entrypoint.

## Usage

```
xhost +local: &&
    export ENTRYPOINT=entrypoint && # or whatever volume you store this in
    docker \
    	run \
    	--interactive \
    	--tty \
    	--rm \
    	--volume ${ENTRYPOINT}:/entrypoint:ro \
    	--workdir /entrypoint \
    	--volume /var/run/docker.sock:/var/run/docker.sock:ro \
    	--env HOST_UID=${UID} \
    	--env HOST_USER=${USER} \
    	--env DISPLAY \
    	tidyrailroad/docker-compose:0.0.1 \
	up
```

where entrypoint is the volume that you store this in