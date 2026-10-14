# Wanting Yang — academic homepage draft

This is a first draft for review, built from the official [al-folio](https://github.com/alshedivat/al-folio) Jekyll template (v1.2, commit `b95d6d61a1b0663529094b1b5f4fbe8aa41f8a04`). It is an independent local Git repository. It has not been published.

## Preview locally

On this Mac, Homebrew Ruby is installed but macOS's older system Ruby appears first in the default shell path. From this directory, run:

```bash
export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000`. After setting `baseurl: /wanting-homepage` for GitHub Pages, preview at `http://localhost:4000/wanting-homepage/`. Stop the server with Control-C. The template's GitHub Actions workflow uses Ruby 3.3.5.

## Add your photo

The homepage uses `assets/img/profile.jpg` when that file is present. A roughly 4:5 portrait crop works with the current layout. Replace the file whenever you choose the final portrait.

## Add contact links

The homepage displays `contact.email` from `_config.yml` as plain text, exactly as written. It uses `contact.scholar_userid` for the Google Scholar link. Empty fields are hidden. The ORCID ID remains in `_config.yml` for future use but is not shown on the homepage.

## Add a paper PDF

Place a PDF you are permitted to share in `assets/pdf/`, for example `assets/pdf/multi-product-pricing-2026.pdf`. Then append this link to the relevant bullet in `_pages/research.md`:

```markdown
([PDF]({{ '/assets/pdf/multi-product-pricing-2026.pdf' | relative_url }}))
```

Keep the existing journal link. The `relative_url` filter also works when the site is published under a GitHub Pages repository path. A PDF is not included in this draft.

## Publish to GitHub Pages after review

1. Create a new **empty** GitHub repository called `wanting-homepage` in your account. Keep this local directory as the repository root. Do not initialize the GitHub repository with another README or template.
2. In `_config.yml`, set `url: https://YOUR_USERNAME.github.io` and `baseurl: /wanting-homepage`. If you instead create a user site repository named `YOUR_USERNAME.github.io`, leave `baseurl:` empty.
3. Add your GitHub repository as `origin`, commit this directory, and push the `main` branch. The included workflow builds the site and deploys it with GitHub Actions.
4. In **Settings → Pages → Build and deployment → Source**, choose **GitHub Actions**. Check the **Actions** tab for the `Deploy site` run, then use the **Visit site** link in Pages settings.

The site has no remote repository or public URL yet. Pushing the `main` branch will trigger the included deployment workflow, so finish your visual and text review first.

After publishing, continue editing the local source files, preview with `bundle exec jekyll serve`, then commit and push `main` again. Each push that changes site files triggers a new deployment; GitHub Pages may take several minutes to show the update.

## Human review before publishing

- Home: biography, research framing, degree wording, affiliation, portrait, email, and Scholar.
- Research: verify the working papers' titles, author order, status, and links; review the publication entry and add a shareable PDF if desired.
- Teaching: confirm the four course titles and codes, and replace each `[Semester / Year]` placeholder with the actual term. DDA3600 appears once because the provided list contained both the course and its `_L01` entry.
- Configuration: public URL, base URL, email, Scholar ID, and optional social icons.
