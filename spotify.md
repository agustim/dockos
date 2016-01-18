## Dockerfile
  
  
  
## Build

## Run
```
docker run -it -v /etc/localtime:/etc/localtime -v /tmp/.X11-unix:/tmp/.X11-unix \
               -e QT_X11_NO_MITSHM=1 -e DISPLAY=$DISPLAY -e PULSE_SERVER=pulseaudio \
               --device /dev/snd --device /dev/video0\
               --link pulseaudio:pulseaudio -v /home/spotify:$HOME
```
