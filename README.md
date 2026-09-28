# omegaflow/browser-ext

Static distribution of the hardened "OpenCode Browser" extension fork, served
over GitHub Pages for Chrome policy `force_installed`.

- `opencode-browser.crx` — packed extension, version 0.17.1
- `update.xml` — Chrome update manifest (appid `fmjakelcochilgoghbdgnomafoogilof`)
- `LICENSE` — MIT, upstream copyright `vymalo contributors`

Source: `omegaflow/omegaflow` → `tools/browser-extension` (a fork of
`@vymalo/opencode-browser-extension`, MIT). The fork adds the MV3 keepalive
(`chrome.alarms`) that keeps the localhost bridge connection alive across
service-worker eviction.

The extension connects to the OpenCode browser bridge at `ws://127.0.0.1:4517`;
the shared token is entered in the extension dashboard, never bundled here.

Policy install (Linux):

```
sudo cp policy.json /etc/opt/chrome/policies/managed/opencode-browser.json
```

with

```
{
  "ExtensionSettings": {
    "fmjakelcochilgoghbdgnomafoogilof": {
      "installation_mode": "force_installed",
      "update_url": "https://omegaflow.github.io/browser-ext/update.xml"
    }
  }
}
```
