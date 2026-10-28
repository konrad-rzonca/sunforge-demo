# Sun Forge Demo

The playable web demo of the Sun Forge showcase, served at https://demo.sunforgetools.com/.

Each release holds one build as its `web.zip` asset, and the `Deploy` workflow serves the release it is given on GitHub Pages. No build is committed here: the private player project builds the demo and publishes it with its `publish-web.ps1`, which creates the release, runs the workflow and deletes all but the three latest releases.

To serve an older build again, run the workflow with its tag:

```
gh workflow run deploy.yml --repo konrad-rzonca/sunforge-demo -f tag=<release tag>
```

The site's custom domain is set in the repository's Pages settings, with its source on GitHub Actions. The domain's `demo` record is a CNAME to `konrad-rzonca.github.io` at Porkbun.
