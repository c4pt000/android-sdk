# docker-android-sdk based off of fedora:34
android-sdk portable
java 1.8.0

requires docker and kvm enabled in host
set xhost before running, run as root
```
xhost SI:localuser:root
```
regular run
```
docker run -it -d --privileged --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix \
-v /dev/kvm:/dev/kvm --device /dev/snd c4pt/docker-androidsdk
```
```
docker run -it -d --privileged --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix \
-v /dev/kvm:/dev/kvm --device /dev/snd c4pt/docker-androidsdk

54699552e879d8950e51d31b3889997c60ab10569eb47a18bc60c1c407fd11f2

┌─[root@fedora]─
└──╼ #docker exec -it 546 bash
```

to run with a source directory attached

```
docker run -it -d --privileged --rm -e DISPLAY=$DISPLAY -v /opt/SRCTEMP:/opt/SRCTEMP \
-v /tmp/.X11-unix:/tmp/.X11-unix -v /dev/kvm:/dev/kvm --device /dev/snd c4pt/docker-androidsdk
```

to run the emulator
```
to run the emulator

emulator @test64 &

or

emulator @test64 -read-only &
```
to create other emulators
```
to create other emulators
sdkmanager  "system-images;android-29;google_apis;x86_64"
sdkmanager --licenses
avdmanager create avd -n test64 -k "system-images;android-29;google_apis;x86_64"
```
to install apk to emulator
```
adb install path_to_apk
```

to sign an APK
```
key-sign-apk 
```
