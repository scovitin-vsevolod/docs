---
title: EU-OSHA documentation hub
---

# EU-OSHA documentation hub

Source for documentation at https://eu-osha.github.io/docs.

## To update existing content

Use the link `Edit this page` on the bottom of each page to find the right file in the repository, and update the contents directly using the GitHub markdown editor.

## To add new content

Here in the repository (https://github.com/eu-osha/docs/tree/gh-pages),

1. add a new folder in the format `My-new-folder-name`
2. add a new file to the folder named `index.md`
3. update https://github.com/eu-osha/docs/blob/gh-pages/_data/menu.yml accordingly. Each menu item is described by two lines - first line is the menu title, second line is the URL to the folder just created.

## To update documentation within "IT-systems" section

**IT-systems** documentation is generated automatically based on documentation found on each github repo within https://github.com/eu-osha. Thus, in order to update docs for one section under **IT-systems** all you have to do is to update github repo README and wait for the documentation to be regenerated. For example, in order to update documentation for ** EU-OSHA - Corporate - Drupal website ** you will need to edit https://github.com/eu-osha/osha-website/blob/master/readme.md
