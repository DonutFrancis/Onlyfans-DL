# OnlyFans Profile Downloader/Archiver
This tool downloads all photos/videos from an OnlyFans profile, creating a local archive.
You must be subscribed to the profile to download their content.

onlyfans-dl will create a directory called `profiles` in the repo directory. 
Each profile you download will be stored as a subdirectory of `profiles`.
Inside each profile directory, some information will be saved in `info.json`,
and all media will be downloaded to `photos/` and `videos/`.

LOOK: `python -m pip install requests`

If you have installed requests and it still doesn't work, then this is an issue with your local environment, not onlyfans-dl.

## Usage
First make sure to set your session variables in auth.json first.

`./onlyfans-dl.py`

## Session Variables
Requests to the API need to be signed. This is an obfuscation technique from the developers to discourage scraping.

You need your browser's __user-agent__, onlyfans **sess**ion cookie, __x-bc__ HTTP header, and **user-id**. Here's how to get them

- Get your user-agent
- Session Cookie
  - Login to OnlyFans as normal
  - Open the dev console Storage Inspector (`SHIFT+F9` on FireFox). or the __Application__ tab of Chrome DevTools
  - Click Cookies -> https://onlyfans.com
  - Copy the value of the `sess` cookie
- x-bc and user-id
  - Login to OnlyFans, goto home page
  - Open dev console `F12` -> Network tab (`Ctrl+Shift+E` in FireFox)
  - Click __Headers__ sub-tab (default)
  - Click on one of the JSON elements (may need to refresh page) and look under __request headers__ on the right

There are variables for each of these values at the top of the script. Make sure to update them every time you login or your browser updates.

## Contributing

PRs are welcome; be sure to take some time to familiarize yourself with OnlyFans' API if
you would like to extend/modify the functionality of this script.
