# Web archives (WACZ), November 2026

`bundles_2026-11.csv` lists 19 web-archive bundles (WACZ files, 896 works in all, about 2.47 GB) that we made on 15 and 16 November
2026 for works whose pages and files the Internet Archive could not capture for us. Each bundle holds, for up to 50 works, the pages and
files as our own headless browser fetched them (one WARC with the requests, the responses and a full-page screenshot of each work's page),
packed as a WACZ. For each bundle the list gives its IPFS CID, the WACZ file's SHA-256 and size in bytes, the number of works, the date
it was made, a note, and the name of its timestamp proof.

- Bundles 1-17 (837 works): the works' pages and files as their addresses answered on 15 November 2026 - **archived; replay of the
  OpenSea item page not guaranteed** (the OpenSea item page is a live application, so a replay may not draw it fully; the screenshot
  inside the bundle shows it as it was).
- Bundles 18-19 (59 works): works whose original servers no longer answer. For these, the bundle holds **OpenSea's current page and
  stored copy; the original server no longer answers** - the OpenSea item page with its screenshot, and the image (and, where there is
  one, the animation) as OpenSea stores it.

**How to check a bundle:** fetch the WACZ by its CID from any IPFS gateway (for example `https://ipfs.io/ipfs/<cid>`), compute its
SHA-256 (`sha256sum` on Linux or macOS, `certutil -hashfile <file> SHA256` on Windows) and compare it with the `sha256` column. A WACZ
opens in [ReplayWeb.page](https://replayweb.page).

**Independent timestamps:** each `bundle_NN.wacz.ots` is an [OpenTimestamps](https://opentimestamps.org) proof that the bundle's WACZ
file existed no later than the Bitcoin block it names. With the OpenTimestamps client (`pip install opentimestamps-client`),
`ots verify bundle_NN.wacz.ots` (beside the downloaded WACZ, named `bundle_NN.wacz`) checks it against a local Bitcoin node; without one,
`ots info bundle_NN.wacz.ots` shows the path from the file's SHA-256 to the block, and its final value, read byte-reversed, equals that
block's merkle root on any block explorer.
