# gopassprompt

`gopassprompt` is a helper script to enable [iTerm2](https://iterm2.com/) integration with [gopass](https://github.com/gopasspw/gopass)

## Background

This project is inspired by
[passprompt](https://github.com/DanFreed/passprompt), which was originally
introduced to ease the pain of losing
[sudolikeaboss](https://github.com/ravenac95/sudolikeaboss) after `1Password`
6.8 upgrade.

`gopassprompt` is trying to achieve the same using `gopass` as underlying
password manager.

## Quick Start

This script relies on following packages to be pre-install on MacOS.

    brew install gnupg gopass pinentry-mac

Simply copy `gopassprompt` to your system (e.g /usr/local/bin/gopassprompt) and ensure it is executable.

Now create a keyboard shortcut in iTerm2 from the following paths: iTerm2
`Preferences -> Keys` or `Preferences -> Profiles -> Keys`, add a `Key Mapping`:

    * Set the key combination to "⌘'" (or other key you like)
    * Set the action to "Run Coprocess"
    * And the third field to the path where gopassprompt is located

Ensure GPG agent is setup correctly with following settings.

    $ cat ~/.gnupg/gpg.conf
    use-agent
    ...

    $ cat ~/.gnupg/gpg-agent.conf
    pinentry-program /usr/local/bin/pinentry-mac
    ...
