# Zerops x Minecraft

Everyone knows Minecraft. Here is few-click deployment to zerops.io, so you can play with your friends and have FUN.

If you and your friends don't have IPv6 connectivity (as you probably won't have), follow these extra steps in GUI to enable
IPv4 connectivity:

- Projects > `minecraft-server`
    - IP Addresses & Public Routing Overview > (Activate) Unique IPv4 address
    - Services > `server` > Public access & internal ports > Public Access through IP Addresses > Setup up the first
      access through IPv4

Otherwise, you'll need to only activate public connectivity to Minecraft server port (GUI):

- Projects > `minecraft-server`
  - Services > `server` > Public access & internal ports > Public Access through IP Addresses > Setup up the first
    access through IPv6

You can change world name and seed by changing / filling up following environment variables in `zerops-import.yml` or in
GUI after deployment.

| key             | default      | description                                                                                                                           |
|-----------------|--------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `MC_WORLD_NAME` | world        | Name of your Minecraft world. Located in `/mnt/disk/$MC_WORLD_NAME`.                                                                  |
| `MC_SEED`       | zerops_rules | Your Minecraft world seed. If you change only seed you may have to delete the current world directory or changing the world name too. |

The world storage is persistent and located in `/mnt/disk`. Feel free to take backups or otherwise manipulate the mounted worlds directory by ssh-ing to the `server` (see [docs.zerops.io](https://docs.zerops.io) for more information about project VPN and SSH access).

Feel free to fork this repository and manipulate `server.properties` as you wish. Only important property for this recipe to work is `server-ip=0.0.0.0`. 

If you have any troubles running the server or whatever, join our [Discord server](https://discord.gg/WDvCZ54) and ask there :) **Enjoy!**
