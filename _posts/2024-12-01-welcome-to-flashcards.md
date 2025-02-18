---
title:  "Introducing Flashcards"
date:   2025-02-14 00:22:00 +0100
categories: 
---
## Introduction
This is an online notebook to help you prepare for the German Test for Immigrants better known as ["Deutsch-Test für Zuwanderer" (DTZ)](https://www.bamf.de/DE/Themen/Integration/ZugewanderteTeilnehmende/Integrationskurse/Abschlusspruefung/abschlusspruefung-node.html). 
This site contains flashcards to help expand your German vocabulary. The Flashcards page is available [here]( {% link flashcards.md %} ).
The flashcards page lists a set of "topics" and each Topic has several tabs of categories.
Each category has one or more flashcards. 

## Steps to create new Flashcards
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