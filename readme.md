# Installing Nextcloud server on Raspberry Pi using Docker network

> Note: To get an SSL certificate issued, you need a domain name. Certificates can't be signed to an IP address any more.

1. Clean install of Raspbian Buster without DE (set up SSH)
 -> secure Raspi following a manual on [their website](https://www.raspberrypi.org/documentation/configuration/security.md)
2. Install Docker (currently ` curl -sSL get.docker.com | CHANNEL='nightly' bash `)
3. ` sudo groupadd docker && sudo usermod -aG docker $USER `
4. ` sudo systemctl enable docker `
5. Install docker-compose

6. Copy the files in this directory to your desired location

7. Substitute all ellipses in docker-compose.yml with your settings

8. ` docker compose up -d `
9. ` docker network inspect NETWORK ` (if you don't know the name, find it by ` docker network ls `) and note the ip address of mariadb server

10. Open the page in web browser, there you should see the config page.
11. Set your credentials, and set the connection to mysql (it's in the docker network, so you have to set address mentioned above). Do not change the data directory, this one is the path inside the Docker container. The data directory cound be changed BEFORE installation in the docker-compose.yml file.
