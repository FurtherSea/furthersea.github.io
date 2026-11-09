# FurtherSea

The site at https://furthersea.org. For now it's only a placeholder; a site showing FurtherSea's research projects will replace it.

This repository owns the domain: the `CNAME` file and the Pages settings bind `furthersea.org` here, and GitHub Pages then serves every other repository's site at `furthersea.org/<repository name>/`, such as [Shiso](https://furthersea.org/shiso/) from `FurtherSea/shiso`. Keep the binding, or those addresses go back to `furthersea.github.io`.

`404.html` is what GitHub Pages serves for any address no repository covers. Shiso's site was at `/mise-homepage/` until November 2026, and copies of the app already installed still open its pages there, so a script at the top of `404.html` sends every address under `/mise-homepage/` to the same page under `/shiso/`, keeping the query and the fragment. Keep it while those copies are around.

The placeholder and its 404 page carry `noindex`, so search engines leave them out. Remove that tag when the real site goes in.
