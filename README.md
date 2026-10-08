# Cool Computers Homebrew tap

Install the official native `cool` CLI on macOS or Linux:

```sh
brew install the-money-company-limited/tap/cool
```

Apple Silicon, Intel Macs, Linux ARM64, and Linux x86-64 use the same binaries
published by [Cool Computers](https://www.cool.computer/install). Homebrew
verifies the pinned SHA-256 checksum before installation.

```sh
cool --help
brew upgrade the-money-company-limited/tap/cool
```

To add Cool Computers instructions to your installed coding agents, run
`cool agents install`. Remove those instructions with `cool agents remove`.
Homebrew does not modify your agent configuration automatically.

To remove the CLI:

```sh
brew uninstall cool
```

If you previously used the standalone installer, check `which -a cool` for an
older copy in `~/.local/bin`. Remove that copy if you want Homebrew to manage
your installation.

[Product guide](https://cool.computer/docs) · [CLI installation](https://www.cool.computer/install)

## Maintaining the tap

`python3 scripts/update.py` reads the official current-release pointer and
manifest, downloads all four supported archives, checks their SHA-256 hashes,
and writes `Formula/cool.rb`. It refuses version downgrades. The scheduled
workflow checks for updates hourly, verifies a native Homebrew installation,
and commits the formula only after the test passes. You can also run that
workflow manually.
