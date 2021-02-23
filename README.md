# tc_record
A python script automatically records TwitCasting stream in the background.

# Usage
## Install Dependencies
Install dependencies with `pip install -r requirements.txt`.

## Get Help
```
python3 record.py -h
```

```
usage: record.py [-h] [--proxy PROXY] [--user-agent USER_AGENT] [-t ITERVAL] user_id

TwitCasting live stream recorder.

positional arguments:
  user_id               The user id to record. i.e. the string after "https://twitcasting.tv/" in URL

optional arguments:
  -h, --help            show this help message and exit
  --proxy PROXY         Request with HTTP proxy. e.g. http://127.0.0.1:1080
  --user-agent USER_AGENT
                        Request with custom User Agent.
  -t ITERVAL, --iterval ITERVAL
                        Interval(sec) this script uses to check if live starts. Default: 10
```

## About Convert

Recorded videos are saved as MPEG-2 TS format, which is designed for live streaming.

You can simply remux them to MP4 format using ffmpeg:

```
ffmpeg -i xxx.ts -codec copy xxx.mp4
```

# References
[GitHub | twitcasting-recorder](https://github.com/printempw/twitcasting-recorder)

[GitHub | live-stream-recorder](https://github.com/printempw/live-stream-recorder)