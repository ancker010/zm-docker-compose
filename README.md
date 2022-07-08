## Usage

Follow the instructions under each folder for the version you want to run.

1. `release` once edited to match, this will run the latest "release" version of ZM plus the EventServer with Pushover support.
 - You'll need to edit the `image:` to point to the appropriate version, check docker hub or ghcr.io for which tags are available.
2. `master-janus` without modification, this will run the latest NIGHTLY built version of ZM from the "master" branch.
 - This includes Janus support, plus EventServer with Pushover support.
 - NOTE: This being a nightly build, is sometimes broken, so muck around at your own risk.

NOTE: Both `docker-compose.yml` files include the appropriate labels to use Traefik as a reverse-proxy. If you're using that, great. If you want to, you'll need to get that up and running first.
If you don't use Traefik or use another reverse-proxy, just remove those lines and optionally change the docker network name.

In both cases, you'll need to already know how to:
1. Set up and config Zoneminder.
2. Set up and config the EventServer.

For `master-janus` you need to also:
1. Understand how to set up Janus.
