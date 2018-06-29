---
title: OSHA
---
OSHA
====

<small class="github">[test_md](https://github.com/scovitin-vsevolod/test_md)</small>


Build scripts and source code for the OSHA project

[![Code Climate](https://codeclimate.com/github/EU-OSHA/osha-website/badges/gpa.svg)](https://codeclimate.com/github/EU-OSHA/osha-website)

### Definitions, acronyms and abbreviations
Term	| Description
--------|--------------------------------------------------
EU-OSHA	| European Agency for Safety and Health at Work
CdT	| Translation Centre for the Bodies of the European Union
FOP	| National Focal Point
NCW	| New Corporate Website
HWC	| Healthy Workplaces Campaign
CMW	| Content Management Workflow
HWC18| Healthy Workplaces Campaign (2018-2019)


## 1. Organisation of repository
* ### Repository Layout
    Breakdown for what each directory/file is used for. See also readme inside directories.
    
    * [conf](https://github.com/EU-OSHA/osha-website/tree/master/conf)
     * Project specific configuration files
    * [docroot](https://github.com/EU-OSHA/osha-website/tree/master/docroot)
     * Drupal root directory
    * [drush](https://github.com/EU-OSHA/osha-website/tree/master/drush)
     * Contains project specific drush commands, aliases, and configurations.
    * [results](https://github.com/EU-OSHA/osha-website/tree/master/results)
     * This directory is just used to export test results to. A good example of this
       is when running drush test-run with the --xml option. You can export the xml
       to this directory for parsing by external tools.
    * [scripts](https://github.com/EU-OSHA/osha-website/tree/master/scripts)
     * A directory for project-specific scripts.
    * [test](https://github.com/EU-OSHA/osha-website/tree/master/tests)
     * A directory for external tests. This is great for non drupal specific tests
     such as selenium, qunit, casperjs.
    * [.gitignore](https://github.com/EU-OSHA/osha-website/blob/master/.gitignore)
     * Contains the a list of the most common excluded files.
    * [modules/contrib](https://github.com/EU-OSHA/osha-website/tree/master/docroot/sites/all/modules/contrib)
     * A directory for contributed modules.
    * [modules/osha](https://github.com/EU-OSHA/osha-website/tree/master/docroot/sites/all/modules/osha)
     * Project specific custom module
    * [sites/all/themes/osha_admin](https://github.com/EU-OSHA/osha-website/tree/master/docroot/sites/all/themes/osha_admin)
     * Project specific backend theme
    * [sites/all/themes/osha_frontend](https://github.com/EU-OSHA/osha-website/tree/master/docroot/sites/all/themes/osha_frontend)
     * Project specific frontend theme
     
* ### Custom modules

    **All custom modules divided into 3 groups:**
    
    #### Base modules
    
    Name | Description
    ---------------------| --------------------------
    osha_breadcrumbs | Breadcrumbs rules
    osha_authentication | LDAP authentication support
    osha_blocks | Content Blocks
    osha_content | No Translation functionality
    osha_menu | Main and Footer Menus
    osha_migration | Migrate data from the old website  
    osha_search | Search customizations
    osha_sitemap | Sitemap for xmlsitemap
    osha_sites_migration | Migrating content from other OSHA websites
    osha_taxonomies | Project Specific Taxonomies
    osha_workflow | Custom Workflow Moderation
[Edit this page](https://github.com/scovitin-vsevolod/test_md/edit/master/readme.md)
