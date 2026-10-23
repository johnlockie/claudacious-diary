# Deploying

This site is hosted on **GitHub Pages**, served from the `main` branch of
`johnlockie/claudacious-diary`. There's no build step and no CI. The whole
app is the static `index.html`.

**Pushing to `main` is the deploy.**

## Steps

1. Make your change (usually an edit to `index.html`).
2. Commit it.
3. Push to GitHub:

   ```sh
   git push origin main
   ```

4. GitHub Pages republishes automatically, usually within a minute or two.
   You can watch progress in the repo's **Actions** tab ("pages build and
   deployment").

## Changes made by pod tasks

Work done as a codependence.ai pod task lands on a `cdp/task-<id>` branch,
not on `main`. To ship it:

```sh
git fetch origin
git checkout main
git merge origin/cdp/task-<id>
git push origin main
```

## Rolling back

Revert the bad commit and push. That redeploys the previous state:

```sh
git revert <commit>
git push origin main
```

## Notes

- Every file in the repo gets published by Pages, this one included.
- Pages settings (source branch, custom domain) live in the GitHub repo
  under **Settings → Pages**.
