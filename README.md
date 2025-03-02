---
layout: page
title: Read Me
permalink: /readme/
---

## Introduction
This repository is meant to be an online notebook to help with preparation for Deutschtest für Zuwanderer (DTZ). Includes Flashcards to help develop German Vocabulary. 
If you have any feedback or face any issues [open an issue](https://github.com/vshanbha/DTZNotizbuch/issues/new/choose).

## Einführung
Dieses Repository soll ein Online-Notizbuch sein, um bei der Vorbereitung auf den Deutschtest für Zuwanderer (DTZ) zu helfen. Es enthält Karteikarten, um den deutschen Wortschatz zu entwickeln.
Wenn Sie Feedback haben oder auf Probleme stoßen, [öffnen Sie ein Issue](https://github.com/vshanbha/DTZNotizbuch/issues/new/choose).
Der Rest der Seite enthält technische Anweisungen für Entwickler dieses Repositorys. Die technische Dokumentation ist derzeit nur auf Englisch verfügbar.

## Developer Envrionment Setup
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

## Creating new Flashcards
To set up new Flashcards there are following steps

1. Setup Development Environment:
Follow the [read me]( {% link README.md %}) instructions to set up a development environment

2. Create a new Database file:
For each topic we need one file of the name `topic.yml` to be placed in the `_data/topics` folder. There are already a couple of files there to act as samples.
The datbase follows a simple to use file format called [YAML](https://yaml.org/). A simple cheat sheet on how to use YAML is available [here](https://yamline.com/tutorial/). 
The file follows a simple logical and hierarchical structure and hopefully it should be self explanatory. However the formatting of file depends on spaces and therefore be careful to understand and use the spaces correctly. Otherwise the site is not generated properly and new updates will not show up.
Here is an example:

    ```yaml
    title: Personalien Flashcards
    topic: personalien
    categories:
    - name: Nouns
        value: "Nomen"
        cards:
        - id: 1001
            title: "Der Name"
            description: "Wie man jemanden nennt."
            related_cards: ["Der Vorname", "Der Nachname", "Der Spitzname", "Der Familienname", "Der Mädchenname"]
            examples: ["Mein Name ist Anna.", "Wie ist dein Name?", "Er hat einen ungewöhnlichen Namen."]
    - name: Verbs
        value: "Verben"
        cards:
        - id: 2001
            title: "heißen"
            description: "Den Namen einer Person oder Sache angeben."
            related_cards: ["Der Name", "Der Vorname", "Der Nachname", "Der Spitzname", "Der Familienname"]
            examples: ["Ich heiße Anna.", "Wie heißt du?", "Er heißt Peter."]
        - id: 2002
            title: "wohnen"
            description: "An einem bestimmten Ort leben."
            related_cards: ["Die Adresse", "Die Straße", "Die Hausnummer", "Der Wohnort", "Das Land"]
            examples: ["Ich wohne in Berlin.", "Wo wohnst du?", "Sie wohnt in einer kleinen Stadt."]
    ```

3. Create a new Flashcard page:
Once a YAML database is created all that is left is to create a mardown file under the folder `_pages` with the name `topic.md`. An example file for topic `personalien` is already present. For new topics all that needs to change is the name of the file and the values in the fields `title` and `topic`. 
Important to note that the value of `topic` field should exactly match the Topic name of the database file `topic.yaml`. That is how the layout matches the presentation of the file with its appropriate database.

    ```markdown
    ---
    layout: flashcards
    title: Personalien
    permalink: /themes/:title
    topic: personalien
    ---
    ```

4. Reuild the site:
That's it. Once a new topic and its database are added rebuild the site and check that the new topic and its contents are available. Have fun.