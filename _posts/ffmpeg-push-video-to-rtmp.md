---
layout: post
title: "Test Theme Styles"
---

http://stackoverflow.com/questions/29018606/android-stream-camera-as-rtmp-stream?rq=1


In the accepted answer of the question you linked someone suggests using JavaCV.

It requires API 8 or newer and features a FFmpegFrameRecorder class.

Link to github:

https://github.com/bytedeco/javacv

They even have a full sample of capturing flv (it's rather large so I won't paste it here): 
https://github.com/bytedeco/javacv/blob/master/samples/RecordActivity.java

In your case you probably need to replace:

`private String ffmpeg_link = "/mnt/sdcard/stream.flv";`

with

`private String ffmpeg_link = "rtmp://<server>:<port>/stream";`

