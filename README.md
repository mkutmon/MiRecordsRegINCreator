MiRecordsRegINCreator
=====================

How to run the miRecords RegIN Creator:

**1. Download current miRecords target information**

* Go to [http://mirecords.biolead.org/download.php](http://mirecords.biolead.org/download.php) 
* Download the latest release of miRecords.
* Open the .xls file in Excel and save it as a comma-separated file (.csv) with tab as the delimiter. 

***

**2. Download the identifier mapping databases from BridgeDb**

* Download the database for gene products for the relevant species from [http://bridgedb.org/data/gene_database/](http://bridgedb.org/data/gene_database/)
  * Hs_Derby_xxxxxxxx.bridge = Homo sapiens
  * Mm_Derby_xxxxxxxx.bridge = Mus musculus
  * Rn_Derby_xxxxxxxx.bridge = Rattus norvegicus
  * ...
* Download the microRNA mapping database (maps from miRBase id to accession) from [https://github.com/mkutmon/rin-creation/blob/master/mirna-mapping/mirbase-v19.bridge](https://github.com/mkutmon/rin-creation/blob/master/mirna-mapping/mirbase-v19.bridge)

***

**3. Download the conversion tool**

* In the releases directory you can find the latest version of the miRecords conversion tool.

***

**4. Run the tool with all required arguments**

```
java -jar MiRecordsRegINCreator-v1.0.0.jar -i miRecords_version4.csv --bridgeDbFile Hs_Derby_20130701.bridge mirbase-v19.bridge -o output.xgmml --organism "Homo sapiens" -v "2013-04-27"
```

* _-i_ -> input file downloaded in step 1
* _--bridgeDbFile_ -> list both bridge files downloaded in step 2 (adapt if you have another version or species)
* _-o_ -> output file, should always end with .xgmml
* _--organism_ -> defines which interactions should be extracted
* _-v_ -> database version - which version of miRecords are you using
