# stream-recorder

## Build image

```bash
> docker build -t recorder:1.0 .
```

## Run image

```bash
> docker run --rm -v /myFolder/video:/home/docker/output/ recorder:1.0 rtsp://184.72.239.149/vod/mp4:BigBuckBunny_175k.mov
```
