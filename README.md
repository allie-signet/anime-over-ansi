# allie's ANSI anime experience - experiments branch
code to encode video into ANSI escape sequences, then play it back at the proper framerate and optionally with subtitles.

## note - this is the experiments branch!
the current experiment is adding multi-track container support to the output files.
the player currently does not support this and thus is broken in this branch, and the encoder is a work-in-progress.

## tips
```bash
# serve video over tcp
./target/release/player video.txt | nc -l 2323

# encoder syntax
./target/release/encoder \
--track=color:256,compression:zstd,width:192,height:108,name:eightbit \
--track=color:true,compression:zstd,width:192,height:108,name:colorful \
input.mkv out.ansi
```

### todos
- improve frame extraction
