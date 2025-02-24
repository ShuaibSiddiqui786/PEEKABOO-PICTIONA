<h1 align="center">Peekaboo-Pictiona</h1>


Peekaboo-Pictiona is an alternative to the web-based drawing game skribbl.io. My main
problems with skribbl.io were the ads and the fact that a disconnect would
cause you to lose your points. On top of that, the automatic word choice was
quite annoying and caused some frustration.

The site will not display any ads or share any data with third parties.

## Play now

Feel free to play on [peekaboo-pictiona.onrender](https://peekaboo-pictiona.onrender.com). Note
that the instance may not respond instantly, as it automatically shuts down
if no traffic is received.

## Configuration

Configuration is read from environment variables or a `.env` file located in
the working directory.

Available settings:

| Key                                       | Description                                                      | Default | Required |
| ----------------------------------------- | ---------------------------------------------------------------- | ------- | -------- |
| PORT                                      | HTTP port that the server listens to.                            | 8080    | True     |
| NETWORK_ADDRESS                           | TCP address that the server listens to.                          |         | False    |
| ROOT_PATH                                 | Changes the path (after your domain) that the server listens to. |         | False    |
| CORS_ALLOWED_ORIGINS                      |                                                                  | *       | False    |
| CORS_ALLOW_CREDENTIALS                    |                                                                  |         | False    |
| LOBBY_CLEANUP_INTERVAL                    |                                                                  | 90s     | False    |
| LOBBY_CLEANUP_PLAYER_INACTIVITY_THRESHOLD |                                                                  | 75s     | False    |

For more up-to-date configuration, read the
[config.go](/internal/config/config.go) file.

## Docker

Alternatively there's a docker container:

```shell
docker pull biosmarcel/scribble.rs:latest
```

Starting from v0.8.5, docker images are only built on tagged pushes. Each git
tag becomes a docker tag, however `latest` will always point to the latest tag.

There's also `biosmarcel/scribble.rs:windows-latest` in case you are interested
in running a native Windows container.

## Building / Running

Dependencies:
  * [go](https://go.dev/doc/install) version 1.21 or later
  * [git](https://git-scm.com/) (You can also download a .zip from Github)

In order to download and build, open a terminal and execute:

```shell
git clone https://github.com/scribble-rs/scribble.rs.git
cd scribble.rs
go build ./cmd/scribblers .
```

This will produce a portable binary called `scribblers` or `scribblers.exe` if
you are on Windows.

## Pre-compiled binaries

In the [Releases](https://github.com/scribble-rs/scribble.rs/releases) section
you can find the latest stable release.

Alternatively each commit uploads artifacts which will be available for a
certain time.

### Changing default port

The default port is `8080`. To override it, run:

```shell
docker run --pull always --env PORT=<port> -p <port>:<port> biosmarcel/scribble.rs:latest
```

## nginx 

Since Scribble.rs uses WebSockets, when running it behind an nginx reverse
proxy, you have to configure nginx to support that. You will find an example
configuration on the [related Wiki page](https://github.com/scribble-rs/scribble.rs/wiki/reverse-proxy-(nginx)).

Other reverse proxies may require similar configuration. If you are using a
well known reverse proxy, you are free to contribute a configuration to the
wiki.

## Contributing

There are many ways you can contribute:

* Update / Add documentation in the wiki of the GitHub repository
* Extend this README
* Create feature requests and bug reports
* Solve issues by creating Pull Requests
* Tell your friends about the project

## Credits

These resources are by people unrelated to the project, whilst not every of
these resources requires attribution as per license, we'll do it either way ;)

If you happen to find a mistake here, please make a PR. If you are one of the
authors and feel like we've wronged you, please reach out.

Some of these were slightly altered if the license allowed it.
Treat each of the files in this repository with the same license terms as the
original file.

* Logo - All rights reserved, excluded from BSD-3 licensing
* Background - All rights reserved, excluded from BSD-3 licensing
* Favicon - All rights reserved, excluded from BSD-3 licensing
* Rubber Icon - Made by [Pixel Buddha](https://www.flaticon.com/authors/pixel-buddha) from [flaticon.com](https://flaticon.com)
* Fill Bucket Icon - Made by [inipagistudio](https://www.flaticon.com/authors/inipagistudio) from [flaticon.com](https://flaticon.com)
* Kicking Icon - [Kicking Icon #309402](https://icon-library.net/icon/kicking-icon-4.html)
* Sound / No sound Icon - Made by Viktor Erikson (If this is you or you know who this is, send me a link to that persons Homepage)
* Profile Icon - Made by [kumakamu](https://www.iconfinder.com/kumakamu)
* [Help Icon](https://www.iconfinder.com/icons/211675/help_icon) - Made by Ionicons
* [Fullscreen Icon](https://www.iconfinder.com/icons/298714/screen_full_icon) - Made by Github
* [Pencil Icon](https://github.com/twitter/twemoji/blob/8e58ae4/svg/270f.svg)
* [Checkmark Icon](https://commons.wikimedia.org/wiki/File:Green_check_icon_with_gradient.svg)
* [Fill Icon](https://commons.wikimedia.org/wiki/File:Circle-icons-paintcan.svg)
* [Trash Icon](https://www.iconfinder.com/icons/315225/trash_can_icon) - Made by [Yannick Lung](https://yannicklung.com)
* [Undo Icon](https://www.iconfinder.com/icons/308948/arrow_undo_icon) - Made by [Ivan Boyko](https://www.iconfinder.com/visualpharm)
* [Alarmclock Icon](https://www.iconfinder.com/icons/4280508/alarm_outlined_alert_clock_icon) - Made by [Kit of Parts](https://www.iconfinder.com/kitofparts)
* https://www.iconfinder.com/icons/808399/load_turn_turnaround_icon TODO
