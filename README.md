# WebRTC Capture Proof of Concept

This is a simple proof of concept of how a H264 stream can be captured by webrtc-rs and converted into a bitmap if the first packet contains a h264 frame (or something like that).

It does not work reliably because sometimes the first packet does not always contain the information needed but it should be enough to get started on a working solution.

The docs bellow are copy and pasted from the webrtc-rs example this is based on:

# save-to-disk-h264
save-to-disk-h264 is a simple application that shows how to record your webcam/microphone using WebRTC.rs and save H264 and Opus to disk.

## Instructions
### Build save-to-disk-h264
```
cargo build --example save-to-disk-h264
```

### Open save-to-disk example page
[jsfiddle.net](https://jsfiddle.net/vfmcg8rk/1/) you should see your Webcam, two text-areas and a 'Start Session' button

### Run save-to-disk-h264, with your browsers SessionDescription as stdin
In the jsfiddle the top textarea is your browser, copy that and:
#### Linux/macOS
Run `echo $BROWSER_SDP | ./target/debug/examples/save-to-disk-h264`
#### Windows
1. Paste the SessionDescription into a file.
1. Run `./target/debug/examples/save-to-disk-h264 < my_file`

### Input save-to-disk-h264's SessionDescription into your browser
Copy the text that `save-to-disk-h264` just emitted and copy into second text area

### Hit 'Start Session' in jsfiddle, wait, close jsfiddle, enjoy your video!
In the folder you ran `save-to-disk-h264` you should now have a file `output.h264` play with your video player of choice!

Congrats, you have used WebRTC.rs!
