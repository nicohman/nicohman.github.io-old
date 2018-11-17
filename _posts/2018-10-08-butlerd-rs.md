---
layout: default
title: "butlerd-rs"
tags: project rust
---
# butlerd-rs

[butlerd-rs](https://git.sr.ht/~nicohman/butlerd-rs) is a rust library for performing API calls over JSONRPC to itch.io's butlerd game manager daemon. I made it because I needed a better way to automatically scan for and launch itch games from [eidolon](http://nicohman.demenses.net/20180820/eidolon), and while my own usecase is quite limited, I did expand it to include almost all of the API. I used the official [butler docs](http://docs.itch.ovh/butlerd/master/#/) for refrence while coding this, and learned quite a bit about rust macros and traits while doing so. The docs for the library are hosted on [docs.rs](https://docs.rs/butlerd), just as the crate itself is hosted on [crates.io](https://crates.io/crates/butlerd) if you want to build something with it. A few notes: Currently, logging in is a bit weird, as if the API asks for either a two-factor token or a captcha result, the library will hang and possibly err out. I've tried to find a better solution for this, but not without getting too complicated and outside the purview of being a 'simple' library. My recommendation is that either you use API tokens for your project, or you implement that part of the AI yourself. Also, the EmptyResponse result type is mostly just so that you can check if a request that would normally return nothing failed.
