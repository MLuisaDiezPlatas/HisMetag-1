# HisMeTag


## Description

HisMetag is a Java tool for the identification and tagging of place names within Medieval Spanish texts that combines lexical, syntactic and semantic analysis with NLP technologies.
The implementation of this tool is under the phase of development, test and training.

The recognition phase has been carried out based on two kinds of procedures:

1.	Identification of terms takes into account its context. As a consequence, a hierarchy of contexts with polymorphic functions has been defined and implemented. Tokenizers and ngramms are used in the processes. This feature allows the recognition of different categories of names. The detection of ambiguities is also feasible. The tool can resolve those ambiguities. Complex structures, nominal phrases, lists of terms, terms with appositions and others are computed. Gazetteers and dictionaries for both ancient and modern names are used for identification functions.

2.	Generation of variants of terms that have not been found in gazetteers and dictionaries. Morphological rules are applied to them for its identification, according to the evolution of Spanish language from Latin to modern Spanish language.

## Gazetteers and dictionaries

1.	Gazetteer of Pleiade,s which  is updated in every execution through a Python script.
2.	Gazetteer of Geonames. The queries against  this gazetteer are  not a priority over the others since it handles modern terms, but it is helpful in terms of  resolution of variants.
3.	Available dictionary in Freeling for Old Spanish.
4.	Medieval dictionary which is fed from the tool.

## Outputs obtained

1.	A XML-TEI or a JSON file with detected and tagged entities.
2.	A csv and JSON files for each document processed with the list of terms identified. These files are located in the output folder. The files with AllTerms suffix contain all the terms, for both place names and, also, entities and people's names; and the one with the prefix named Placenames, which contains only the place names found and/or proposed.
3.	The new generated terms are incorporated into the medieval gazetteer. The Medieval gazetteer is in the resources/dataFiles folder called medieval-data.txt. A new-medieval-data file that contains the terms proposed, according to the context but they have not localized in any gazetteer or dictionary.
4.	A medieval-gazeteer.csv file, which contains all the terms that they have currently been identified in the texts.
5.	The list of new names found or proposed are incorporated to the new-proper-names.txt file, and a list of names of found saints (that allow us to resolve the ambiguity of place names), in the saint-names.txt file. Both of them are located at the resources/dataFiles folder.


## Nomenclatures used for the classification of identified terms

Terms
•	CN-common name
•	PN-proper name
•	PPN-proposed proper name
•	STN-saint name
•	PSTN-proposed saint name
•	APN-ambiguous proper name
•	ACN-ambiguous common name
•	PLN-place name
•	PPLN-proposed place name
•	APLN-ambiguous place name
•	UN-unidentified

Types of terms according to recognition

•	AT-ambiguous term
•	FT-found term
•	GENT-generated term
•	INI-unidentified term
•	PPT-proposed term

Actions to be taken

•	FOUND-term found does not require verification
•	VALIDATE-validation of the identified category is required
•	UNIDENTIFIED-term without identified category

## Acknowledges

The software was developed at LINHD-UNED by Ma Luisa Diez Platas and presented at the Linked Pasts II Symposium,15-16 December, 2016, organized by Pelagios Commons and LINHD-UNED.  This tool has been developed thanks to the research projects Pelagios Commons microgrant (2016) for Medieval Iberia project, coordinated by Gimena del rio Riande, Acción Europa Investiga EUIN2013-50630: Repertorio Digital de Poesía Europea (DIREPO) and FFI2014-57961-R. Laboratorio de Innovación en Humanidades Digitales: Edición Digital, Datos Enlazados y Entorno Virtual de Investigación para el trabajo en humanidades, funded by MINECO and led by Elena González-Blanco, and the Starting Grant research project: Poetry Standardization and Linked Open Data: POSTDATA (ERC-2015-STG-679528), funded by European Research Council (ERC) under the European Union´s Horizon 2020 research and innovation programme, (http://postdata.linhd.es/). 
With the collaboration of Alfonso Cuesta Alcantara of the In2AI company. [(Changes by In2AI)](CHANGES.md)

## How to run

### DOCKER
In the root directory run
```
docker-compose up
```

### With Maven and Tomcat
If the target folder is not in the Hismetag directory, run in the Hismetag directory the Maven command
```
mvn package
```
Then copy the file .war in the target folder into de Tomcat webapps folder and run Catalina

