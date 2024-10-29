# How to run a minecraft server
After Ubunto is downloaded
Use drive, not the hard drive
Before computer is booted, press f9 (or f2, or spam them all)
This gets into boot menu
Choose Ubunto
Try Ubunto
(terminal) ip a
Eno1 is internet, with the address
We want third party software, addition media for a desktop

People connecting will download tailscale (with personal account)
I will send a link to give server to their tailscale
They will have to run tailscale while running Minecraft


(controlling the server on my end)
tailscale status
ssh marc@cs-minecraft-server
sudo shutdown -h now 😊

(adding admin)
ssh marc@cs-minecraft-server
sudo useradd -m -s /bin/bash -d /home/username username (Change userame)
sudo usermod -aG sudo <username>    (Change username and <>)
 (changing their password, all admins can do this)
Sudo passwd <username> (password must be 8 characters)

When adding a person
send the tailscale link to the person (Have people skip the intro or else it wont work)
(Code to run to start the server)
docker run \
-d \
-p 25565:25565 \
--name mc \
-e EULA=TRUE \
--restart=always \
-v /home/marc/minecraftData:/data \
itzg/minecraft-server

(explanation)
-d means run in the background
-p means port forward the server port to virtual docker environment port
--name Is the name of the docker container
-e environment variable, it is accepting the agreements associated with the program
--restart=always means to restart the server whenever it crashes
-v volumes, This says that we shouldn’t delete this folder when we restart
Itzg/Minecraft-server is where download the name from (put url here if you want)


Going through docker

Docker ps will list the containers it holds. Adding -a to the end will show stopped containers
Docker logs <container name> will show the logs of the containers
Docker rm -f <container name> will delete the container

When adding others
Open a normal powershell, do tailscale
Give them the ip address of the server
Before Tuesday!
Make a git repo, add these instructions and allow people to copy the code

Learn more about backups

