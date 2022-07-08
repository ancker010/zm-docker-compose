## Usage

Edit the `docker-compose.yml` file as needed for your environment.
It uses Traefik for reverse-proxy. If you don't use/need that, then remove it and make sure to expose either port 80 or 443 (if you want to run TLS).

The `docker-compose.yml` file references a few files you'll need.
1. `env` make sure you edit this and make it available to both your DB and ZM containers.
2. `pushapi_pushover.py` this is the script that makes PushOver work. It's not included by default in EventServer, so you have to map it in.
3. `install-stuff.sh` you need to run this from inside the container after you start it. This will install the python stuff needed to make Pushover work.
 - NOTE: You'll need to re-run this any time the container is deleted. If the container is just restarted, you should be fine.
4. `janus.jcfg` just make sure this exists and has the right settings.
5. `janus.plugin.streaming.jcfg` same as the above.
6. `janus.js` this needs to be available in the webroot of the ZM container.

Once you have everything running, check the logs to make sure everything is sane.
Then browse to your docker host at port 80 or 443. This version of ZM does NOT use the /zm/ subdirectory in the URL. So you'll go to http://zm.example.com or whatever URL.

Follow the ZM and EventServer docs on how to set both up.
You also might need to read the Janus docs to get that working right.
