# YouTube Transcript API

Heavily inspired by the excellent Python library: https://github.com/jdepoix/youtube-transcript-api

## Installation
```bash
go get github.com/dougbarrett/youtube-transcript
```

## Usage
```go
package main

import (
    "log"
    "context"

    "github.com/dougbarrett/youtube-transcript"
)

func main() {
    videoID := "VIDEO_ID"
    transcript, err := youtubetranscript.GetTranscript(context.Context(), videoID)

    if err != nil {
        panic(err)
    }

    log.Printf("%v", transcript)
}
```

### Fetching Transcripts in Other Languages
```go
package main

import (
    "context"
    "log"

    "github.com/dougbarrett/youtube-transcript"
)

func main() {
    videoID := "VIDEO_ID"
    opts := []youtubetranscript.Option{
        youtubetranscript.WithLang("TARGET_LANGUAGE"),
    }
    transcript, err := youtubetranscript.GetTranscriptWithOpts(context.Background(), videoID, opts...)

    if err != nil {
        panic(err)
    }

    log.Printf("%v", transcript)
}

```
