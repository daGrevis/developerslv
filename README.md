# #developerslv

#developerslv is a IRC channel on [Freenode network](https://freenode.net/)

Topic is about software and hacking in Latvian/English. The chat is public and
its history can be found on [developers.lv](https://developers.lv).  History
tracking works thanks to [msks bot](https://github.com/daGrevis/msks), one of
many bots on this channel. New bots are encouraged, make your own!

## Bots

* **msks** (JavaScript)
* **vdk** (JavaScript)
* **obql** (JavaScript)
* **zn** (Haskell)
* **Xn** (Haskell)
* **snbt** (Ruby)
* **agni** (C)

## Bot Spec

Bot should respond to:

* `!command`
* `,command`
* `nick, command`
* `nick: command`

...where `command` is command name like `ping` and `nick` is bot nick like
`msks`.

If it's a PM, bot should respond also on bare `command`. This makes `!botcast`
possible, a feature of `zn` bot.

### !ping

Responds with `pong`.

### !echo

On `!echo foobar` responds with `foobar`.

Doesn't respond on `!echo` or `!echo<Space>`.

### !version

Responds with current version in free-form text.

Consider showing at least few of these:

* Version number
* Commit ID, tag
* Commit/build message
* Build time
* Project link

### !uptime

Responds with elapsed time since successful connection.

For example, `!echo uptime` might return `4d 3h 2m 1s` which means that bot
connected 4 days, 3 hours, 2 minutes and 1 second ago.

| Duration    | Seconds            |
| ----------- |:-------------------|
| s (second)  | 1
| m (minute)  | 60
| h (hour)    | 60 * 60
| d (day)     | 60 * 60 * 24
| y (year)    | 60 * 60 * 24 * 365 |

Larger durations are preferred so respond with `1h 2m 3s` instead of `3723s` or
`62m 3s`.

Empty durations should be omitted so respond with `1h 2s` instead of `0y 1h 0m
2s`.
