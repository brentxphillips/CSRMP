# Sector Code Classifier

![activity code](https://github.com/brentxphillips/CSRMP/blob/main/description_sector.png)

Humanitarian organizations use **sector codes** to classify aid activities. This project will try to build a **Sector Code Classifier** able to assign sector codes to aid activities based mainly on activity description information. Two child-projects link to this parent project: [IATI Descriptions]() and [Sector Codes]().



### Background

IATI is an open data sharing standard and reporting framework widely used across the humanitarian community for reporting aid activities that is mandated by many government development agencies.

A large percentage of IATI reported activities contain coded sector references clarifying the purpose of individual activities. Sector codes refer to codes listed in standardized vocabularies curated by different initiatives, the most commonly used being [OECD-DAC 5 digit purpose codes](https://iatistandard.org/en/iati-standard/203/codelists/sector/). Excluding the problem of their differing taxonomies, comparing activities using sector codes can help voice applications use IATI data to answer complex queries posed by humanitarian actors.

### Project Focus

The project will develop and use IATI data to train and test a classifier able to assign hybrid purpose and activity codes curated by [AidData](https://www.aiddata.org/) to activities through mainly comparing keywords and phrases found in activity descriptions to those found in sector code descriptions. Operationally, the classifier will be able to verify sector codes found in activity files, assign codes to actvities missing sector information and make activities coded using different vocabularies sector-comparable.

### Research Problem

From a research perspective, the project is interested in how to approach building a sector classifier, how the classifier can be packaged for use at scale by voice applications in conjunction with other classifiers and algorithms and how accurately this project's classifier can perform based on limited keyword and phrase information found in activity **description** and **sector** fields. Whether or not a classifier can be built capable of performing sufficently will help answer whether sector codes can help artificial intelligent applications infer relationships between aid activities and traverse aid activity information, collecting useful information for answering queries.

### Research and Development Steps

Listed below are main steps that the project will carry out:

* The project will store two main datasets in a Google Cloud storage bucket, a CSV file containing activity descriptions taken from some or all of IATI's entire coprus and a CSV file listing sector codes and their respective descriptions.
* Establish all the necessary APIs and endpoints
* Setup a CoLab notebook for the project
* Test accessing data from the datasets via CoLab
* Identify and ready natural language processing tools
* Ready Tensorflow
* Carry-out basic testing and basic classifications to test the sandbox and components
* Develop a way to score classification results based on comparing sector codes assigned by the classifier to actual codes added by authors.
* Begin training and testing the classifier
* Examine where the classifier is failing and then create annotated datasets to use for retraining.
* Incrementally train and improve the classifier and improve training resources

### Outputs

* The project will try to (iterate through basic setup challenges) setup a sandbox to study the classification of aid activity information, useful for this project and others, facilitating subsequent research.
* Generate a basic classification algorithm
* Report on its performance
* Make and collect improvement recomendations


## Project Resources

### Project Data

Data | Storage Bucket
---- | ----
IATI Dataset | https://storage.cloud.google.com/sectordataset/Oxfam_activities.csv
Sector Codes | https://storage.cloud.google.com/sectordataset/aiddata_purpose_codes.csv

### Fields and endpoints

The datasets use these fields and endpoints


## IATI Data and Sector Codes

IATI is a standard and reporting framework developed by the humanitarian communitry through the International Aid Transparency Initiative. Humanitarian and development organizations, grantmakers and other stakeholders piublish to IATI by converting information on aid activities to machine readable XML in compliance with the IATI standard, publish the generated XML files on their own servers and then register matadata to IATI's registry making the information visible to others.

The standard uses hundreds of elements and codelists, making it possible to report aid activities in granular highly structured detail.

### Example IATI File

One activity carried out it Jordan by CAFOD, note the Title, Description and Sector fields:

![file](https://github.com/brentxphillips/CSRMP/blob/main/iati_example.png)

This activity's XML file can be found [here](https://github.com/brentxphillips/CSRMP/blob/main/undpko.xml).

### IATI Data Fields

IATI contains hundreds of parent and child fields. IATI Summary Table: https://iatistandard.org/en/iati-standard/203/activity-standard/summary-table/

### Sector Classification Relevant Fields

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

## AidData Purpose and Activity Fields

Here is a breakdown of the sector code used above, and child codes, provided by AidData. 

![basic health](https://github.com/brentxphillips/CSRMP/blob/main/basic_health.png)

Typically code descriptions are one or more sentences long. Here is an example of a more detailed text:

(images)


