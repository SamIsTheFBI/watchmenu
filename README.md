# watchmenu
A little dmenu script to watch your very legally downloaded and owned TV shows, movies and anime in style. This script lists all your media in an organized manner using dmenu, trying to mimic a media library kind of aesthetic but in a suckless way :)

## Dependencies
- dmenu
- mpv
- awk
- Your legally downloaded media

## Directory Structure

You are supposed to use the directory structure that Plex, Jellyfin and such media servers understand. So, the following should suffice:

![image](https://user-images.githubusercontent.com/70562711/171038983-d9c07095-d3fa-4fa6-957e-f681c3b653f9.png)

## Usage
Run the script and your dmenu should pop up. I will be referring to these as different menu. So when dmenu prompt reads "Search", consider it the Search menu. I'll use the same analogy throughout this readme.

Upon running the script, you will be greeted with the Search menu. Here you can either press `Enter key` to list all your TV shows & movies or type a `search term` to search for in your media directories.

Pressing `Escape key` inside Episode menu (season directory) will start mpv with that directory as playlist. This will also save your watch progress and I think that's cool.You can do the same to watch all episodes of a show as playlist if you press Escape twice in Season menu. 

A few commands for simple navigation:
- `:s`    : Go to Search menu
- `:q`    : Quit dmenu
- `:b`    : Go back to previous menu
- `:h`    : Help screen which only works in Search menu

A demo video [here](https://0x0.st/oBpx.mp4).

## Purpose behind making this
In my honest opinion, the UI for Plex on Linux sucks. There is a subtle difference in the appearance between Windows and Linux versions, and that annoys me way more than it should. True I could open a browser and Plex would still look same as Windows' version but that's such a sucky way. Shouldn't I be using other media servers then? Jellyfin's UI is clanky as ever, Kodi can't properly arrange Monogatari seasons, and I don't want to use Docker. I tried out [dmenufm](https://github.com/huijunchen9260/dmenufm), it's cool and all but navigation was a hassle

Hence this script. Simple script that just does the work.
