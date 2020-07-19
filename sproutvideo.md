# Downloading from Sproutvideo

## Introduction 

A semi-complicated guide on how to download videos from Sproutvideo.  
While I say this guide works on Windows, Mac and Linux, I have only tried it on Linux.  
In theory, as long as you do things correctly, it should work fine on Windows as well.

Keep in mind that this guide is written on July 19th, 2020.  
If you're here months later, then I can't guarantee that this method still works, though I'll try to keep it updated.

## Table of Contents

- [Downloading from Sproutvideo](#downloading-from-sproutvideo)
  - [Introduction](#introduction)
  - [Table of Contents](#table-of-contents)
  - [Requirements](#requirements)
  - [Prerequisites](#prerequisites)
    - [User Agent](#user-agent)
    - [Userscript](#userscript)
  - [1. Getting the version of youtube-dl we need](#1-getting-the-version-of-youtube-dl-we-need)
  - [2. Testing if the project works (at all)](#2-testing-if-the-project-works-at-all)
  - [3. Downloading a video from Sproutvideo](#3-downloading-a-video-from-sproutvideo)
  - [4. Downloading multiple videos (via text file)](#4-downloading-multiple-videos-via-text-file)
  - [5. Edge cases: 403 Forbidden (Referer)](#5-edge-cases-403-forbidden-referer)
  - [Finale](#finale)

## Requirements

- A computer (Windows, Mac, Linux). This doesn't work on iOS or Android.
- The ability to Google for both guides and troubleshooting is helpful.
    - At least for installation of Git, Python and so on. I won't hold your hand there, as that's "out of scope" for this guide.
- Familiarity with a CLI (Command Line Interface) is handy.
    - Basic understanding of `PATH`, directories etc. would help immensely.
- [Git][Git-SCM] - For downloading the Git repository from GitHub.
    - If you use some sort of package manager (Linux especially), you most likely can use that to install Git.
    - DigitalOcean has a nice community tutorial for installing Git that covers multiple platforms: [Check it out here][Git-Install-DO]
- [Python][Python-DL]
    - I've tested with both Python 3.8.4 and Python 2.7.17 and it seems to work with both, but I only tested 3.8.4 on two videos, so keep that in mind.
    - If you don't have either of those installed, get Python 3.8.x (whatever is the latest), as Python 2.7.x is no longer supported.
    - Linux: Ubuntu-based (Debian-based too?) distros often come with Python 2.7.x pre-installed, which should work.
    - Windows: Just use the "executable" installer. I recommend the 64-bit (`x86-64`) installer if you're on a 64-bit system.
        - **Make sure to check "Add to PATH"**: [Screenshot][Python-Path-SS]
- [FFmpeg](https://ffmpeg.org/)
    - FFmpeg is used for video processing. I'm not entirely sure if this is necessary, but it probably is.
- A userscript manager for your web browser, such as [Violentmonkey][Violentmonkey], Tampermonkey, Greasemonkey etc.
    - Mainly used for installing a script that will display the "embed URL" that we need to use when downloading shit.
- A Sproutvideo link (typically `https://blah-blah.vids.io/videos/b6f0479ae87d244975439c6124592772/some-video-title`).
    - It's from this page we'll be getting the "Embed URL".

## Prerequisites

### User Agent
Here's your browser's user agent, which we will use later.

<input disabled="1" type="text" id="user-agent" />
<button type="button" id="ua-copy">Copy to clipboard</button>

### Userscript

Once you have a userscript manager installed in your browser, visit this [gist URL][Sprout-Embed-URL-US] and click "Raw". Your userscript manager should prompt you to install the script.  
The script is useful for displaying the "embed URL", which we will use to get the correct URL for download. It's possible to get this URL with other methods, but this makes it easier (especially if you're downloading multiple videos).

## 1. Getting the version of youtube-dl we need

You might be familiar with `youtube-dl`, which is an extremely powerful tool for downloading media from all kinds of different websites.  
Unfortunately the version we need is a 'fork', because someone has started implementing support for Sproutvideo, but it hasn't been included in the main version yet.

All the credit for the Sproutvideo support should go to [TheZ3ro on GitHub](https://github.com/TheZ3ro).

**If you haven't installed Git yet, do so now.**

1. Open a Terminal/Command Prompt window.
2. Create a directory, such as:
   1. Windows: `md C:\Projects`
   2. Linux/Mac: `mkdir -p ~/projects`
   3. These directories are examples, but I'll be using them throughout the guide. If you don't know what you're doing, you should probably not change it from the examples.
3. Navigate to the directory you just made:
   1. Windows: `cd C:\Projects`
   2. Linux/Mac: `cd ~/projects`
4. "Clone" the youtube-dl Git repo from TheZ3ro's GitHub page:
   1. `git clone https://github.com/TheZ3ro/youtube-dl.git ytdl-sprout`
   2. Using the command above will clone it into a `ytdl-sprout` directory, which will automatically be created.
5. Navigate into the Git repo's folder:
   1. Windows/Linux/Mac: `cd ytdl-sprout`
6. Checkout the correct Git branch:
   1. Windows/Linux/Mac: `git checkout sproutvideo`

## 2. Testing if the project works (at all)

Before we move on, we need to make sure that both Python and our project works at all.  
Python is absolutely necessary for youtube-dl to function, so let's test that first.

**If you haven't installed Python at this point, do so now.**  
During Python installation, make sure that `Add to PATH` (or similar working) is **checked/included** (at least the Windows installer has this, [see screenshot][Python-Path-SS]).  
After Python installation, close and reopen your Terminal/Command Prompt windows and navigate back to the project folder (Windows: `cd C:\Projects\ytdl-sprout` or Linux/Mac: `cd ~/projects/ytdl-sprout`).  
I highly recommend following a guide for installation for your operating system, unless you know what you're doing.

1. Check that Python is working by running: `python --version`
   1. It should output something like: `Python 3.x.x` or `Python 2.x.x` - nothing more.
2. Check that the version of youtube-dl works by running: `python youtube_dl/__main__.py --version`
   1. It should output a version number/date: `2020.xx.xx`.
   2. At the time of writing it's: `2020.03.24`
3. If neither of these gave you any weird error, we can assume they 'work' and move on.

## 3. Downloading a video from Sproutvideo

It's possible to download a list of videos in one command, but for testing purposes let's just test with one video.

1. Visit the URL of the video you want to do download, typically looks like: `https://blah-blah.vids.io/videos/b6f0479ae87d244975439c6124592772/some-video-title`
2. Type in the password to get to the page with the _video player_
   1. Page with the video player should look like [this screenshot][Sprout-Video-Player-SS].
3. Right-click on the 'Embed URL' and copy it to your clipboard.
4. Now go back to your Terminal / Command Prompt and write the following command:
   1. `python youtube_dl/__main__.py --add-header "User-Agent: <Your User Agent>" "<Embed URL>"`
   2. `<Your User Agent>` should be replaced with your actual user agent (which you can get from the beginning of this page).
   3. `<Embed URL>` should be replaced with the embed URL you just copied from the video player.
   4. **Full example**: `python youtube_dl/__main__.py --add-header "User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0" "https://videos.sproutvideo.com/embed/9c12db1a048ed3c5/b2060375b95276c1?type=hd"`
5. Run the command with the correct values replaced.
6. If everything is working correctly, it should start downloading the video and eventually complete.

## 4. Downloading multiple videos (via text file)

Downloading multiple videos is not that much harder than downloading one video, but it is a bit more tedious, because you'll still have to get the "Embed URL" of each video.

1. Create a text file using Notepad, call it something like `sprout.txt`. Save it as an empty text file for now.
   1. Make sure to save it inside the `ytdl-sprout` folder.
2. Get the "Embed URL" as explained in [part 1-3 in chapter #3](#3-downloading-a-video-from-sproutvideo).
3. Paste it into the `sprout.txt` text file using Notepad.
4. Repeat this for all videos, but make sure to place **each embed URL onto its own line**.
5. Once you've pasted all the embed URLs into the `sprout.txt` text file, make sure to save it.
6. Run the following command to download all the URLs in the `sprout.txt` text file:
   1. `python youtube_dl/__main__.py --add-header "User-Agent: <Your User Agent>" -a sprout.txt`
   2. Note the `-a` before the `sprout.txt` filename.
   3. **Full example**: `python youtube_dl/__main__.py --add-header "User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0" -a sprout.txt`
7. The download should start. This will take a while, as it only downloads one video at a time.

## 5. Edge cases: 403 Forbidden (Referer)

In some scenarios you may have videos that are give you a `403 Forbidden` error. These might only play if they are 'embedded' on the correct page.  
The easiest way to test if this is the case, open the embed URL in a new tab **by copy/pasting** (NOT clicking) and see if you get this error:

![Screenshot of referer error][Sprout-Referer-Error-SS]

If you have an error like this, the easiest is to include another flag with your command:  
`--referer https://blah-blah-blah.vids.io/` - where the `https://blah-blah-blah.vids.io/` is the original URL where you copied the embed URL from.  
Usually it's not necessary to include the full URL and you can do it similar to my example.

## Finale

And that's it! If everything has been done correctly (and the project isn't broken), then you now have a setup for downloading videos from Sproutvideo.  
As I mentioned in the [Introduction](#introduction), this works at the time of writing, but no guarantees that it will in the future.  
I'll _try my best_ to update this guide whenever necessary.

[Git-SCM]: https://git-scm.com/
[Git-Install-DO]: https://www.digitalocean.com/community/tutorials/how-to-contribute-to-open-source-getting-started-with-git
[Python-DL]: https://www.python.org/downloads/
[Python-Path-SS]: https://i.titty.stream/ss/2020-07-19_1wMAqC.png
[Sprout-Embed-URL-US]: https://gist.github.com/M-rcus/8bba3d654767a6bfc8b8d83f1abb2ae9
[Sprout-Referer-Error-SS]: https://i.titty.stream/ss/2020-07-19_Uv0IWg.png
[Sprout-Video-Player-SS]: https://i.titty.stream/ss/2020-07-19_sIDkvG.png
[Violentmonkey]: https://violentmonkey.github.io/

<script type="text/javascript">
    document.addEventListener('load', () => {
        /**
        * User Agent stuff
        */
       const uaInput = document.querySelector('#user-agent');
       uaInput.value = navigator.userAgent;

       const uaBtn = document.querySelector('#ua-copy');
       uaBtn.onclick = () => {
           uaInput.select();
           document.execCommand('copy');
       };
    });
</script>