# Shelbot - An IRC karma bot.

Shelbot is a simple IRC karma bot written in Golang.

[![Go Report Card](https://goreportcard.com/badge/github.com/davidjpeacock/shelbot)](https://goreportcard.com/report/github.com/davidjpeacock/shelbot)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/davidjpeacock/shelbot/master/LICENSE)

## Configuration

Create a JSON configuration file with IRC details. By default Shelbot will look for this file in `~/.shelbot.conf`, this can be changed with the command line option `-config <file>` Example:

```
{
	"server":  "irc.freenode.org",
	"port":    6667,
	"nick":    "shelbot",
	"channel": "#shelly",
	"pass":    "",
	"user":    "Sheldon Cooper"
}
```

## Usage with systemd

1. Build shelbot for your platform of choice, copy the binary over to your system
2. Tailor the shelbot.service file provided under the systemd directory to suit your USER and GROUP
3. `cp shelbot.service /etc/systemd/system`
4. `sudo systemctl daemon-reload`
5. `systemctl start|stop|status shelbot`

Shelbot logs to `~/.shelbot.log`

## Shelbot usage

In channel, you can invoke shelbot commands as follows.

`shelbot help`

shelbot commands available: `help`, `version`, `query item`, `topten`, `bottomten`
Karma can be adjusted thusly: `foo++` and `bar--`

For data persistence, Shelbot stores karma as a JSON in the default location`~/.shelbot.json`, this can be configured with the command line option `-karmaFile <file>`

## License and Copyright

Copyright (c) 2017 David J Peacock - david.j.peacock@gmail.com

Please see LICENSE file for details.
