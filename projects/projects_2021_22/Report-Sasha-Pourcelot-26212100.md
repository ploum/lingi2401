# Open Source Contribution Project
*Author:* Sasha Pourcelot

*NOMA:* 26212100

*Year:* 2021

*Selected project:* [cargo-doc2readme](https://github.com/msrd0/cargo-doc2readme)

# Project research and selection (23/11/2021)

Most Rust projects use tools such as [`cargo-readme`] to generate the README.md
file of their repository by processing the top-level documentation of library.

I recently opensourced [`dep_doc`], a Rust library that allow to generate code
snippets in Rust documentation using macros. It works quite well, but it turns
out that [`cargo-readme`] does not try to expand the macros provided by
[`dep_doc`], which generates incorrect README files.

[`dep_doc`]: https://github.com/scrabsha/dep-doc
[`cargo-readme`]: https://github.com/livioribeiro/cargo-readme

Issue [#64] of [`cargo-readme`] reports that some kind of macro-based
documentation is not handled too. I jumped in and commented the issue,
suggesting that all the macros should be handled as part of the README
generation. The issue author responded me that they maintain a prototype
modified version of [`cargo-readme`], entitled [`cargo-doc2readme`] where they
try to handle simple macros such as `#![doc = "my documentation string"]`.

[#64]: https://github.com/livioribeiro/cargo-readme/issues/64
[`cargo-doc2readme`]: https://github.com/msrd0/cargo-doc2readme

I opened issue [#37] of [`cargo-doc2readme`] suggesting that we should handle
`#![doc = macro_call!(...)]` situations and suggested that we could rely on the
Rust compiler to expand all the macros for us and use this expanded version for
the README generation.

[`#37`]: https://github.com/msrd0/cargo-doc2readme/issues/37

# Implementation (24/11/2021)

Some problems happened. For instance:
  - naive implementation would have run the build system (Cargo) inside the
  Rust build system, which is not permitted (there's a specific lockfile for it).
  - the code author uses Rust coding style that is not common in the Rust
  community and quite often considered as not idiomatic. The code is definitely
  correct and sound, but I was a bit disoriented at first.

Some features are really impressive. For instance, it is able to resolve Rust
imports. I tried (and failed) to implement such algorithm in [`cargo-breaking`]
and never did it correctly.

[`cargo-breaking`]: https://github.com/iomentum/cargo-breaking

I expected my pull request to be very small (less than 20 added lines
approximately) and it turns out that i underestimated the amount of required
changes. This is fine, i had a lot of fun doing it.

Anyways, I finally opened PR [#38].

[#38]: https://github.com/msrd0/cargo-doc2readme/pull/38

# Merging (25/11/2021)

The project maintainer, [`msrd0`] pushed a small commit on top of my branch in
order to fix a slightly misleading function comment, then ensured that the CI
actions properly pass, and merged my pull request.

[`msrd0`]: https://github.com/msrd0/

# Final thoughts

It was quite fun to contribute to this codebase and to discover different coding
styles than the one i'm used to. To my knowledge, [`cargo-doc2readme`] is the
only Rust-readme-generator that handles at the same time [`intra-doc-links`] and
macro expansion. I hope these two features will make it more widely used.

[`intra-doc-links`]: https://github.com/rust-lang/rfcs/blob/master/text/1946-intra-rustdoc-links.md

Thinking about documentation, intra-doc-links and macro expansion made me
realize that we could use the rustdoc, the Rust documentation processing tool,
to process the documentation and generate the readme. That would be a bit
cleaner. I even discovered [i could use rustdoc][icur] in another project i'm
working on, involving static analysis of the public API of a Rust library
([`cargo-breaking`])

[icur]: https://twitter.com/scrabsha/status/1463852016854343683
[`cargo-breaking`]: https://github.com/iomentum/cargo-breaking
