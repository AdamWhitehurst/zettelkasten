---

id: 202007271152
tags:
 - #minecraft
 - #spigot
 - #plugin
 - #server
primary source: https://github.com/DiscordSRV/DiscordSRV/wiki/Installation

---

# DiscordSRV

## Plugin Installation
https://github.com/DiscordSRV/DiscordSRV/wiki/Installation

Username: Wharp@live.com
Bot Name: RuinMineBot

- Unchecked `PUBLIC BOT` - Only I can invite bot to servers/channels
- Checked `SERVER MEMBER INTENT` - Ask permission to get member lists of servers?
- Added global and console channels to `config.yml`
- Added bot role in Discord
- Set Administrator privilege

## Bidirectional Role Sync Installation
- Add Discord Roles with Minecraft Permission Groups in `synchronization.yml`
- Need DiscordSRV 1.19.2 SNAPSHOT or higher:
https://github.com/DiscordSRV/DiscordSRV/pull/640


## Configuration

- Removed Discord-to-Minecraft chat prefix part: `DISCORD | `
- Set `GroupRoleSynchronizationMinecraftIsAuthoritative:  false`
- Set `NicknameSynchronizationEnabled: false`

## See Also

## References
https://www.spigotmc.org/resources/discordsrv.18494/
