# choliphant.github.io

This repository publishes the static site at:

<https://choliphant.github.io/>

## How deployment works

GitHub Pages serves this repository from the `main` branch. Each directory's
`index.html` becomes the page at that path. For example:

- `/index.html` → <https://choliphant.github.io/>
- `/cs472/index.html` → <https://choliphant.github.io/cs472/>
- `/cs472/readings/example/index.html` →
  `https://choliphant.github.io/cs472/readings/example/`

After a pull request is merged into `main`, GitHub will publish the update
automatically. The first deployment or a later update can take a few minutes to
appear.

If the page does not publish, open the repository on GitHub and go to
**Settings → Pages**. Under **Build and deployment**, choose **Deploy from a
branch**, then select the `main` branch and `/ (root)` folder.

## Adding a CS 472 reading artifact

1. Create a descriptive folder under `cs472/readings/`, such as
   `cs472/readings/neural-networks/`.
2. Put the artifact in that folder as `index.html` (plus any local images, CSS,
   or JavaScript it needs).
3. Add a card linking to it in `cs472/index.html`.
4. Preview both pages locally and then publish the change with the workflow
   below.

Keeping each artifact in its own folder gives it a stable URL and prevents a
new artifact from replacing the course or site home page.

## Publishing future changes

From this repository directory:

```sh
git switch main
git pull --ff-only
git switch -c describe-your-change
# Add or edit an artifact and its course-page link, then review the change.
git diff
git add cs472 README.md
git commit -m "Describe the site update"
git push -u origin describe-your-change
gh pr create --fill
gh pr merge --merge --delete-branch
```

After the pull request merges, visit <https://choliphant.github.io/>. You can
check deployment progress in the repository's **Actions** tab.
