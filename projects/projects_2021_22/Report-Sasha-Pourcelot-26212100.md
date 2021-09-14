# Open Source Contribution Project
*Author:* Sasha Pourcelot

*NOMA:* 26212100

*Year:* 2021

*Selected project:* [The Rust Compiler](https://github.com/rust-lang/rust)

# Project research and selection

I discovered the Rust Programming Language when I started University and try
to participate to its development. I have already done a few contributions
([1], [2], [3]) which improve the error messages emitted during
parsing in very specific situations.

[1]: https://github.com/rust-lang/rust/pull/75779
[2]: https://github.com/rust-lang/rust/pull/76160
[3]: https://github.com/rust-lang/rust/pull/88546

As I love this language and the community that formed around it, I'd like to
contribute to its development again. I think [issue #27300][4] is a good
candidate. 

[4]: https://github.com/rust-lang/rust/issues/27300

# Issue description

This issue points out that the closures written with the Ruby syntax are
syntatically valid in Rust, but are not parsed the correct way, which causes
a very weird error messsage during the type-checking process.
