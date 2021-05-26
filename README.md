#  Preconfigured Minecraft server to run on a Raspberry Pi 4 under Docker

## Quick setup

Download/clone the repo on the server.

You will need Docker along with Docker-Compose or you could make a startup script in `/data` and run it that way.

Run Docker-Compose via `docker-compose up -d` (you may need to change the volume path in the `docker-compose.yml` file). The folder associated with the volume will have all the server config files (plugins, permissions etc.).

The server should be up at your RPi's IP, access the console with `docker attach mc-pi`.

## Performance

<p align="center"><img src="https://github.com/sabinM1/mc-pi/blob/master/images/tps.png"/></p>
<br>
<p align="center"><img src="https://github.com/sabinM1/mc-pi/blob/master/images/netdata.png"/></p>

## Modified configurations & preinstalled plugins

The `bukkit.yml`, `spigot.yml` and `paper.yml` are modified with recommended setting from the [*Server Optimization* guide by *Celebrimbor* on SpigotMC](https://www.spigotmc.org/threads/guide-server-optimization%E2%9A%A1.283181/) and also some personal preferences. **This also enables the anti-Xray protection built-in Paper.** Engine-mode 2 is enabled with a modified config from [*stonar96*'s *Recommended Paper Anti-Xray settings*](https://gist.github.com/stonar96/ba18568bd91e5afd590e8038d14e245e). Turn this off if you don't need it.

In the `KSpigot.yml` file the *mobAi* is set to *false* to reactivate the AI of the mobs. This lowers performance but restores normal functionality for any server type that makes use of them. Set it to *true* if you run a PVP only server (practice).

---

The following plugins are installed and configured:
  - [ViaVersion](https://www.spigotmc.org/resources/viaversion.19254/) - to support versions up to 1.16.5
  - [Updated-NoCheatPlus](https://github.com/Updated-NoCheatPlus/NoCheatPlus) - general-purpose anticheat with almost no false positives
  - [TabTPS](https://www.spigotmc.org/resources/tabtps-1-8-8-1-16-show-tps-mspt-and-more-in-the-tab-menu.82528/) - nice plugin to quickly display server performance
  - [TCPShield](https://github.com/TCPShield/RealIP)* - proxy/DDOS protection, ideal for a low-performance server, such as the RPi
  - [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/) - dependency of NCP and TCPShield

_*_TCPShield is disabled by default to avoid server connection confusion; set `only-allow-proxy-connections` to *true* if you use it, remove the plugin if it isn't needed.

## License

I am not the owner of the *kSpigot* PaperSpigot fork or of any files associated with it. **You need to [buy a copy](https://www.mc-market.org/resources/12302/) of it if you want to use it!** I chose it for its overall performance, but you can use any other PaperSpigot 1.12.2 version. By using it you agree to the [Terms and Conditions](https://www.mc-market.org/resources/12302/market-place-view-tnc) described on its page.

The *ViaVersion* plugin is licensed under the [MIT License](https://github.com/ViaVersion/ViaVersion/blob/master/LICENSE).<br>
The *Updated-NoCheatPlus* plugin is licensed under the [GPL-3.0 License](https://github.com/Updated-NoCheatPlus/NoCheatPlus/LICENSE.txt).<br>
The *TabTPS* plugin is licensed under the [MIT License](https://github.com/jpenilla/TabTPS/blob/master/license.txt).<br>
The *ProtocolLib* plugin is licensed under the [GPL-2.0 License](https://github.com/dmulloy2/ProtocolLib/blob/master/License.txt).

**Note: The source code of these plugins is not included, only the precompiled JARs.**

Any other files are licensed under the MIT License. You should have a copy along with this file.
