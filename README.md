# choliphant.github.io

This repository publishes the static site at:

<https://choliphant.github.io/>

## How deployment works

GitHub Pages serves `index.html` from the repository's `main` branch. After a
pull request is merged into `main`, GitHub will publish the update automatically.
The first deployment or a later update can take a few minutes to appear.

If the page does not publish, open the repository on GitHub and go to
**Settings → Pages**. Under **Build and deployment**, choose **Deploy from a
branch**, then select the `main` branch and `/ (root)` folder.

## Publishing future changes

From this repository directory:

```sh
git switch main
git pull --ff-only
git switch -c describe-your-change
# Edit index.html, then review the change.
git diff
git add index.html
git commit -m "Describe the site update"
git push -u origin describe-your-change
gh pr create --fill
gh pr merge --merge --delete-branch
```

After the pull request merges, visit <https://choliphant.github.io/>. You can
check deployment progress in the repository's **Actions** tab.
