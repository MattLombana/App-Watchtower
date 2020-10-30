# App-Watchtower

## Running the Containers

1. Update the following environment variable in [docker-compose.yml](./Docker/docker-compose.yml)
    * `WATCHTOWER_NOTIFICATION_SLACK_HOOK_URL=https://hooks.slack.com/services/xxx/yyyyyyyyyyyyyyy`
2. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## Watchtower Labels

* Force Watchtower to monitor but not update the container
    * `com.centurylinklabs.watchtower.monitor-only="true"`
* Force Watchtower to update the container
    * `com.centurylinklabs.watchtower.enable=true`
* Run a script before or after you restart a container:
    * `com.centurylinklabs.watchtower.lifecycle.pre-check="/example.sh"`
    * `com.centurylinklabs.watchtower.lifecycle.pre-update="/example.sh"`
    * `com.centurylinklabs.watchtower.lifecycle.post-update="/example.sh"`
    * `com.centurylinklabs.watchtower.lifecycle.post-check="/example.sh"`
