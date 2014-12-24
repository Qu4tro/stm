stm
===

Steam CLI Wrapper to browse and launch installed steam games. Inspired by [Steam-Browser](https://github.com/hunteriam/Steam-Browser)

If it is desired and people want it, support for other app properties can be added (such as file size or other intricacies.) Although until then, this is what it is!

```
usage: stm [-h] [--steamapps STEAMAPPS] {list,launch,appid} ...

positional arguments:
  {list,launch,appid}
    list                list installed steam games
    launch              launch game using steam
    appid               get appid of a game

optional arguments:
  -h, --help            show this help message and exit
  --steamapps STEAMAPPS
                        location of steamapps folder
```

This is a small example of its use:

```bash
stm list # List installed games
stm launch VVVVVV # Launch game
stm appid "The Binding of Isaac: Rebirth" # Returns id of the game
```

You can use the `--steamapps` argument to specify the location of the steamapps folder. It assumes that it's at `$HOME/.local/share/Steam/steamapps`.

As a bonus here's a one line to launch steam games with dmenu:

```bash
stm launch "$(stm list | dmenu -p "Pick your game:")"
```
