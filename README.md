# AdGuard-Lists

Blocklists for [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome), in AdGuard filter syntax (`||domain`). The repository hosts three lists: a general ads list and two YouTube ad lists. Add them to AdGuard Home by URL.

## Lists

| File | Rules | Blocks | Based on |
|------|------:|--------|----------|
| [`ads.txt`](ads.txt) | 154,542 | General advertising domains | [The Block List Project – Ads List](https://blocklistproject.github.io/Lists/ads.txt) |
| [`youtube.txt`](youtube.txt) | 1,440 unique (1,640 lines) | YouTube ad-serving `googlevideo.com` hosts | [anudeepND's YouTube list (gist)](https://gist.githubusercontent.com/anudeepND/adac7982307fec6ee23605e281a57f1a/raw/5b8582b906a9497624c3f3187a49ebc23a9cf2fb/Test.txt) |
| [`youtube2.txt`](youtube2.txt) | 364 | YouTube and Google ad domains (`doubleclick.net`, `fwmrm.net`, `googlevideo.com` hosts, …) | Ewpratten/youtube_ad_blocklist (upstream repository has since been removed) |

Every rule uses the AdGuard/Adblock-style domain syntax `||example.com`, which blocks the domain and all its subdomains. `ads.txt` also keeps the upstream header comments (`#`).

> **Note:** these lists are snapshots, imported once on 2021-12-28. Nothing in this repository updates them automatically. For the most current ads list, subscribe to the upstream source directly.

## Usage

1. In AdGuard Home, open **Filters → DNS blocklists**.
2. Click **Add blocklist → Add a custom list**.
3. Enter a name and one of the raw URLs below, then click **Save**.

| List | Raw URL |
|------|---------|
| Ads | `https://raw.githubusercontent.com/t0mer/AdGuard-Lists/main/ads.txt` |
| YouTube | `https://raw.githubusercontent.com/t0mer/AdGuard-Lists/main/youtube.txt` |
| YouTube 2 | `https://raw.githubusercontent.com/t0mer/AdGuard-Lists/main/youtube2.txt` |

## Troubleshooting

* **YouTube videos stop playing.** The YouTube lists block individual `googlevideo.com` hosts. YouTube serves both ads and regular video from `googlevideo.com`, so blocking these hosts can break normal playback. Disable the YouTube list, or allowlist the affected host in AdGuard Home's query log.
* **Legitimate sites are blocked by `ads.txt`.** Unblock the domain from the AdGuard Home query log, or report the false positive to [The Block List Project](https://github.com/blocklistproject/lists).

## Contributing

Issues and pull requests are welcome. For changes to `ads.txt`, contribute to the upstream [Block List Project](https://github.com/blocklistproject/lists) instead.

## License

This repository has no license file. `ads.txt` comes from The Block List Project, which publishes it under the [Unlicense](https://unlicense.org). The upstream sources of the YouTube lists state no license.
