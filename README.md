---
layout: page
title: Read Me
permalink: /readme/
---

## Introduction
This repository is meant to be an online notebook to help with preparation for Deutschtest für Zuwanderer (DTZ). Includes Flashcards to help develop German Vocabulary. 
If you have any feedback or face any issues [open an issue](https://github.com/vshanbha/DTZNotizbuch/issues/new?template=issue_template.md).

## Einführung
Dieses Repository soll ein Online-Notizbuch sein, um bei der Vorbereitung auf den Deutschtest für Zuwanderer (DTZ) zu helfen. Es enthält Karteikarten, um den deutschen Wortschatz zu entwickeln.
Wenn Sie Feedback haben oder auf Probleme stoßen, [öffnen Sie ein Issue](https://github.com/vshanbha/DTZNotizbuch/issues/new?template=issue_template.md).

The rest of the page covers developer instructions to work with this repository. 


## Usage Pre-Requisites
This repository is meant to be a template repository for a Blog or a Website and uses [Jekyll](https://jekyllrb.com/docs/){:target="_blank"} to transform markdown files into HTML. It has necessary setup to be deployed on to GitHub pages.

If you simply want to publish files using the default theme and markdown files and are happy to let Github pages do the publishing then the is not much to do just learn a little bit about Jekyll site structure and start creating posts inside the `_posts` directory. There is a getting started post already included there. You can start by editing that post.

A more detailed usage guide coming soon.

## Developer Guide
For developers or programmers who want to have fine grained control over the site here are the steps. 

If you want to edit and preview files on local machine then some set up is needed.
- `ruby`, `gcc` and `make` Installation: Latest stable [Ruby](https://www.ruby-lang.org/en/downloads/){:target="_blank"} version is recommended. Jekyll documentation provides up to date [OS specific install guides](https://jekyllrb.com/docs/installation){:target="_blank"}
- Jekyll CLI setup: Once pre-requisites are installed we need the `jekyll` and `bundle` command line interface (CLI) tools. Again Jekyll documentation provides a [quick start guide](https://jekyllrb.com/docs/#instructions){:target="_blank"}
- GitHub repository from Template: Create a new repository using this repository as a template with [Github templates](https://github.com/new?template_name=github_jekyll_pages_demo&template_owner=vshanbha){:target="_blank"}. 
- Clone GitHub repository: Clone the newly created GitHub repository and start editing the project files using your favourite editor.
- Ensure all Ruby Gem dependencies are installed
```bash
bundle install
```
- Jekyll local server: Running the site on local machine requires running the local server from the root directory of the newly created project.
```bash
bundle exec jekyll serve
```
## Customization
After creating a new repository there are some very simple and basic customization steps to be done and then the newly created GitHub repository would be ready to use as a blog or website. 
- Configuration: Jekyll offers a lot of finegrained [configuration options](https://jekyllrb.com/docs/configuration/){:target="_blank"}. The file `_config.yml` in the root folder has the bare bones configuration in place. 
- Name Changes: A few changes are of course in order. In the `_config.yml` Modify the fields `title`, `description`, `baseurl`, `url` and `github_username` to make the site your own.
- Theme: The `_config.yml` file has a simple responsive theme set up already [`"alembic-jekyll-theme"`](https://github.com/daviddarnes/alembic){:target="_blank"}. It is a simple theme with features including configurable colours, pagination, search, post categories and more. The documentation page has a lot of information. However, if this is not to your liking consider using a different theme. [Jekyll community](https://jekyllrb.com/docs/themes/){:target="_blank"} has a lot of themes available for use. 

## Deployment 
This template is meant to be a quick start for creating a website using Jekyll and Markdown. It includes ready GitHub Action for deploying to [GitHub Pages](https://pages.github.com/){:target="_blank"} using Jekyll. The file is `jekyll.yml` under `.github/workflows` is ready to use for deployments. All that is left is to set up GitHub pages deployment using this file as the configuration file for the GitHub deployment action.  
