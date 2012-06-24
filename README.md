Snipt CLI
=========

A Python-based CLI for working with the Snipt.net API.


## Requirements

    pip install clint requests

## Symlink

    ln -s snipt /usr/local/bin/snipt

## Configuration

Create a configuration file in your home directory named `.snipt` with your [Snipt.net](https://snipt.net) username and API key:

    [user]
    username=USERNAME
    api_key=API_KEY

## Post and get URL

Pipe some data to `snipt post_and_get_url`.

    echo 'Oh hai' | snipt post_and_get_url

With a specific [lexer](https://snipt.net/nick/list-of-lexers-for-use-with-the-snipt-api/):

    echo 'Oh hai' | snipt post_and_get_url python

I like to alias it like this:

    alias sp='snipt post_and_get_url'

...so it's nice and sweet:

    echo For real.|sp javascript|xargs open

(post a new `javascript` snipt and open it in a browser.)

## Vim shortcut

Select text in visual mode. Hit \<leader\>G. It'll post to Snipt, copy the returned URL, and open it in your browser.

    vnoremap <leader>G :w !snipt post_and_get_url \| pbcopy && pbpaste \| xargs open<CR>
