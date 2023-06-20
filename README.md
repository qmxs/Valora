<div align="center">
<img src='https://cdn.jsdelivr.net/gh/GamerNoTitle/VALORA@dev/assets/img/head.png'>
</div>

# VLR | Valora: What it is in my VALORANT Store TODAY??

English | [简体中文](https://github.com/GamerNoTitle/VSC/blob/master/docs/README_CN.md)

This is a website that helps you peek your shop and night market of VALORANT. It's a project that I make on my spare time.

There are a lot of application on the network that can help you do that and they even better than mine. If you are worried about my project, you can use theirs.

You need to read FAQ before you use: [FAQ](https://gamernotitle.notion.site/VALORA-FAQ-86f072f8cebf4a8d9453a795b24cd507)

[Project Milestones (CHINESE)](https://github.com/users/GamerNoTitle/projects/1)

## Quick Start

You can access [https://val.bili33.top](https://val.bili33.top) to start your shop peek. The production server will not storage your username & password

- Stable Service (Master branch): [https://val.bili33.top](https://val.bili33.top)
- Developing Service (Dev branch): [https://dev.val.bili33.top](https://dev.val.bili33.top)

## Build your own

### Run on Docker

https://hub.docker.com/r/gamernotitle/vsc

### Run on Railway

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/JuUPyU?referralCode=U8coe_)

### Run on VPS/PaaS

First you need a server/Paas platform which can run python and flask. Fork this repo to your account.

You need to install some requirements on your server, use the following command.

> On some servers, you may need to use `pip3` instead of using `pip`. Meanwhile, you also need to use `python3` to instead of using `python` or `py`

```shell
$ pip install -r requirements.txt
```

After installation, you can change the listening address & port. We use `0.0.0.0:8080` as default.

Every time you start the server, the session key will be generated. That means all the logged in users will need to re-login. If this is not you wish, you can use Redis as your session storage.

You need to configurate the following items:

```shell
$ export SESSION_TYPE=filesystem|redis  # If you want to use redis u need to set it as redis, and configure the following items
$ export REDIS_URL=<Your Redis URL>
# If your redis url cannot be parsed
$ export REDIS_HOST=<Your Redis Host>
$ export REDIS_PORT=<Your Redis Port>
$ export REDIS_PASSWORD=<Your Redis Password>
# Optional
$ export REDIS_SSL=True # If your redis does not support this, please DO NOT configure it, or this will make your application timeout.
```

After doing all things above, you can turn your server on. Using the following command to do that.

```shell
$ python app.py
```

Now, you can access [http://127.0.0.1:8080](http://127.0.0.1:8080) (If you haven't changed it), and you will see your website.

## Dashboard

> For docker users, this feature will only monitor this alive container. Once u restart the container, this will reset. Since the data is saved in sqlite instead of Redis.

VSC uses `flask-profiler` to help developers to monitor its work. In order to enable it, u need to set the following variables

```shell
$ export PROFILER=1 # Just dont leave it empty
$ export PROFILER_AUTH=True # Basic auth of the dashboard | U can turn it off by leaving it empty
$ export PROFILER_USER=admin    # Set it as your creds
$ export PROFILER_PASS=password
```

After u set them, u can access your dashboard from `/profiler`

## Args

|    Path     |   Args   |                Options                 |                     Mark                     |                           Example                           |
| :---------: | :------: | :------------------------------------: | :------------------------------------------: | :---------------------------------------------------------: |
|  (global)   |   lang   |          en/zh-CN/zh-TW/ja-JP          |      Change the language of the website      |               https://val.bili33.top/?lang=en               |
|  /library   |  query   |                 (Any)                  |             Search for the skins             | https://val.bili33.top/library?query=Magepunk%20Sparkswitch |
| /api/reauth | redirect | `/market` `/market/night` `/inventory` | Redirect to correct page after reauthorizing |     https://val.bili33.top/api/reauth?redirect=/market      |

## Credit

[Prodzify/Riot-auth (github.com)](https://github.com/Prodzify/Riot-auth)

[Valorant-API](https://valorant-api.com/)

[Soft-ui-design-system](https://github.com/creativetimofficial/soft-ui-design-system)

[VALORANT Fandom Wiki (Price Data Source)](https://valorant.fandom.com/wiki/VALORANT_Wiki)

## Referrance

There's no any good doc on the network (at least i didn't find that). Here's my doc. (I find one and edit based on the doc [https://ultronxr2ws.notion.site/UAIOSC-valorant-GitHub-Valorant-API-0ac20cd4c5b744148a74c6cd0f3380dc](https://ultronxr2ws.notion.site/UAIOSC-valorant-GitHub-Valorant-API-0ac20cd4c5b744148a74c6cd0f3380dc))

[Referrance Doc (CHINESE)](https://gamernotitle.notion.site/Valorant-API-baffa2069fb848a781664432564e94d0)

[Developing Log (CHINESE)](https://bili33.top/posts/Valorant-Shop-with-API/)

## Sponsor

[https://bili33.top/sponsors/](https://bili33.top/sponsors/)