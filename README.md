# UNCC Game Developers Docs

Source for the club's **Game Jam Organizer Guide**, published with GitHub Pages at
<https://unccgamedevelopers.github.io/unccgamedev-docs/>.

The site uses the open-source [jekyll-gitbook](https://github.com/sighingnow/jekyll-gitbook)
theme (Apache-2.0). You only edit Markdown files. GitHub Actions builds the site
every time `main` changes, so nobody commits generated HTML and there is no `gh-pages` branch.

## Where things live

| Path | What it is |
| --- | --- |
| `index.md` | The home page (the guide's introduction). |
| `_chapters/` | One Markdown file per chapter. The sidebar lists them in filename order. |
| `_config.yml` | Site title, theme version and sidebar settings. |
| `.github/workflows/pages.yml` | The build and deploy workflow. |

## Edit a chapter

1. Open the chapter in `_chapters/` on GitHub and select the pencil icon (**Edit this file**).
2. Make your change in Markdown.
3. Select **Commit changes…**, choose **Create a new branch for this commit and start a pull request**, then select **Propose changes**.
4. Open the pull request. The **Pages** check builds the site to catch mistakes.
5. When an officer approves and merges it, the live site updates within a few minutes.

## Add a new chapter

1. In `_chapters/`, create a file named with a two-digit number and a short name, for example
   `15-board-game-jams.md`. The number sets its place in the sidebar.
   To put it between two chapters, renumber the files after it.
2. Start the file with a title block:

   ```markdown
   ---
   title: "Board Game Jams"
   ---

   Your chapter text starts here.
   ```

3. Use `##` and `###` for headings inside the chapter. They become the chapter's
   table of contents in the sidebar.
4. Open a pull request as in [Edit a chapter](#edit-a-chapter).

## Writing rules

- **No personal information.** No real names, emails, phone numbers, Discord or
  GitHub handles, addresses or account details. Write roles instead ("the event lead",
  "an officer"). If an example needs a name, use `alex`.
- **No passwords or account access.** Never put logins, recovery codes or shared
  account details in this repository, even in a draft.
- **Write for someone new.** Short steps, plain words, and say *why* when it isn't obvious.
- **Accessible pages.** Give every image alt text, use descriptive link text
  (not "click here"), and don't rely on color alone to carry meaning.
- **Check links to university offices and forms.** Their rules and dollar limits change
  each year, so link to the official page rather than copying numbers that will go stale.

## Preview locally (optional)

You don't need this to edit the guide; the pull request check builds it for you.
If you want to preview on your own computer, follow GitHub's guide,
[Testing your GitHub Pages site locally with Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll).
Don't commit the `_site/` folder or a `Gemfile.lock`; `.gitignore` already skips `_site/`.

## Updating the theme or actions

The theme and every GitHub Action are pinned to an exact commit so a change upstream
can't alter the site without review.

- **Theme:** in `_config.yml`, `remote_theme` ends with `@<commit SHA>` from
  [sighingnow/jekyll-gitbook](https://github.com/sighingnow/jekyll-gitbook/commits).
- **Actions:** in `.github/workflows/pages.yml`, each `uses:` line has a commit SHA and a
  `# vX.Y.Z` comment.

To update one, pick a release or commit that is **at least two weeks old**, replace the SHA
(and the version comment), and open a pull request so the build check runs.

## License

[MIT](LICENSE). The jekyll-gitbook theme is used under the Apache-2.0 license.
