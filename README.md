# zsh-url-highlighter

A plugin for [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
that turns URLs green if they respond with a "good"** status, and red otherwise.
Useful for checking URL typos.

## Installation

Clone this repo somewhere and then symlink the `url` directory into `[zsh-syntax-highlighting-dir]/highlighters/` like so:

```sh
$ git clone git@github.com:ascii-soup/zsh-url-highlighter.git ~/zsh-stuff/zsh-url-highlighter
$ ln -s ~/zsh-stuff/zsh-url-highlighter/url [zsh-syntax-highlighting-dir]/highlighters/url
```

Modify your `ZSH_HIGHLIGHT_HIGHLIGHTERS` array to add `url`:

```sh
# Specify which highlighters should be active
ZSH_HIGHLIGHT_HIGHLIGHTERS=(main brackets pattern url)
```
## Configuration

To change the highlight styles, you can use:
```sh
ZSH_HIGHLIGHT_STYLES[url-good]='fg=blue,bold'
ZSH_HIGHLIGHT_STYLES[url-bad]='fg=magenta,bold'
```

To change the timeout in curl from the default of 0.25s, you can use:
```sh
ZSH_HIGHLIGHT_URL_HIGHLIGHTER_TIMEOUT=4
```

## Dependencies

This requires curl to be installed and on your `$PATH`

** Currently this is only 200 - this will be configurable in the future
