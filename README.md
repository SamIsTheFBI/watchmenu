# watchmenu 

A dmenu script to watch your downloaded TV shows, movies and anime in style. This bash script lists all your media in an organized manner using dmenu (or rofi or fzf whichever you prefer), trying to mimic a media library kind of aesthetic but in a suckless way :)

## Dependencies
- dmenu/rofi/fzf
- mpv
- awk
- grep
- yt-dlp
- your media library
- your YouTube API key (for searching YouTube videos/playlist)

https://user-images.githubusercontent.com/70562711/179566428-4dc1dd8f-65ac-4c8b-a531-3849545fbb5a.mp4

## Installation

- Copy `watchmenu` to your desired bin directory. Make it executable by running `sudo chmod a+rx`. Make sure to update PATH variable if required.

- Copy `watchmenu.conf` to `~/.config/watchmenu/` directory. It should be created upon running `watchmenu`.

## Usage

Run the script by typing `watchmenu` in your terminal and dmenu or your preferred prompt should pop up. I will be referring to these as different menu. So when the prompt reads "Search", consider it the Search menu. I'll use the same analogy throughout this readme.

Upon running the script, you will be greeted with the Search menu. Here you can either press `Enter key` to list all your TV shows & movies or type a `search term` to search for in your media directories.

Pressing `Escape key` inside Episode menu (season directory) will start mpv with that directory as playlist. This will also save your watch progress and I think that's cool.You can do the same to watch all episodes of a show as playlist if you press Escape twice in Season menu. 

You can set your media directories in `watchmenu.conf`. Put each path inside respective parentheses. The paths will not be recursively checked.

NOTE: `watchmenu.conf` holds configurations for preferred `WATCHMENU_PROMPT` like rofi or fzf or a whole dmenu command with parameters as per your build. Same can be done with `VIDEO_PLAYER` but keep it to mpv based video players.  

| Keys/Commands     | What it will do                                                  |
|-------------------|------------------------------------------------------------------|
| `:s`              | Go to Search menu                                                |
| `:q`              | Quit watchmenu                                                   |
| `:b`              | Go back to previous menu                                         |
| `:h`              | Help screen which only works in Search menu                      |
| `Shift` + `Enter` | Ignore the selection and search for the term you typed (dmenu) (depends on what you set when building dmenu from source)   |
| `Ctrl` + `Enter`  | Ignore the selection and search for the term you typed (rofi)    |
| `Alt` + `Enter`   | Ignore the selection and search for the term you typed (fzf)     |

## For YouTube Video & Playlist Search feature

Copy your YouTube API key and paste it in a file `${HOME}/.api_keys/YT_API_KEY` or set it as the value of `YT_API_KEY` in the config file. Check this [tutorial](https://elfsight.com/blog/2016/12/how-to-get-youtube-api-key-tutorial/) on how to get your own YouTube API key.

With this you should be able to search YouTube videos/playlists and play them using watchmenu.

**`Note:`** Some YouTube playlists may not work unless you choose to extract video links from it. And hence, there is a prompt when playing a YouTube playlist, asking the user to either extract video links or continue without doing so.

## Directory Structure

You can add your media directories to respective arrays in the script.

You are supposed to use the directory structure that Plex, Jellyfin and such media servers understand. So, the following should suffice:

![image](https://user-images.githubusercontent.com/70562711/171038983-d9c07095-d3fa-4fa6-957e-f681c3b653f9.png)

## Purpose behind making this

In my honest opinion, the UI for Plex on Linux sucks. There is a subtle difference in the appearance between Windows and Linux versions, and that annoys me way more than it should. True I could open a browser and Plex would still look same as Windows' version but that's such a sucky way. Shouldn't I be using other media servers then? Jellyfin's UI is clanky as ever, Kodi can't properly arrange Monogatari seasons, I don't want to use Docker and furthermore, they all are heavy on my laptop and take up a lot of space which I could've used for more movies. I tried out [dmenufm](https://github.com/huijunchen9260/dmenufm), it's cool and all but navigation was a hassle.

Hence this script that just does the work. Also, bash scripting kinda fun. Just look at [fff](https://github.com/dylanaraps/fff)

# Credits

- Thanks to [reo101](https://github.com/reo101) for refactoring the code & making the script much more readable!
- [Bugswriter](https://github.com/Bugswriter), his [myyt](https://github.com/Bugswriter/myyt) script was modified & used for the YouTube video search feature. 

