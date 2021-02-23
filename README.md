# tc_record
A python script automatically records TwitCasting stream in the background.

# Usage
Install dependencies with `pip install -r requirements.txt`.



Recorded videos are saved as MPEG-2 TS format, which is designed for live streaming.

You can simply remux them to MP4 format using ffmpeg:

```
ffmpeg -i xxx.ts -codec copy xxx.mp4
```

# References
[GitHub | twitcasting-recorder](https://github.com/printempw/twitcasting-recorder)

[GitHub | live-stream-recorder](https://github.com/printempw/live-stream-recorder)