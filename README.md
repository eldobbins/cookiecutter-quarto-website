# Cookiecutter Quarto Website

A Cookiecutter template to make a project that is a [Quarto](https://quarto.org/) website with places for slides, notebooks, and images.

- GitHub repo: https://github.com/eldobbins/cookiecutter-quarto-website
- Documentation: https://cookiecutter-pypackage.readthedocs.io/
- Free software: BSD license

## Features

- Contains the basic building blocks to create a [Quarto based website](https://quarto.org/docs/websites/).
  - [_quarto.yml](https://quarto.org/docs/websites/website-navigation.html#top-navigation) configuration file to generate the website navigation
  - index.qmd to serve as the homepage of the website
- a [GitHub action](https://github.com/features/actions) workflow to publish the website to [GitHub Pages](https://pages.github.com/)
- .gitignore file that will ignore the rendered HTML of the site
- several subdirectories to install content into
- a conda environment to allow quarto to run.  Includes JupyterLab for the notebooks.

## How to Create a New Project

Here are the commands to set-up a new project and to conntect it to a GitHub repo with  automatic publishing via GitHub Actions.

1. Install Cookiecutter on your local computer using the [Cookiecutter Installation Instructions](https://cookiecutter.readthedocs.io/en/stable/installation.html). I prefer the conda option and an environment called `cookies` generated from the included `environment.yml file.  
    1. `conda activate cookies`  

2. [Start a new GitHub repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories) using the online developer platform (hereafter called github.com). Go to your equivalent of `https://github.com/eldobbins?tab=repositories` and click the `New` button.
    1. Note the repository name you choose (i.e. `new-quarto-website`)
    2. Create a README.md file (and a main branch) while making the repo

3. Still at github.com, create the new branch in GitHub that will contain the rendered HTML website. That branch should be called `gh-pages`.

4. Still at github.com, to ensure GitHub Pages are enabled, navigate to Settings > Pages and make sure "Build and Deploy" uses the `gh-pages` branch.

5. To ensure the publishing Action has permission to write to `gh-pages`, navigate to Settings > Actions > General > Workflow Permissions and then check the “Read and Write Permissions” box.

6. To add a link to the new webpages in the repo, go to the Code tab and click the gear in the About section to the right. For Website, check the box for `Use your GitHub Pages website`.  If you click that link now, you will see the contents of the README.md file - so basically nothing yet.

7. On the command line of your local machine, use your chosen method to generate a new project from the template. For instance: `cookiecutter gh:eldobbins/cookiecutter-quarto-website`. 
    1. The name of the directory will be generated from your responses to the interactive prompts. For our example, enter "New Quarto Website" to match the repository name above.

8. Make the new directory a git repo, and [set the remote](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories) to your GitHub account

    ``` bash
    cd new-quarto-website
    git init
    git branch -M main
    git add -A
    git commit -m "Make new repo from cookiecutter-quarto-website"
    git remote add origin git@github.com:eldobbins/new-quarto-website
    git remote -v
    git push --force -u origin main
    ```

9. Check the Actions tab at github.com. You should see a queued or successful event called `pages build and deployment`.  Wait till it finished. (Refresh the page to update its progress.)

10. Look at the new website. If you see the README text, then the page did not build or deploy. Check the Actions tab for error messages and fix them.

## More Sources of Information

Here are some places to look for information if you get stuck.

Follow Quarto's instructions to authorize [GitHub Actions](https://quarto.org/docs/manuscripts/publishing.html#authorize-github-actions) for your repo if they aren't enabled by default. There are some screenshots that might help.

Follow Openscapes's instructions for [Set-up GitHub Publishing](https://openscapes.github.io/quarto-website-tutorial/explore.html#setup-github-action). You can skip the section on GitHub Actions because this should already be done. But you will need to make a new `gh-pages` branch and use it for the published website.

A very detailed workflow for how to use a Cookiecutter template to make a GitHub repo can be found at https://gist.github.com/cjtu/74a38e1ad066e714218762b910d0910e

To find other Cookiecutter templates, try https://github.com/search?q=cookiecutter&type=Repositories
