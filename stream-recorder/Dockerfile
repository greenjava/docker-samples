FROM ubuntu:18.04

RUN apt-get update && apt-get install -y vlc sudo ffmpeg \
    && rm -rf /var/lib/apt/lists/*

RUN useradd -m docker && echo "docker:docker" | chpasswd && adduser docker sudo

USER docker
RUN mkdir /home/docker/output

VOLUME /home/docker/output
WORKDIR /home/docker/output

#ENTRYPOINT  ["ffmpeg"]
#CMD [ \
#    "-i", "rtsp://184.72.239.149/vod/mp4:BigBuckBunny_175k.mov", \
#    "-vcodec", "copy", \
#    "-acodec", "copy",  \
#    "-map",  "0",  \
#    "-f", "segment",  \
#    "-segment_time", "30", \
#    "-segment_format", "mp4",  \
#    "capture-%03d.mp4" \
#    ]

ENTRYPOINT  ["cvlc", "-vvv", "--sout=#transcode:duplicate{dst=file{dst=video.mp4}}"]
CMD [ "rtsp://184.72.239.149/vod/mp4:BigBuckBunny_175k.mov" ]
