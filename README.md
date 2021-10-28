# Sector Code Classifier

Humanitarian organizations use **secor codes** to classify aid activitis, and many codelist (see code lists initiatives have been started). This project aims to build a rudamentry **Sector Code Classifier** able to assign sector codes to aid activities based mainly on activity titles and description text (with the possiblity of other parameters capable of being added), to use to evaluate how to tackle classification, how a classification module can look and function as a plugin and how the base classifier can perform, informing subsiquant training, testing and classification work.

### Application

IATI is an open data sharing framework humanitarian organizations use to report aid activities. A large percentage of aid activities published on IATI include sector code information however many activity files contain missing codes. The project will use IATI data to train and test a classifier able to examine activity description information and assign the activity a classification code, where a code might be missing, and where codes exist, check (rate or other) the accuracy of codes that are provided and assign the activity a main code from a top-level vocabulary in cases where other vocabularies are used.

### Research Problem

Centrally, the project is interested in (build approaches) and how accurately a classifier can perform, based on limited code descritive information and actvity descriptive text. Can the classifier infer or match sector code chapters and then individule parent codes and child codes? At heart the project is interested in information traversal and relationship determinations and the use of codes to add relationships.

### Development Objective

The project hopes to develop or facilitate the development of a sector coding module able to fit within a code-set, and help build the code-set. Core algorithm (code), and a framework or module

## IATI Data Fields

IATI contains hundreds of parent and child fields. IATI Summary Table: https://iatistandard.org/en/iati-standard/203/activity-standard/summary-table/

### Project Relevant Fields

The project is primarily interested in activity **Title**, **Description** and **Sector** fields.

IATI Fields | Description
---- | ----
Title | A short, human-readable title that contains a meaningful summary of the activity. May be repeated for different languages.
Description | A longer, human-readable description containing a meaningful description of the activity. May be repeated for different languages.
Sector | A recognised code, from a recognised vocabulary, classifying the purpose of the activity. Sector MUST EITHER be reported here OR at transaction level for ALL transactions
Vocabulary | An IATI code for the vocabulary (see codelist) used for sector classifications. If omitted, OECD DAC 5-digit Purpose Codes are assumed. It is recommended that OECD DAC 5-digit Purpose Codes are used wherever possible. It is also recommended that if a publisher has its own classification system or systems then the vocabularies 99 or 98 (Reporting Organisation’s own vocabularies) should be used in addition to DAC codes. Publishers using 98 or 99 must also include a narrative in the narrative element. Note that if multiple sector codes are used in multiple vocabularies, then each vocabulary’s percentages should add up to 100. Sector can also be reported at the transaction level rather than the activity level. Sector must only be reported at EITHER transaction level OR activity level.
Vocabulary-uri | The URI where this vocabulary is defined. If the vocabulary is 99 or 98 (reporting organisation), the URI where this internal vocabulary is defined. While this is an optional field it is STRONGLY RECOMMENDED that all publishers use it to ensure that the meaning of their codes are fully understood by data users.
Code | The code for the sector.

Here is a sample CSV file comtaining x number of activities (with defferent vocabularies)

## Example IATI File

One activity carried out it Jordan by CAFOD, note the Title, Description and Sector fields:

![file](https://github.com/brentxphillips/CSRMP/blob/main/iati_example.png)

Here is a breakdown of the sector code used above, and child codes, provided by AidData. 

![basic health](https://github.com/brentxphillips/CSRMP/blob/main/basic_health.png)

Typically code descriptions are one or more sentences long. Here is an example of a more detailed text:

(image)

## Project Data

Data | Storage Bucket
---- | ----
IATI Dataset | https://storage.cloud.google.com/sectordataset/Oxfam_activities.csv
Sector Codes | https://storage.cloud.google.com/sectordataset/aiddata_purpose_codes.csv
