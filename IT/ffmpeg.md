# FFMPEG

## Download

[ffmpeg.org](https://ffmpeg.org/)

### Tricks

On windows, you can add the path to `ffmpeg.exe` to your global PATH variable to use it as `ffmpeg`

## Compress a file

```sh
ffmpeg -i input.mp4 -preset veryslow OUTPUT_NAME.mp4
```

> Legend :
>
> - `-preset veryslow` is the level of compress, see [here](https://trac.ffmpeg.org/wiki/Encode/H.264#:~:text=ultrafast) for others presets

## Zoom in a video

```sh
ffmpeg -i input.mp4 -vf "scale=2*iw:-1, crop=iw/2:ih/2:0:400" OUTPUT_NAME.mp4
```

> Legend :
>
> - `scale` enlarge the video, and `crop` cut a part
> - `crop` parameters are width:height:x:y
> - here, it is a zoom of `2`

## Cut a video

```sh
ffmpeg -ss 00:01:00 -i input.mp4 -t 00:02:00 -c copy OUTPUT_NAME.mp4
```

> - `-i` :This specifies the input file. In that case, it is (input.mp4)
> - `ss` : Used with -i, this seeks in the input file (input.mp4) to position.
> - `00:01:00` : This is the time your trimmed video will start with.
> - `t` : This specifies duration from start (00:01:40) to end (00:02:12).
> - `00:02:00` : This is the time your trimmed video will end with.
> - `c copy` : This is an option to trim via stream copy. (NB: Very fast)

[StackOverflow](https://stackoverflow.com/questions/18444194/cutting-the-videos-based-on-start-and-end-time-using-ffmpeg#:~:text=Try%20using%20this.%20It%20is%20the%20fastest%20and%20best%20ffmpeg-way%20I%20have%20figure%20it%20out:)

> - ⚠️ `-t` specifies the duration !
> - The OUTPUT_NAME need to have the same extension as the input file (or ffmpeg will need to re-encode the video)

## Format a video for Da Vinci Resolve for Linux

- On linux, Da Vinci resolve can't use proprietary library, so you need to convert your file, for example in `DNxHD`:

```sh
ffmpeg -i input.mkv -c:v dnxhd -b:v 185M -c:a pcm_s16le output.mov
```

> - [https://en.wikipedia.org/wiki/Avid_DNxHD](https://en.wikipedia.org/wiki/Avid_DNxHD)

## Convert to ProRes

```sh
ffmpeg -i input.mp4 -c:v prores_ks -profile:v 3 -vendor apl0 -bits_per_mb 8000 -pix_fmt yuv422p10le output.mov
```

> - from [https://ottverse.com/ffmpeg-convert-to-apple-prores-422-4444-hq/](https://ottverse.com/ffmpeg-convert-to-apple-prores-422-4444-hq/)

## Extract audio from video

```sh
ffmpeg -i input.mp4 -vn -acodec copy output-audio.mp3
```

> - from <https://stackoverflow.com/a/27413824>
