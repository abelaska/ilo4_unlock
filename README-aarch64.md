# Build on ARM MacOS

```shell
rm -rf ./build
docker build --platform linux/amd64 -o build .
```

Copy content of `./build` directory to a USB stick. And then execute this sequence on the server:

```shell
sudo modprobe -r hpilo
cd flash
sudo ./flash_ilo4 --direct
# wait until the fans spin down ...
sudo shutdown now # remove power and disable the security override after shutting down!
```
