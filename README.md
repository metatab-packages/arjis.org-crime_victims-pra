# San Diego Crime Incidents with Victim Descriptions

There are important national conversations going on about criminal justice
reform, aligning resources towards prevention and community support rather than
primarily for policing, and calls to Defund or Abolish the Police. These are
all valuable discussions about the communities in which we want to live. An
important voice in that conversation is the voice of victims of crime. The data
below is a complete data set for victims of violent crime from ARJIS (Automated
Regional Justice Information System) for San Diego County, the nation's fifth
largest County, from 2016 through 2020. The complete data set, a cleaned
version of the data, a data dictionary, the Public Records Act request on which
the data was based and several maps are provided for review. A full
conversation requires diverse voices and will help ensure that resources are
realigned in a way that furthers the dual aims of equity and safety in our
communities. 

The file has multiple rows per incident, one for each suspect or
victim. The primary key ``pk`` links records together into a single crime incident. 

This package provides the datasets as CSV files. You can also get the Excel source files for these CSVs, 
and the Excel file originally returned by ARJIS:

* [Processed Dataset](http://ds.civicknowledge.org.s3.amazonaws.com/sandag.org/OPCrimeVictims/Omar%20Passons%20-%20SDCounty_CrimeData_Jan16_Jul20.xlsx). Excel. This is the dataset used to generate this data package
* [Original Source Dataset](http://ds.civicknowledge.org.s3.amazonaws.com/sandag.org/OPCrimeVictims/Omar%20Passons%20-%20second_DataExtract_Omar_Passons.xlsx). Excel. Original, unprocessed dataset, ARJIS’ response to the PRA. This dataset is an Excel file with one tab per year.


## Processing

The resources in this pacakage have been converted from Excel format to CSV, and the
mixed-case column names are all lowercased. For the Excel file source, as it was 
recieved by the San Diego Regional Data Library, see the [References Section](#references).

* dates are converted to ISO format
* Created "year" field
* Deleted MACRStatus from years 2017-2020
* Combined years into 1 file
* Deleted partial August cases to have complete month
* Deleted 2 ARJIS and 1 DA as AGENCY records
* Deleted incident type (all were crime case), highcharge (all were 1) and  role (all were incident)
* ALLYRS_NOSUSP includes only victims, victim/witnesses and blank (property?) in the person role
* UNIQUECASE includes unique case numbers (no matter how many victims)

ALLYEARS data has 676,244 records/ ALLYRS_NOSUSP has 402,397 records with 312,089 unique cases

Of the 312,089 cases, 5% (16,765) don't have a block number and 2% (5,025) don't have a ZIP (with another 1-2% with a ZIP not in SD County).
