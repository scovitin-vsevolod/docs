---
title: ODP CKAN - EU Open Data Portal CKAN client
---
#  ODP CKAN - EU Open Data Portal CKAN client


<small class="github">[eea.odpckan](https://github.com/eea/eea.odpckan)</small>

  * read messages from the RabbitMQ service
  * interrogate [SDS](http://semantic.eea.europa.eu) and retrieve full data about the specified datasets in JSON format
  * updates the [EU Open Data Portal (ODP)](https://open-data.europa.eu/en/data/publisher/eea) using CKAN API

Contents

  * Base docker image
  * Source code
  * Usage via Docker
  * Usage w/o Docker
  * Example usage
  * EEA main portal use case
    * RabbitMQ message example
  * Copyright and license
  * Funding

##  Base docker image

>   * [hub.docker.com](https://registry.hub.docker.com/u/eeacms/odpckan)

>

##  Source code

>   * [eea.odpckan](http://github.com/eea/eea.odpckan)

>

##  Usage via Docker

Start the odpckan client with the following command:

    
    
    $ sudo docker run -d \
                      -e RABBITMQ_HOST=http://rabbitmq.apps.eea.europa.eu \
                      -e RABBITMQ_PORT=5672 \
                      -e RABBITMQ_USERNAME=client \
                      -e RABBITMQ_PASSWORD=secret \
                      -e CKAN_ADDRESS=https://open-data.europa.eu/en/data \
                      -e CKAN_APIKEY=secret-api-key \
                      -e SERVICES_EEA=http://www.eea.europa.eu/data-and-maps/data \
                      -e SERVICES_SDS=http://semantic.eea.europa.eu/sparql \
                      -e SERVICES_ODP=https://open-data.europa.eu/en/data/publisher/eea \
                      -e SDS_TIMEOUT=60 \
                      -e CKANCLIENT_INTERVAL="0 */3 * * *" \
                      -e CKANCLIENT_INTERVAL_BULK="0 0 * * 0" \
                      -e  eeacms/odpckan
    

For docker-compose orchestration see
[eea.docker.odpckan](https://github.com/eea/eea.docker.odpckan).

##  Usage w/o Docker

Dependencies

  * [Pika](https://pika.readthedocs.org/en/0.10.0/) a python client for RabbitMQ
  * [ckanapi](https://github.com/ckan/ckanapi) a python client for [CKAN API](http://docs.ckan.org/en/latest/contents.html) to work with ODP
  * [rdflib](https://github.com/RDFLib/rdflib/) a python library for working with RDF
  * [rdflib-jsonld](https://github.com/RDFLib/rdflib-jsonld) JSON-LD parser and serializer plugins for RDFLib

Clone the repository:

    
    
    $ git clone https://github.com/eea/eea.odpckan.git
    $ cd eea.odpckan
    

Install all dependencies with pip command:

    
    
    $ pip install -r requirements.txt
    

##  Example usage

ODP CKAN entry point that will start consume all the messages from the queue
and stops after. This command can be setup as a cron job.:

    
    
    $ python app/ckanclient.py -d
    $ #debug mode: creates debug files for dataset data from SDS and ODP, before and after the update
    
    $ python app/ckanclient.py
    $ #default/working mode: reads and process all messages from specified queue
    

Inject test messages (default howmany = 1):

    
    
    $ python app/proxy.py howmany
    

Query SDS (default url = <https://www.eea.europa.eu/data-and-maps/data/eea-
coastline-for-analysis-1>) and print result:

    
    
    $ python app/sdsclient.py -d
    $ #debug mode: queries SDS and dumps a dataset and all datasets
    
    $ python app/sdsclient.py
    $ #default/working mode: initiate the bulk update
    

##  EEA main portal use case

Information published on [EEA main portal](https://www.eea.europa.eu) is
submitted to the [EU Open Data Portal](https://data.europa.eu).

[![https://raw.githubusercontent.com/eea/eea.odpckan/master/docs/EEA%20ODP%20CKAN%20-%20swimlane%20workflow%20diagram.png](https://raw.githubusercontent.com/eea/eea.odpckan/master/docs/EEA%20ODP%20CKAN%20-%20swimlane%20workflow%20diagram.png)](https://drive.google.com/file/d
/0B-2fZm4-OM0pYmJuY1BsT21IVUU/view?usp=sharing)

The workflow is described below:

  * [EEA CMS](https://www.eea.europa.eu) (Plone)
    
    * content is published
    * CMS content rules are triggered and the following operations are performed:
    
      * a message is added in [RabbitMQ message broker](http://rabbitmq.apps.eea.europa.eu) queue, see example below
      * [SDS](http://semantic.eea.europa.eu) is pinged to update its harvested content
  * [EEA ODP CKAN](https://github.com/eea/eea.odpckan/tree/master/app) client
    
    * CKAN client is triggered periodically via a cron job
    * CKAN client connect to [RabbitMQ message broker](http://rabbitmq.apps.eea.europa.eu) and consumes all the messages from the "odp_queue" queue performing following operations:
    
      * dataset is identified
      * dataset's metadata is extracted from [SDS](http://semantic.eea.europa.eu)
      * using CKAN API, [OPD](http://data.europa.eu/euodp) is updated
      * if issues occur during message processing the message is re queued
  * [EEA ODP CKAN](https://github.com/eea/eea.odpckan/tree/master/app) client (bulk update operation)
    
    * is triggered periodically via a cron job
    * it reads all the datasets from the [SDS](http://semantic.eea.europa.eu)
    * generates update messages in the [RabbitMQ message broker](http://rabbitmq.apps.eea.europa.eu), one message per dataset found

###  RabbitMQ message example

Message:

    
    
    $ update|https://www.eea.europa.eu/data-and-maps/data/eea-coastline-for-analysis-1 |eea-coastline-for-analysis-1
    

Message structure:

    
    
    $ action|url|identifier
    

Action(s):

    
    
    $ create/update/delete
    

##  Copyright and license

The Initial Owner of the Original Code is European Environment Agency (EEA).
All Rights Reserved.

The Original Code is free software; you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the Free
Software Foundation; either version 2 of the License, or (at your option) any
later version.

##  Funding

[European Environment Agency (EU)](http://eea.europa.eu)

[Edit this page](https://github.com/eea/eea.odpckan/edit/master/README.rst)
