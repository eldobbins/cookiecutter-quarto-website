# Cookiecutter Quarto Website

A Cookiecutter template to make a project that is a [Quarto](https://quarto.org/) website with places for slides, notebooks, and images.


- GitHub repo: https://github.com/eldobbins/cookiecutter-quarto-website
- Documentation: https://cookiecutter-pypackage.readthedocs.io/
- Free software: BSD license

## Features

* Contains the basic building blocks to create a [Quarto based website](https://quarto.org/docs/websites/).
  * [_quarto.yml](https://quarto.org/docs/websites/website-navigation.html#top-navigation) configuration file to generate the website navigation
  * index.qmd to serve as the homepage of the website
* a [GitHub action](https://github.com/features/actions) workflow to publish the website to [GitHub Pages](https://pages.github.com/)
* .gitignore file that will except the built site from git commit
* several subdirectories to install content
* a conda environment to allow quarto to run.  Includes JupyterLab for the notebooks.


## How to Create a New Project

A complete workflow for how to use a Cookiecutter template to make a GitHub repo can be found at https://gist.github.com/cjtu/74a38e1ad066e714218762b910d0910e. This set-up is slightly different because it includes automatic publishing via GitHub Actions.

1. Install Cookiecutter using the [Cookiecutter Installation Instructions](https://cookiecutter.readthedocs.io/en/stable/installation.html). I prefer the conda option.

2. Copy the template into a new directory with `cookiecutter gh:eldobbins/cookiecutter-quarto-website`. The name of the directory will be generated from your responses to the interactive prompts. We'll pretend it is `new-quarto-website`.

3. Make the new directory a git repo, and [set the remote](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories) to your GitHub account
``` bash
cd new-quarto-website
git init
git add -A
git commit -m "Make new repo from cookiecutter-quarto-website"
git remote add origin git@github.com:eldobbins/new-quarto-website
git remote -v
git branch -M main
```

4. Go to GitHub, click + "make a new repository", call it the same thing as your cookiecutter folder: `new-quarto-website`.  

5. Back to the terminal
``` bash
git push -u origin main
```

6. After you create the main branch, you can create the new branch in GitHub that will contain the rendered HTML website. That branch should be called `gh-pages`.

7. To ensure publishing Action has permission to write to `gh-pages`, navigate to Settings > Actions > General > Workflow Permissions and then check the “Read and Write Permissions” box.

8. After you create the `gh-pages` branch, you can check the Actions tab in GitHub. You should see a successful event called `pages build and deployment`. There might be a falure or two, but it should be working now. Perhaps resubmit the failed job if needed.

9. To add a link to the new webpages in the repo, go to the Code tab and click the gear in the About section to the right. For Website, check the box for `Use your GitHub Pages website`.

10. Look at the new website. If you see this README text, then the page did not build or deploy. Check the Actions tab for error messages.


## More Sources of Information

Here are some places to look for information if you get stuck.

Follow Quarto's instructions to authorize [GitHub Actions](https://quarto.org/docs/manuscripts/publishing.html#authorize-github-actions) for your repo if they aren't enabled by default. There are some screenshots that might help.

Follow Openscapes's instructions for [Set-up GitHub Publishing](https://openscapes.github.io/quarto-website-tutorial/explore.html#setup-github-action). You can skip the section on GitHub Actions because this should already be done. But you will need to make a new `gh-pages` branch and use it for the published website.
