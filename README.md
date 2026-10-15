# grog-release

`latest.json` is the manifest Grog's update check reads, at most once a day, from
`https://raw.githubusercontent.com/HITOA/grog-release/main/latest.json`.

```json
{
    "format": 1,
    "latest": { "version": "0.1.0", "date": "2026-11-02", "summary": "New nodes." },
    "url": "https://www.patreon.com/..."
}
```

- `format`: the manifest's layout. A Grog that doesn't know it ignores the manifest.
- `latest.version`: `major.minor.patch`. A Grog older than it shows that it's available.
- `latest.summary`: optional, shown when hovering the notice.
- `url`: where to get Grog. Grog only opens https links to the sites it knows (`src/UI/Browser.cpp`),
  and shows the notice without a link while it's empty.

Publishing a release: set `version` (and `date`, `summary`) once the binary is out, then push.
