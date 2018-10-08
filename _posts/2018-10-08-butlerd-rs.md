---
layout: default
title: "butlerd-rs"
tags: project rust
---
# butlerd-rs

[butlerd-rs](https://github.com/nicohman/butlerd-rs) is a rust library for performing API calls over JSONRPC to itch.io's butlerd game manager daemon. I made it because I needed a better way to automatically scan for and launch itch games from [eidolon](http://nicohman.demenses.net/20180820/eidolon), and while my own usecase is quite limited, I did expand it to include almost all of the API. I used the official [butler docs](http://docs.itch.ovh/butlerd/master/#/) for refrence while coding this, and learned quite a bit about rust macros and traits while doing so. The docs for the library are hosted on [docs.rs](https://docs.rs/butlerd), just as the crate itself is hosted on [crates.io](https://crates.io/crates/butlerd) if you want to build something with it.
