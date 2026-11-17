# FurtherSea

The site at https://furthersea.org. For now it's only a placeholder; a site showing FurtherSea's research projects will replace it.

This repository owns the domain: the `CNAME` file and the Pages settings bind `furthersea.org` here, and GitHub Pages then serves every other repository's site at `furthersea.org/<repository name>/`, such as [Shiso](https://furthersea.org/shiso/) from `FurtherSea/shiso`. Keep the binding, or those addresses go back to `furthersea.github.io`.

`404.html` is what GitHub Pages serves for any address no repository covers. Shiso's site was at `/mise-homepage/` until November 2026, and copies of the app already installed still open its pages there, so a script at the top of `404.html` sends every address under `/mise-homepage/` to the same page under `/shiso/`, keeping the query and the fragment. Keep it while those copies are around.

The placeholder and its 404 page carry `noindex`, so search engines leave them out. Remove that tag when the real site goes in.

## Links that open Shiso

`.well-known/apple-app-site-association` lets the Shiso app (`CH83X89C6W.com.junhao.mise`, which claims `applinks:furthersea.org`) open the links on its dish cards' QR codes, `https://furthersea.org/shiso/r/?k=<key>`, wherever it's installed. Elsewhere those links open the page for the dish on Shiso's site. Apple fetches this file from the domain's root, which only this repository can serve, so it lives here and not in `FurtherSea/shiso`.

- It's JSON with no file extension. GitHub Pages serves it as `application/octet-stream`, which Apple accepts.
- `.nojekyll` keeps Jekyll off, so the `.well-known` folder is published as it is. Keep that file.
- It must answer 200 at `https://furthersea.org/.well-known/apple-app-site-association` with no redirect. `404.html` only redirects addresses under `/mise-homepage/`, so it never touches this one or `/shiso/r/`.
- Apple's CDN caches it, so a change can take a day to reach phones. `https://app-site-association.cdn-apple.com/a/v1/furthersea.org` shows what the CDN has.
- Only `/shiso/r` and what's under it open the app. Any other path added to `components` would open the app instead of the website, so add one only together with the app.
