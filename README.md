# watchmenu
A little dmenu script to watch your downloaded TV shows, movies and anime in style. This script lists all your media in an organized manner using dmenu (or rofi if you prefer), trying to mimic a media library kind of aesthetic but in a suckless way :)

## Dependencies
- dmenu/rofi/fzf
- mpv
- awk
- grep
- Your media library
- rclone (very optional) (for cloud access)

https://user-images.githubusercontent.com/70562711/179566428-4dc1dd8f-65ac-4c8b-a531-3849545fbb5a.mp4

## Usage

Run the script and dmenu should pop up. I will be referring to these as different menu. So when the prompt reads "Search", consider it the Search menu. I'll use the same analogy throughout this readme.

Upon running the script, you will be greeted with the Search menu. Here you can either press `Enter key` to list all your TV shows & movies or type a `search term` to search for in your media directories.

Pressing `Escape key` inside Episode menu (season directory) will start mpv with that directory as playlist. This will also save your watch progress and I think that's cool.You can do the same to watch all episodes of a show as playlist if you press Escape twice in Season menu. 

Note: You can set `WATCHMENU_PROMPT` in environment variables to change prompt to rofi or fzf. Same can be done with `VIDEO_PLAYER`.  

| Keys/Commands     | What it will do                                                  |
|-------------------|------------------------------------------------------------------|
| `:s`              | Go to Search menu                                                |
| `:q`              | Quit watchmenu                                                   |
| `:b`              | Go back to previous menu                                         |
| `:h`              | Help screen which only works in Search menu                      |
| `Shift` + `Enter` | Ignore the selection and search for the term you typed (dmenu)   |
| `Ctrl` + `Enter`  | Ignore the selection and search for the term you typed (rofi)    |
| `Alt` + `Enter`   | Ignore the selection and search for the term you typed (fzf)     |

## Directory Structure

You can add your media directories to respective arrays in the script.

You are supposed to use the directory structure that Plex, Jellyfin and such media servers understand. So, the following should suffice:

![image](https://user-images.githubusercontent.com/70562711/171038983-d9c07095-d3fa-4fa6-957e-f681c3b653f9.png)


## Purpose behind making this
In my honest opinion, the UI for Plex on Linux sucks. There is a subtle difference in the appearance between Windows and Linux versions, and that annoys me way more than it should. True I could open a browser and Plex would still look same as Windows' version but that's such a sucky way. Shouldn't I be using other media servers then? Jellyfin's UI is clanky as ever, Kodi can't properly arrange Monogatari seasons, I don't want to use Docker and furthermore, they all are heavy on my laptop and take up a lot of space which I could've used for more movies. I tried out [dmenufm](https://github.com/huijunchen9260/dmenufm), it's cool and all but navigation was a hassle.

Hence this script. Simple script that just does the work.
