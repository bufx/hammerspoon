- ### Straightforward Method (suitable for test purpose or temporary tasks)

Open the Terminal and run:

``` shell
aria2c --enable-rpc --rpc-listen-all rpc-allow-origin-all=true rpc-secret=token
```

The disadvantage: you have to run this again and again, and don't even think about killing the process before the download is completed. :(

- ### "Complicated" Method (config once and forget about it 🎉)

1. Create your aria2 config file `~/.config/aria2/aria2.conf` which at least contains the lines below:

``` config
enable-rpc=true
rpc-listen-all=true
rpc-allow-origin-all=true
rpc-secret=token
```

2. Download [this file](https://gist.github.com/be5ac74620cfd52d9429041fa4e91e21), put it into `~/Library/LaunchAgents/`.

3. Restart your computer or run `launchctl load ~/Library/LaunchAgents/com.github.aria2.plist`.