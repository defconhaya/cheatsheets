FFMPEG 

**Basic Multimedia Conversion:**

- Convert a video to another format:
  ```
  ffmpeg -i input.mp4 output.avi
  ```

- Convert an audio file to a different format:
  ```
  ffmpeg -i input.mp3 output.wav
  ```

**Video and Audio Streams:**

- Extract audio from a video:
  ```
  ffmpeg -i input.mp4 -vn output.mp3
  ```

- Extract a specific audio stream from a video with multiple audio streams:
  ```
  ffmpeg -i input.mp4 -map a:1 output.mp3
  ```

- Extract a specific video stream from a video with multiple video streams:
  ```
  ffmpeg -i input.mp4 -map v:0 output.mp4
  ```

**Video and Audio Manipulation:**

- Trim a video (start and end times in HH:MM:SS format):
  ```
  ffmpeg -i input.mp4 -ss 00:00:10 -to 00:01:30 -c:v copy -c:a copy output.mp4
  ```

- Adjust the volume of an audio file:
  ```
  ffmpeg -i input.mp3 -filter:a "volume=2.0" output.mp3
  ```

- Resize a video:
  ```
  ffmpeg -i input.mp4 -vf "scale=1280:720" output.mp4
  ```

**Concatenate Multimedia Files:**

- Concatenate multiple video files:
  ```
  ffmpeg -f concat -safe 0 -i filelist.txt -c copy output.mp4
  ```

- Create `filelist.txt` with a list of input file paths.

**Recording Your Screen:**

- Record your screen with audio (using x11grab):
  ```
  ffmpeg -f x11grab -framerate 30 -video_size 1920x1080 -i :0.0 -f pulse -ac 2 -i default output.mkv
  ```

**Transcoding with Specific Codecs:**

- Convert a video to H.264 format with AAC audio:
  ```
  ffmpeg -i input.mp4 -c:v libx264 -c:a aac output.mp4
  ```

**Adding Watermark:**

- Add a watermark image to a video:
  ```
  ffmpeg -i input.mp4 -i watermark.png -filter_complex "overlay=10:10" output.mp4
  ```

**Extract Frames as Images:**

- Extract frames as images at a specified interval (e.g., 1 frame per second):
  ```
  ffmpeg -i input.mp4 -vf "fps=1" image%d.png
  ```

**Creating GIFs:**

- Create a GIF from a video:
  ```
  ffmpeg -i input.mp4 -vf "fps=10,scale=320:-1:flags=lanczos" output.gif
  ```

**Subtitles Manipulation:**

- Add external subtitles to a video:
  ```
  ffmpeg -i input.mp4 -i input.srt -c:v copy -c:a copy -c:s mov_text -map 0 -map 1 output.mp4
  ```

- Extract subtitles from a video to an external subtitle file:
  ```
  ffmpeg -i input.mp4 -map 0:s:0 output.srt
  ```

- Burn subtitles onto a video, rendering them as part of the video stream:
  ```
  ffmpeg -i input.mp4 -vf "subtitles=input.srt" -c:v libx264 -c:a copy output.mp4
  ```

- Convert subtitle format from SubRip (SRT) to WebVTT:
  ```
  ffmpeg -i input.srt output.vtt
  ```

- Delay subtitles by 5 seconds:
  ```
  ffmpeg -i input.mp4 -vf "subtitles=input.srt:delay=5" -c:v libx264 -c:a copy output.mp4
  ```

- Change subtitle font and size:
  ```
  ffmpeg -i input.mp4 -vf "subtitles=input.srt:force_style='FontName=Arial,FontSize=24'" -c:v libx264 -c:a copy output.mp4
  ```

- Remove subtitles from a video:
  ```
  ffmpeg -i input.mp4 -c copy -map 0 -map -0:s output.mp4
  ```
