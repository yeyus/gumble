### This is a fork of [layeh.com/gumble](https://github.com/layeh/gumble)

<img src="misc/gumble.svg" width="200" align="right">

# gumble

gumble is a [Mumble](https://mumble.info/) client implementation in Go

## Sub-projects

- gumble ([docs](https://pkg.go.dev/github.com/yeyus/gumble/gumble))
    - Client library
- gumbleopenal ([docs](https://pkg.go.dev/github.com/yeyus/gumble/gumbleopenal))
    - [OpenAL](http://kcat.strangesoft.net/openal.html) audio system for gumble
- gumbleffmpeg ([docs](https://pkg.go.dev/github.com/yeyus/gumble/gumbleffmpeg))
    - [ffmpeg](https://www.ffmpeg.org/) audio source for gumble
- gumbleutil ([docs](https://pkg.go.dev/github.com/yeyus/gumble/gumbleutil))
    - Extras that can make working with gumble easier

## Example

```go
package main

import (
  "github.com/yeyus/gumble/gumble"
  "github.com/yeyus/gumble/gumbleutil"
)

func main() {
  gumbleutil.Main(gumbleutil.Listener{
    UserChange: func(e *gumble.UserChangeEvent) {
      if e.Type.Has(gumble.UserChangeConnected) {
        e.User.Send("Welcome to the server, " + e.User.Name + "!")
      }
    },
  })
}
```

## Related projects

- [barnard](https://layeh.com/barnard)
    - terminal-based Mumble client
- [piepan](https://layeh.com/piepan)
    - an easy to use framework for writing Mumble bots using Lua

## License

MPL 2.0

## Author

Tim Cooper (<tim.cooper@layeh.com>)
