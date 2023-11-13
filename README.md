<h1 align="center">watchmenu</h1>

<div align="center">
  <em>A POSIX script that organizes all of your movies and TV shows, making it easy to find & watch your media collection.</em>
</div>

<div align="center">
<br>

https://github.com/SamIsTheFBI/watchmenu/assets/70562711/306ace0e-22d9-4a24-8bd1-37a4808a706d

</div>

Get a dmenu list of your media collection in a very organized way, making it hassle-free to find and watch your favorite TV shows & movies. You can also search YouTube videos (using API) and play them using mpv. All of this achieved using a simple bash script!

## Table of contents

- [Dependencies](#dependencies)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Purpose behind making this](#purpose-behind-making-this)
- [Credits](#credits)

## Dependencies

- dmenu/rofi/fzf
- mpv
- awk
- grep
- yt-dlp
- your media library
- your YouTube API key (for searching YouTube videos/playlist)

## Installation

- Copy `watchmenu` to your desired bin directory. Make it executable by running `sudo chmod a+rx`. Make sure to update PATH variable if required.

- Copy `watchmenu.conf` to `~/.config/watchmenu/` directory. It should be created upon running `watchmenu`.

## Usage

Run the script by typing `watchmenu` in your terminal and dmenu or your preferred prompt should pop up. You can also bind this to a keyboard shortcut to make it more convenient.

Upon running the script, you will be greeted with the Search menu. You can select any of the categories (TV Shows/Anime/Movies) or search the media directly.

| Keys/Commands     | What it will do                                                  |
|-------------------|------------------------------------------------------------------|
| `:s`              | Go to Search menu                                                |
| `:q`              | Quit watchmenu                                                   |
| `:b`              | Go back to previous menu                                         |
| `:h`              | Help screen which only works in Search menu                      |
| `Shift` + `Enter` | Ignore the selection and search for the term you typed (dmenu) (depends on what you set when building dmenu from source)   |
| `Ctrl` + `Enter`  | Ignore the selection and search for the term you typed (rofi)    |
| `Alt` + `Enter`   | Ignore the selection and search for the term you typed (fzf)     |

## Configuration

All the configurations are stored in `watchmenu.conf` file. After installation, it will be present at `~/.config/watchmenu/`. It holds configurations for user-preferred prompt (dmenu/fzf/rofi), video player to be used, YouTube API key and so on. You can view the sample config file [here](https://github.com/SamIsTheFBI/watchmenu/blob/main/watchmenu.conf).

### Directory Structure

You can add your media directories to respective arrays in the script. Follow the directory structure that Plex, Jellyfin and such media servers understand. So, the following should suffice:

<div align="center">
<br>
  
  ![image](https://github.com/SamIsTheFBI/watchmenu/assets/70562711/25dd454a-f0d9-433e-8865-a5f04af20db8)

</div>

### For YouTube Video & Playlist Search feature

Copy your YouTube API key and paste it in a file `${HOME}/.api_keys/YT_API_KEY` or set it as the value of `YT_API_KEY` in the config file. Check this [tutorial](https://elfsight.com/blog/2016/12/how-to-get-youtube-api-key-tutorial/) on how to get your own YouTube API key.

With this you should be able to search YouTube videos/playlists and play them using watchmenu.

<em>
Note: Some YouTube playlists may not work unless you choose to extract video links from it. And hence, there is a prompt when playing a YouTube playlist, asking the user to either extract video links or continue without doing so.
</em>

## Purpose behind making this

In my honest opinion, the UI for Plex on Linux sucks. There is a subtle difference in the appearance between Windows and Linux versions, and that annoys me way more than it should. True I could open a browser and Plex would still look same as Windows' version but that's such a sucky way. Shouldn't I be using other media servers then? Jellyfin's UI is clanky as ever, Kodi can't properly arrange Monogatari seasons, I don't want to use Docker and furthermore, they all are heavy on my laptop and take up a lot of space which I could've used for more movies. I tried out [dmenufm](https://github.com/huijunchen9260/dmenufm), it's cool and all but navigation was a hassle.

Hence this script that just does the work. Also, bash scripting kinda fun. Just look at [fff](https://github.com/dylanaraps/fff).

## Credits

- Thanks to [reo101](https://github.com/reo101) for refactoring the code & making the script much more readable!
- [Bugswriter](https://github.com/Bugswriter), his [myyt](https://github.com/Bugswriter/myyt) script was modified & used for the YouTube video search feature. 

