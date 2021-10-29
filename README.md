# Sector Code Classifier

Humanitarian organizations use **sector codes** to classify aid activities. This project will undertake to build a **Sector Code Classifier** able to assign sector codes to aid activities based mainly on activity description information. Two child-projects link to this parent project: [IATI Descriptions]() and [Sector Codes]().

![activity code](https://github.com/brentxphillips/CSRMP/blob/main/activity_code.png)

### Background

IATI is an open data sharing standard and reporting framework widely used across the humanitarian community for reporting aid activities that is mandated by many government development agencies.

A large percentage of IATI reported activities contain sector code information clarifying the purpose of individual activities. Sector codes refer to codes listed in standardized vocabularies curated by different initiatives. Excluding the problem of their differing taxonomies, comparing activities using sector codes can help voice applications process and answer complex queries posed by humanitarian actors.

## Project Focus

The project will use IATI data to train and test a classifier able to classify and assign hybrid purpose and activity sector codes curated by [AidData]() to activities through mainly comparing keywords and phrases found in activity descriptions to those found in sector code descriptions.



### Research Problem

Centrally, (from a processing perspective) the project is interested in (build approaches) and how accurately a classifier can perform, based on limited code descritive information and actvity descriptive text. Can the classifier infer or match sector code chapters and then individule parent codes and child codes? At heart the project is interested in information traversal and relationship determinations and the use of codes to add relationships.

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
