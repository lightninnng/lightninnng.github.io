# Hai Luo — Academic Homepage

A personal academic homepage built with HTML and CSS. It presents Hai Luo's name, university, graduate school, and university email directly on the public page, so they are easy to find when visiting the homepage for identity verification.

## Project files

```text
.
├── index.html    # Homepage content and metadata
├── style.css     # Responsive layout and typography
├── .nojekyll     # Serve the static files without Jekyll processing
├── .gitignore    # Keep local preview artifacts out of Git
└── README.md     # Preview, deployment, and maintenance instructions
```

There is no JavaScript, framework, package installation, database, or backend. The page uses local CSS and system fonts. No build command is needed.

## Personal information

The homepage uses the supplied information and is entirely in English:

- **Name:** Hai Luo
- **University:** Tsinghua University
- **Graduate school:** Tsinghua Shenzhen International Graduate School
- **Position:** Master's Student
- **Public contact email:** h-luo26@mails.tsinghua.edu.cn
- **GitHub:** https://github.com/lightninnng
- **Master's education:** September 2026–Present; Civil and Hydraulic Engineering, Tsinghua University
- **Bachelor's education:** September 2022–June 2026; Bachelor of Engineering in Civil Engineering, Southwest Jiaotong University, School of Civil Engineering
- **Research interests:** Civil Engineering; Artificial Intelligence for Engineering; Structural Response Prediction

No personal information needs replacing before deployment. The education dates include the corrected undergraduate end date of June 2026. Publications currently read: “Publications will be updated here.” Update this section only when actual publication information is available.

The Git commit email `3102054116@qq.com` is separate from the university contact email displayed on the homepage.

## Local preview

Open `index.html` directly in any modern browser. Check both a wide desktop window and a narrow phone-sized window.

Optionally, if Python is installed, run the following in the project directory:

```powershell
python -m http.server 8000 --bind 127.0.0.1
```

Then open [http://127.0.0.1:8000/](http://127.0.0.1:8000/). Press `Ctrl+C` in the terminal to stop the server. Python is only an optional preview tool; it is not needed for the published website.

## Target repository and URL

- **Owner:** `lightninnng`
- **Repository name:** `lightninnng.github.io`
- **Repository:** [lightninnng/lightninnng.github.io](https://github.com/lightninnng/lightninnng.github.io)
- **Website after deployment:** [https://lightninnng.github.io/](https://lightninnng.github.io/)

This repository name creates a GitHub user site at the account's root Pages URL. Make the repository **Public**. See [GitHub's guide to creating a Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

The URLs above identify the intended deployment destination; this README does not assert that a push or deployment has already succeeded.

## Push to GitHub

Run commands from this directory in PowerShell. Install Git if `git --version` is unavailable. The optional GitHub CLI is available from [cli.github.com](https://cli.github.com/).

### 1. Check the current local repository

```powershell
git status
git branch --show-current
git remote -v
```

If the directory is not yet a Git repository, initialize it:

```powershell
git init -b main
```

If it already is a repository, keep its history. Check its branch and existing remote before continuing. The instructions below assume the publication branch is `main`; for a different existing branch, use its name consistently in both push commands and Pages settings.

Set the author details for this repository only:

```powershell
git config user.name "Hai Luo"
git config user.email "3102054116@qq.com"
```

Review and commit the website files:

```powershell
git add index.html style.css README.md .nojekyll .gitignore
git diff --cached
git commit -m "Create academic homepage"
```

If these files are already committed and there are no changes, skip the commit command.

### 2. Authenticate as lightninnng

With GitHub CLI installed, sign in through the browser, verify the account, and configure Git authentication:

```powershell
gh auth login --hostname github.com --git-protocol https --web
gh auth status
gh auth setup-git
```

Complete the browser flow using **lightninnng**. If another account is already authenticated, select the correct account before creating or pushing the repository. See the [official GitHub CLI authentication guide](https://cli.github.com/manual/gh_auth_login).

### 3A. If the target repository does not exist

For a local repository that has no `origin` remote, create the public remote and push the existing commit:

```powershell
gh repo create lightninnng/lightninnng.github.io --public --source=. --remote=origin --push
```

The command uses the current local Git repository and publishes its existing commits. See [the official `gh repo create` manual](https://cli.github.com/manual/gh_repo_create).

Alternatively, create a public repository named `lightninnng.github.io` on GitHub while signed in as `lightninnng`. Leave the new remote empty: do not initialize another README, license, or `.gitignore`. Then follow section 3B.

### 3B. If the target repository already exists or was created in the browser

If there is no `origin`, add it:

```powershell
git remote add origin https://github.com/lightninnng/lightninnng.github.io.git
```

If `origin` already points to that URL, keep it. If it points to another repository, preserve that remote and add a separate one:

```powershell
git remote add homepage https://github.com/lightninnng/lightninnng.github.io.git
```

In that case, replace `origin` with `homepage` in the commands below.

Before pushing to an existing remote, fetch and inspect its branches:

```powershell
git fetch origin
git branch -r
```

If the remote is empty, push directly:

```powershell
git push -u origin main
```

If it already contains `main`, integrate its history first:

```powershell
git pull --rebase origin main
git push -u origin main
```

Resolve any conflicts before pushing. If the remote was independently initialized and Git reports unrelated histories, inspect both versions and merge them deliberately rather than replacing the remote history. Do not use `--force` or delete existing remote content as a shortcut.

## Enable GitHub Pages

After the files have been pushed to `main`:

1. Open [the repository's Pages settings](https://github.com/lightninnng/lightninnng.github.io/settings/pages).
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Select branch **main** and folder **/(root)**.
4. Click **Save**.
5. Check the repository's **Actions** tab for the Pages deployment result.
6. Open [https://lightninnng.github.io/](https://lightninnng.github.io/) after deployment succeeds.

`index.html`, `style.css`, and `.nojekyll` must be in the selected branch's root directory. No custom workflow or framework configuration is required. See [GitHub's publishing-source instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

The empty `.nojekyll` file disables the default Jekyll processing for this static site. See [GitHub's static-site instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

Changes can take up to 10 minutes to appear after a push. See [GitHub Pages Quickstart](https://docs.github.com/en/pages/quickstart). If the page returns 404, first check the deployment result, the repository name, the selected branch, and the location of `index.html`.

## Verify the published homepage

Open the website in a private browser window without signing in to GitHub. Confirm that:

- The page is accessible at `https://lightninnng.github.io/`.
- **Hai Luo**, **Tsinghua University**, and **Tsinghua Shenzhen International Graduate School** are plainly visible.
- **h-luo26@mails.tsinghua.edu.cn** appears as readable text in Contact and links to the same email address.
- The layout remains readable on a phone.
- The GitHub link opens the correct account.

Once the public page is working, use **https://lightninnng.github.io/** as the personal homepage URL on OpenReview. Public visibility provides the requested identity information; OpenReview's registration review remains its own process.

## Maintain the homepage

Edit `index.html` to update your biography, education, interests, contact details, or publications. Edit `style.css` to adjust the appearance. After changing CSS, increase the version in the stylesheet link in `index.html` (for example, `style.css?v=2` to `style.css?v=3`) so returning visitors receive the updated styles. Preview the page locally, then commit and push:

```powershell
git add index.html style.css
git commit -m "Update academic homepage"
git push
```

GitHub Pages publishes updates from the configured source branch. Keep the public university email visible when changing the Contact section, and verify the published page after each content update.
