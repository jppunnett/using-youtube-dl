# Using [youtube-dl](https://github.com/ytdl-org/youtube-dl)

## Download a playlist or single video and save only the audio portion

      youtube-dl --extract-audio --audio-format mp3 -o "%(title)s.%(ext)s" <playlist/video URL>
  
Where,
* `--extract-audio` means to extract only the audio portion of a video
* `--audio-format mp3` means the audio file should be the MP3 format
* `-o` means the file name for the audio file should be `title.ext`, where `title` is the name of the video and `ext` is the file extension of the audio format, in this case, `mp3`
* `<playlist/video URL>` is the a URL to the playlist or single video. E.g. `https://www.youtube.com/playlist?list=PLICkMuP20RMw7BHRtBjTXFmlo-CnJQ8vP` is a playlist URL, while `https://youtu.be/AXUI6d8hZwA` is a single video URL. 

## Download only new items in a playlist

When you download the playlist (like the example above), tell youtube-dl to create a text file containing the current list of items in the playlist.

      youtube-dl --download-archive archive.txt --extract-audio --audio-format mp3 -o "%(title)s.%(ext)s" <playlist URL>

The next time you run the same command to download the playlist again, youtube-dl will only download the new items in the playlist and update the archive.txt file.
