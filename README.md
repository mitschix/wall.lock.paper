# Wallpaper Lockscreen Collection

These wallpapers and lockscreens are collected from a number of different places. Most of the wallpapers are from default wallpaper packages of Linux distributions or from other wallpaper repositorys. Some wallpaper as well as the lockscreens are from google pictures search results. Therefore I do not know if there is a copyright on these images. 

If you find an image hosted in this repository that is yours and of limited use, please let me know and I will remove it.

The majority of these wallpapers are nature and landscape photos. The lockscreens are mostly funny and nerdy jokes.

### Wallpaper/Lockscreen sources:
+ mostly [DitroTube's Wallpaper](https://gitlab.com/dwt1/wallpapers)
+ [Salient OS](https://salientos.github.io/)
+ some [Ubuntu OS](https://salientos.github.io/)
+ [Pop\! OS](https://pop.system76.com/)
+ Google pictures search results

##  i3 Tipps and Tricks
Since I use i3 there are some tricks I use to randomize the wallpapers and lockscreens to enjoy them as much as possible.

For the wallpaper I use **feh** in the *i3 config file* to set the wallpaper and change it every 5 minutes:
```
# exec --no-startup-id feh --bg-scale $bgpic
exec --no-startup-id /usr/bin/feh --no-fehbg --bg-scale --randomize -r $wallpaper_folder
exec --no-startup-id systemd-run --on-calendar="*:0/5" --user -- /usr/bin/feh --no-fehbg --bg-scale --randomize -r $wallpaper_folder
```
The path to the wallpaper folder is set with:
```
set $wallpaper_folder "path/to/wallpaper"
```

For the lockscreen I use the tool [Betterlockscreen](https://github.com/pavanjadhaw/betterlockscreen). With this tool it is possible to choose a random picture from a folder und to display it in different kinds like dimmed, black and white or blurred.
To use it as lockscreen and prepare a new picture after every lock the following command is used as i3lock:
```
set $i3lock betterlockscreen -l dim && betterlockscreen -u /path/to/lockscreens
```
(!buggy! Some times the script will not generate a new lockscreen or will not run proberly. It is also import to check how the lockscreen is called when used with *xautolock* or *xss-lock*.)
