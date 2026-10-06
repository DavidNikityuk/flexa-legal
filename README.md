# flexa-legal

Legal pages for the Flexa app, served by GitHub Pages (Jekyll, no build step):

| | Ukrainian (originals) | English |
| --- | --- | --- |
| Terms of Use | https://davidnikityuk.github.io/flexa-legal/terms/ | https://davidnikityuk.github.io/flexa-legal/terms-en/ |
| Privacy Policy | https://davidnikityuk.github.io/flexa-legal/privacy/ | https://davidnikityuk.github.io/flexa-legal/privacy-en/ |
| Support | https://davidnikityuk.github.io/flexa-legal/support/ | https://davidnikityuk.github.io/flexa-legal/support-en/ |

The app builds these URLs in `lib/core/constants/app_links.dart`
(`AppLinks.legalPage`): the Ukrainian app language opens the originals, every
other language the `-en` pages (BLOCK37 §6). The edition date at the top of
`terms.md` / `privacy.md` is what the app records on acceptance
(`LegalVersions`) — bump both together when a text changes.

Every page needs the YAML front matter (`title`, `lang`): without it Jekyll
copies the Markdown as a raw file instead of rendering it. Links between pages
are relative (`../privacy-en/`), which works under the `/flexa-legal/` base
path with `permalink: pretty`.

## Updating

Edit the Markdown, commit, `git push` — Pages rebuilds within a minute or two.
Pages source: Settings → Pages → *Deploy from a branch*, `main`, `/ (root)`.
