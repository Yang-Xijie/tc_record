# tc_record
A python script automatically records TwitCasting stream in the background.

# Usage
## Install Dependencies
Install dependencies with `pip install -r requirements.txt`.

usage: `python3 record.py [-h] [--proxy PROXY] [--user-agent USER_AGENT] [-t ITERVAL] user_id`

user_id refers to the name after `https://twitcasting.tv/` such as `hima_asmr`, `natsuiromatsuri`

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

We use `ffmpeg` to convert that format, which **requires `ffmpeg` on your computer**.

If you don't want to convert `.ts` file to `.mp4` file or ffmpeg is not installed , just comment lines in the script.

# Create executable file
Use `pyinstaller` to do that in order to package the script to make it easier to use. (**Notice**: Just packaging instead of compiling.)

```
pip3 install pyinstaller
pyinstaller -F -w record.py
```

`-F` means making script to executable file.

`-w` closes the debugging window.

Use `pyinstaller record.py --onefile` on windows to avoid being recognized as virus.

You can find executable file in `dist` folder in current wording directory.

# Others
## Generate requirements.txt 
```
pip install pipreqs
pipreqs ./
```
Generate requirements.txt which avoids including packages in Path. 

# References
[GitHub | twitcasting-recorder](https://github.com/printempw/twitcasting-recorder)

[GitHub | live-stream-recorder](https://github.com/printempw/live-stream-recorder)

[如何编译python使之成为可执行程序](http://www.360doc.com/content/19/0918/22/277688_861872169.shtml)

[CSDN | pyinstaller 生成exe之后不报毒的终极方法](https://blog.csdn.net/eastdawnc/article/details/113813790)