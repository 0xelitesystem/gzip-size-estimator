# Gzip Size Estimator

Paste text or code and see its raw byte size versus gzip and deflate compressed size, right in your browser. No server, no tracking, no third-party scripts.

**Live demo:** https://0xelitesystem.github.io/gzip-size-estimator/

## Use

Open `index.html` in any modern browser, or visit the GitHub Pages link in the repo description.

Paste text, JSON, HTML, CSS, or source code. As you type (debounced), the tool shows:

- **Raw size** (UTF-8 encoded byte count)
- **Gzip size** via the browser CompressionStream API
- **Deflate size** if the browser supports the deflate variant
- **Savings percentage** of gzip versus raw
- A bar chart comparing raw, gzip, and deflate

If the browser does not support CompressionStream, the tool shows a clear message instead of guessing. If deflate is unavailable but gzip works, it shows gzip only.

## Why this exists

Bundle size numbers usually quote gzipped bytes, but most quick size checks only show you the raw length. This measures the actual gzip output using the browser's native compressor, so the number matches what a server would send over the wire, without installing anything or pasting your code into a remote service.

Note: real servers may use a different compression level, so treat this as a close estimate rather than a byte-exact match to your production headers.

## Privacy

Everything runs in your browser. Compression happens locally through CompressionStream and your text is never uploaded. You can verify by viewing the page source or by opening DevTools and watching the network tab, no requests are made.

## Run locally

```bash
git clone https://github.com/0xelitesystem/gzip-size-estimator
cd gzip-size-estimator
# Open index.html in your browser, or:
python -m http.server 8000
```

## Build

There is no build. It's a single HTML file.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT.

## Related

- [color-contrast-checker](https://github.com/0xelitesystem/color-contrast-checker)
- [color-format-converter](https://github.com/0xelitesystem/color-format-converter)
- [gradient-generator](https://github.com/0xelitesystem/gradient-generator)
