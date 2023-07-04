# Setting up
This repo shows how to set up a nexus server for use in your Synology NAS.

## Installation
This repo assumes you have docker and docker-compose installed in Synology NAS.

* Step 1: Go to File Station and open the docker folder. Inside the docker folder, create one new folder and name it nexus. Then, create a subfolder nexus-data.
* Step 2: Connect Synology via ssh
* Step 3: Change permissions on the nexus persistent data subdirectory
```
chown -R 200 /volume1/docker/nexus/nexus-data
```
* Step 4: Clone this repo in nexus folder
* Step 5: Now, you can run it via `docker-compose` directly:
```
docker-compose up -d
```

### Running
You can watch the logs as nexus comes up:
```
docker logs -f nexus
```

You are waiting to see:

```
-------------------------------------------------

Started Sonatype Nexus OSS 3.XX.XXX

-------------------------------------------------
```

Once it's running, visit:

http://{SynologyIP}}:8081

### First login
Click 'Sign In'.

You will sign in using the `admin` username.

You can find the initial admin password by running:

```
cat /volume1/docker/nexus/nexus-data/admin.password
```

On first login, you will be prompted to change the admin password.