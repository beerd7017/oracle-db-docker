
## Docker Instructions
1) Install [Docker Toolbox for Windows](https://docs.docker.com/toolbox/toolbox_install_windows/#step-3-verify-your-installation).
2) Run `docker run hello-world` command in the Docker Toolbox terminal.

## Building Oracle Database Docker Install Images
1) Clone git [Oracle .git repo](https://github.com/oracle/docker-images);
2) Pull in the `oracle/docker-images/OracleDatabase` directory into your project.
3) Download an [Oracle Database](http://www.oracle.com/technetwork/database/database-technologies/express-edition/downloads/index.html).
4) Add the installation files to `src/OracleDatabase/11.2.0.2`.
5) Run `src/OracleDatabase/buildDockerImage.sh -v 11.2.0.2`.
6) Once the script is finished, you can verify the image was created by running `docker image ps`.

## Running the new Docker image
1) Run the following command:

`docker run -it --name dennis-local \
 --shm-size="2g" \
 -p 1521:1521 -p 8080:8080 \
 -e ORACLE_PWD=apps \
 destepp11/oracle/database:11.2.0.2-xe`
 
 ## Accessing the Container from the Host
 Since I'm on Windows 10 Home edition, I have to run the command `docker-machine ip` to find out what the docker IP address is. Generally it's 
 `192.168.99.100`


