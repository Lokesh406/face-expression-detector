# IMPORTANT: Bug Fixes

## `navigator.getUserMedia`

The method `navigator.getUserMedia` has been deprecated and is no longer recommended for use.  
To maintain compatibility with modern browsers, **replace all occurrences** of `navigator.getUserMedia` with the modern alternative:  
`navigator.mediaDevices.getUserMedia`.

## Low-end Devices Bug

On low-performance machines (observed on Debian Firefox and Windows with Chrome/Firefox), the `play` event on the video element triggers **before the video is fully buffered**, causing Face API to throw errors and halt the script.  
To fix this, switch to the `playing` event, which fires **only when the media is ready to start playback** with sufficient data, ensuring stable Face API operation.
