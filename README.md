#  Preconfigured Minecraft server to run on a Raspberry Pi 4 under Docker

## Quick setup

Download/clone the repo on the server.

You will need Docker along with Docker-Compose or you could make a startup script in ```/data``` and run it that way.

Run Docker-Compose via ```docker-compose up -d``` (you may need to change the volume path in the ```docker-compose.yml``` file). The folder associated with the volume will have all the server config files (plugins, permissions etc.).

The server should be up at your RPi's IP, access the console with ```docker attach mc-pi```.

## Performance

<p align="center"><img src="https://github.com/sabinM1/mc-pi/blob/master/images/tps.png"/></p>
<br>
<p align="center"><img src="https://github.com/sabinM1/mc-pi/blob/master/images/netdata.png"/></p>

## License

I am not the owner of the *kSpigot* PaperSpigot fork or of any files associated with it. You need to [buy a copy](https://www.mc-market.org/resources/12302/) of it if you want to use it in this project. I used it for its overall performance, but you can use any other PaperSpigot 1.12.2 version.

Any other files are licensed under the MIT License. You should have a copy along with this file.
