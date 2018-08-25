---
layout: default
title: "rws"
tags: rust, project
---

# rust-wildbow-scraper

[rust-wildbow-scraper](https://github.com/nicohman/rust-wildbow-scraper) automatically downloads and compiles into ePubs Wildbow's web serials for your own use, letting you read them in the format you want, while being offline. I highly advise anyone who uses this or reads his serials at all to donate to Wildbow via his [patreon](https://www.patreon.com/Wildbow) to show your appreciation. Currently, it supports all four of his main serials, plus the interim chapters between Twig and Ward, called Glow-worm. To scrape the chapters, it starts with a pre-configured 'starting chapter' URL, downloads it, uses [select](https://crates.io/crates/select) to parse the html, and saves the chapter title and content to a file in a content folder. Then, it follows the 'Next chapter' link and repeats the process until it can't go any farther. It uses [gen-epub-book](https://github.com/nabijaczleweli/gen-epub-book.rs) to turn the saved chapters into an ePub, and is then done. It also supports automatic downloading of fan-made book covers, to complete the metadata each book gets.

### Books

- [Worm](https://parahumans.wordpress.com)

- [Pact](https://pactwebserial.wordpress.com)

- [Twig](https://twigserial.wordpress.com)

- [Glow-worm](https://www.parahumans.net/2017/10/21/glow-worm-0-1) (hosted on the same site as Worm)

- [Ward](https://parahumans.net)

### Fan Cover Artists

- Worm: [/u/Winkle92](https://reddit.com/u/Winkle92)

- Pact: [/u/SozSurt](https://reddit.com/u/SozSurt)

- Twig: [mahasim](https://mahasim.deviantart.com)'s illustrations, but cover made by [/u/WildbowCoverArt](https://reddit.com/u/WildbowCoverArt)

None of the fan covers are distributed by me -- the scraper downloads them from wherever the artists posted them at ebook creation. Still haven't found any covers for Glow-worm or Ward, so if you find one, feel free to contact me.
