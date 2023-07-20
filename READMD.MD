```sh

ffmpeg -hwaccels

ffmpeg -decoders | grep -i 'h264'

ffmpeg -encoders | grep -i 'h264'

ffmpeg -codecs

ffmpeg -y -vsync 0 -hwaccel cuda -hwaccel_output_format cuda -i input.mp4 -c:a copy -c:v h264_nvenc -b:v 5M output.mp4

ffmpeg -i input.mp4 -c:a copy -c:v libx264 -b:v 5M output1.mp4

ffprobe -show_format -show_streams -of json input.mp4

```
https://github.com/JackeyLea/ffmpeg_beginner/blob/0565f85644dc8d216985d5efb0343cd657309a2f/11.3.video_decode_by_cuda_display_by_qml/ffmpegdecoder.cpp