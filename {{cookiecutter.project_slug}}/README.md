# {{cookiecutter.project_slug}}
{{cookiecutter.project_short_description}}


## Preview and Render Locally


[Website Previewing](https://quarto.org/docs/websites/#website-preview) allows viewing of the completed website by generating HTML from the `qmd` files. VSCode and RStidio both render and preview pages automatically using a `Render` button.

To preview the website using commands in the terminal:
``` bash
# preview the website in the current directory
quarto preview
```
It should automatically open a browser window. See `quarto preview help` for hints

You can also render the website without displaying it. The generated code goes in the `_site` directory (which should be listed in .gitignore)
``` bash
# render the website in the current directory
quarto render 
```

## Publishing via GitHub

Set things up (or is that the cc business)


## Credits

Website format is based on the [Quarto Website Tutorial](https://openscapes.github.io/quarto-website-tutorial/) developed by [Openscapes](https://openscapes.org/). Code is avalable in the [tutorial GitHub repo](https://github.com/Openscapes/quarto-website-tutorial/tree/main).

This project was created using the [cookiecutter-quarto-website](https://github.com/eldobbins/cookiecutter-quarto-website) template that utilizes the [Cookiecutter](https://cookiecutter.readthedocs.io/en/stable/README.html) project.