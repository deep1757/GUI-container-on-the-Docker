# GUI-container-on-the-Docker

you need to create a Dockerfile for your application. Here’s an example that runs the Firefox web browser:
FROM ubuntu:latest
RUN apt-get update && apt-get install -y firefox
CMD ["/usr/bin/firefox"]
# Now build and run the image:
docker-compose build
docker-compose up
A new Firefox window should appear on your desktop! The Firefox instance will run within the container, independently of any other open Firefox windows. The container will share your host’s X socket, so the containerised Firefox still shows up on your desktop.
# Handling X Authentication
Inside the Docker container, install the xauth package. Then run xauth add, passing the token you copied in the previous step.
$ apt install -y xauth 
$ xauth add <token>
$ xauth list
Your container should now successfully authenticate to the X Server.
