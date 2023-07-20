```sh

ffmpeg -hwaccels

ffmpeg -decoders | grep -i 'h264'

ffmpeg -encoders | grep -i 'h264'

ffmpeg -codecs

ffmpeg -y -vsync 0 -hwaccel cuda -hwaccel_output_format cuda -i input.mp4 -c:a copy -c:v h264_nvenc -b:v 5M output.mp4

ffmpeg -i input.mp4 -c:a copy -c:v libx264 -b:v 5M output1.mp4

ffprobe -show_format -show_streams -of json input.mp4

```
