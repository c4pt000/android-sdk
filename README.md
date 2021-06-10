# android-sdk
android-sdk portable
java 1.8.0

requires docker and kvm enabled in host
set xhost before running, run as root
```
xhost SI:localuser:root
```

```
docker run -it -d --privileged --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -v /dev/kvm:/dev/kvm --device /dev/snd c4pt/docker-androidsdk
```
