# Cookiecutter Quarto Website

A Cookiecutter template to make a project that is a [Quarto](https://quarto.org/) website with places for slides, notebooks, and images.


GitHub repo: https://github.com/eldobbins/cookiecutter-quarto-website
Documentation: https://cookiecutter-pypackage.readthedocs.io/
Free software: BSD license

## Features

* Contains the basic building blocks to create a [Quarto based website](https://quarto.org/docs/websites/).
  * [_quarto.yml](https://quarto.org/docs/websites/website-navigation.html#top-navigation) configuration file to generate the website navigation
  * index.qmd to serve as the homepage of the website
* a [GitHub action](https://github.com/features/actions) workflow to publish the website to [GitHub Pages](https://pages.github.com/)
* .gitignore file that will except the built site from git commit
* several subdirectories to install content
* a conda environment to allow quarto to run.  Includes JupyterLab for the notebooks.

## Required Manual Interventions

https://quarto.org/docs/manuscripts/publishing.html#authorize-github-actions

Do you need to make the branch too? Or will that pop up automatically


