# IATI Data Classifier


IATI Summary Table: https://iatistandard.org/en/iati-standard/203/activity-standard/summary-table/

IATI Fields | Description
---- | ----
Sector | A recognised code, from a recognised vocabulary, classifying the purpose of the activity. Sector MUST EITHER be reported here OR at transaction level for ALL transactions
Vocabulary | An IATI code for the vocabulary (see codelist) used for sector classifications. If omitted, OECD DAC 5-digit Purpose Codes are assumed. It is recommended that OECD DAC 5-digit Purpose Codes are used wherever possible. It is also recommended that if a publisher has its own classification system or systems then the vocabularies 99 or 98 (Reporting Organisation’s own vocabularies) should be used in addition to DAC codes. Publishers using 98 or 99 must also include a narrative in the narrative element. Note that if multiple sector codes are used in multiple vocabularies, then each vocabulary’s percentages should add up to 100. Sector can also be reported at the transaction level rather than the activity level. Sector must only be reported at EITHER transaction level OR activity level.
Vocabulary-uri | The URI where this vocabulary is defined. If the vocabulary is 99 or 98 (reporting organisation), the URI where this internal vocabulary is defined. While this is an optional field it is STRONGLY RECOMMENDED that all publishers use it to ensure that the meaning of their codes are fully understood by data users.
Code | The code for the sector.

x

Data | Storage Bucket
---- | ----
IATI Dataset | https://storage.cloud.google.com/sectordataset/Oxfam_activities.csv
Sector Codes | https://storage.cloud.google.com/sectordataset/aiddata_purpose_codes.csv

x
![https://github.com/brentxphillips/CSRMP/blob/main/iati_example.png]
x
