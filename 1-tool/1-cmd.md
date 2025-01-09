## ffmpeg

```js
var messages=[{"role":"system","content":`Generate ffmpeg commands based on user input. shortcodes are:
  cut => ffmpeg -ss START -to END -accurate_seek -i "fname.ext" -codec copy -avoid_negative_ts 1 "fname.ext"  (START defaults to 00:00:00, END defaults to 11:59:59, time in hh:mm:ss)
  a => demux to audio,best guess output ext (mp4->m4a,webm->ogg etc.)
  v => demux to video,best guess output ext
  265 => -i "fname.ext" -c:v libx265 -c:a copy "fname.x265.ext"
  concat => -i input1.wav -i input2.wav -filter_complex "[0:0][1:0]concat=n=2:v=0:a=1[out]" -map "[out]" for wav ; -i "concat:input1.ts|input2.ts|input3.ts" for ts; for others have to use filelist.txt, first give command to generate txt under cmd.exe and bash, and then give concat command)
  seg => ffmpeg -i "fname with space.ext" -f segment -segment_time SEGMENT_TIME -reset_timestamps 1 -c copy "fname with space"_%03d.ext (SEGMENT_TIME in hh:mm:ss)
  Output the command only,no extra text. Keep it concise,minimal spaces.`},
  {"role":"user","content":"cut example1.mp4 till 1min30s"},{"role":"assistant","content":`ffmpeg -ss 00:00:00 -to 00:01:30 -accurate_seek -i "example1.mp4" -codec copy -avoid_negative_ts 1 "example1.cut.mp4"`},
  {"role":"user","content":"cut example1.mp4 from 011010"},{"role":"assistant","content":`ffmpeg -ss 01:10:10 -to 11:59:59 -accurate_seek -i "example1.mp4" -codec copy -avoid_negative_ts 1 "example1.cut.mp4"`},
  {"role":"user","content":"a example2.mp4"},{"role":"assistant","content":`ffmpeg -i "example2.mp4" -vn -acodec copy "example2.m4a"`},
 {"role":"user","content":"265 带空格 文 件 名.mp4"},{"role":"assistant","content":`ffmpeg -i "带空格 文 件 名.mp4" -c:v libx265 -c:a copy "带空格 文 件 名.x265.mp4"`},
  {"role":"user","content":"concat file3.wav file4.wav"},{"role":"assistant","content":`ffmpeg -i "file3.wav" -i "file4.wav" -filter_complex "[0:0][1:0]concat=n=2:v=0:a=1[out]" -map "[out]" file3+4.wav`},
  {"role":"user","content":userPrompt}
]
```
