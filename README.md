# hetarchief2lod

Script that builds a CSV and RDF dataset of the metadata from [hetarchief.be](http://hetarchief.be).

You can download the metadata from the data folder and is freely available under CC0.

OCR (Optical Character Recognition) and the images are available under a disclaimer. These are only available on the website. (but will be available as raw data in the future).

## Dataset CSV

Column  | Info
------------ | -------------
viaa_uri | VIAAs unique identifier
title | Title of the newspaper or newspaperpage
type | 'newspaper' or 'newspaperpage'
date_created | 'Date of creation/publishing'
language | 'EN', 'FR', 'NL' or 'DE'
abraham_id | Identifier of the Abraham catalogue
abraham_uri | URI of the Abraham catalogue
see_also_hetarchief | Link to hetarchief.be
original_carrier_id | Original carrier ID of the Content Partner
content_partner | Organisation that has the carrier
sub_content_partner | Sub organisation
rights_owner | Owner of the IP

## Dataset RDF

The RDF triples contain the same data as the CSV, including tags of [DBpedia Spotlight](http://www.dbpedia-spotlight.org/). These tags are automatically annotated entities from the OCR text. Note that there's a high percentage of wrong tags because of the bad quality of OCR and different time period.

## Linked Data Fragments

The RDF representation is also available through a Triple Pattern Fragments [interface](http://linkeddatafragments.org). The interface is available at [http://linkeddatafragments-qas.viaa.be/hetarchief](http://linkeddatafragments-qas.viaa.be/hetarchief). Note that this is still in beta.

With this technology, federated queries are possible. Click [here](http://client.linkeddatafragments.org/#datasources=http%3A%2F%2Ffragments.dbpedia.org%2F2016-04%2Fen;http%3A%2F%2Flinkeddatafragments-qas.viaa.be%2Fhetarchief&query=SELECT%20%3Fnewspaper%20%3Fartist%20%20%3Ftag%20%3Fhetarchief%0AWHERE%20%7B%0A%3Fartist%20dc%3Asubject%20%3Chttp%3A%2F%2Fdbpedia.org%2Fresource%2FCategory%3ABelgian_war_artists%3E%20.%0A%3Fartist%20owl%3AsameAs%20%3Ftag%20.%0A%3Fnewspaper%20%3Chttp%3A%2F%2Fwww.bbc.co.uk%2Fontologies%2Fcreativework%23tag%3E%20%3Ftag%20.%0A%3Fnewspaper%20%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23seeAlso%3E%20%3Fhetarchief%0A%7D) for an example.
