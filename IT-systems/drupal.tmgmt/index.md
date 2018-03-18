---
title: EU-OSHA Translation management demo
---
#  EU-OSHA Translation management demo


<small class="github">[drupal.tmgmt](https://github.com/EU-OSHA/drupal.tmgmt)</small>

This repository contains a fully working Drupal installation that demonstrates
the functionality of the EU-OSHA translation management workflow. If you want
to separately download only the Drupal module that implements the
functionality, please use the `release` section of this repository where the
archive is found.

[![Code
Climate](https://camo.githubusercontent.com/ece01114938c0194fde598550e0416a7eec50f1f/68747470733a2f2f636f6465636c696d6174652e636f6d2f6769746875622f45552d4f5348412f64727570616c2e746d676d742f6261646765732f6770612e737667)](https://codeclimate.com/github
/EU-OSHA/drupal.tmgmt) [![Issue
Count](https://camo.githubusercontent.com/8014f2b1ca106fc180a7e9caa5f7395197b0484c/68747470733a2f2f636f6465636c696d6174652e636f6d2f6769746875622f45552d4f5348412f64727570616c2e746d676d742f6261646765732f69737375655f636f756e742e737667)](https://codeclimate.com/github
/EU-OSHA/drupal.tmgmt)

How to start using the product

  * Read the [product specifications](/EU-OSHA/drupal.tmgmt/blob/master/docs/functional-specifications.pdf) located in the `docs/` directory.
  * Create an working instance by using the Vagrant recipe located in the [vagrant](/EU-OSHA/drupal.tmgmt/blob/master/vagrant) directory.

##  Known issues

In order to develop the product, we have integrated functionality from third
party modules. However, during development we have identified issues using
these modules, therefore we have applied a set of patches on these modules. To
keep track of the applied patches, these are stored in the [patches](/EU-
OSHA/drupal.tmgmt/blob/master/patches) directory.

#  ChangeLog

##  7.x-1.1 - 2018-01-15:

Ported all the changes up to (including):
`bb693536db69c9f9f7e376017e9e66d97270e748`

###  Fixed

  * [MDR-351](https://jira.osha.europa.eu/browse/MDR-351): Notifications inside different workflows - Adapt notifications to the real message (partial port)
  * [MDR-767](https://jira.osha.europa.eu/browse/MDR-767): Cannot download publications (partial port)
  * [MDR-237](https://jira.osha.europa.eu/browse/MDR-237): Fix permissions for final language revisions before publishing content
  * [MC-321](https://jira.osha.europa.eu/browse/MC-321): Re-translate option does not work for a page
  * [MC-313](https://jira.osha.europa.eu/browse/MC-313): Error when setting translations to "Ready to Publish"
  * [MC-161](https://jira.osha.europa.eu/browse/MC-161): Remove temporary job items older than 1 day

###  Added

  * Ported integration with search_api for translated nodes
  * New button for cleaning up tmgmt id's
  * [MDR-911](https://jira.osha.europa.eu/browse/MDR-911) \- Added compatibility with metatag >= 7.x-1.21 (adapted port)
  * [MC-277](https://jira.osha.europa.eu/browse/MC-277): Create preview option for translation jobs
  * [MDR-177](https://jira.osha.europa.eu/browse/MDR-177): Develop an interface that would allow us to send selected paragraphs to translation

[Edit this page](https://github.com/EU-OSHA/drupal.tmgmt/edit/master/README.md)
