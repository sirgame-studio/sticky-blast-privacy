# Stickman Blast Party – Privacy Policy site

Static privacy policy for the Stickman Blast Party Android app, published with GitHub Pages at:

**https://sirgame-studio.github.io/sticky-blast-privacy/**

This folder is the source. It is published as the root of the public repository
`sirgame-studio/sticky-blast-privacy` (branch `main`, folder `/`). `.nojekyll` turns off the
Jekyll build so the HTML is served as-is. The folder is not a Git repository itself: it is
copied into a checkout of the Pages repository to publish.

## Publish or update

```sh
# one-time (already done): create the repo from a copy of this folder and enable Pages
rm -rf /tmp/sticky-blast-privacy && cp -R privacy-site /tmp/sticky-blast-privacy && cd /tmp/sticky-blast-privacy
git init -b main && git add . && git commit -m "Stickman Blast Party privacy policy"
gh repo create sirgame-studio/sticky-blast-privacy --public --source . --push --description "Privacy policy for the Stickman Blast Party Android game"
gh api -X POST repos/sirgame-studio/sticky-blast-privacy/pages -f "build_type=legacy" -f "source[branch]=main" -f "source[path]=/"

# later updates
rm -rf /tmp/sticky-blast-privacy && gh repo clone sirgame-studio/sticky-blast-privacy /tmp/sticky-blast-privacy
cp privacy-site/index.html privacy-site/README.md /tmp/sticky-blast-privacy/
cd /tmp/sticky-blast-privacy && git add . && git commit -m "Update privacy policy" && git push
```

GitHub can take a few minutes to publish. Then check:

```sh
curl -sSI https://sirgame-studio.github.io/sticky-blast-privacy/ | head -1   # expect HTTP/2 200
```

## Keep it in sync

Update this page and the effective date whenever any of these change:

- SDKs in the app (for example adding analytics or crash reporting).
- What the app stores in Firebase (`docs/rtdb-structure.md`) or how long it keeps it.
- Ad formats or mediation partners.
- The Google Play Data safety answers (`store-assets/android/listing.md`).
- The package name (currently `com.stickyblast.app`) or the target audience (13+, not directed at children).
