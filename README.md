# metis-language-normalization

This project provides a tool for normalizing language related metadata, such as dc:language properties. The tool was designed after an investigation of how the dc:language property was being used by data providers of Europeana.

The project provides a normalization tool that is able to recognize language names in all European languages, and the codes of the ISO-639 family of standards.
The tool has been designed to suport the integration into Metis, but without dependencies of the Metis framework. It can be used through:
- A Java class (provided in a .jar package)
- A REST API (the project contains the implementation as a REST service, as well as a corresponding Client for networked Java applications)

The tool implements an matching algorithm that makes extensive use of the Languages Name Authority List (NAL) published in the European Union Open Data Portal (https://open-data.europa.eu/en/data/dataset/language)

The normalized language output of the tools, can be configured for ISO-639-1 language codes (currently, the standard adopted by Europeana), ISO-639-2r, ISO-639-2t, ISO-639-3 (with limititations) and to the Languages NAL.


## Results from the application in Europeana 

In May 2016, the language normalization methods implemented in this tool were tested on the complete Europeana dataset. 				
The analysis of the presence of ISO-639 familiy of  language codes  in dc:language values within the Europeana dataset is shown in the following table:				

|                                          | ISO-639-1 codes | Other ISO-639 family codes | Other values |   Total    |
|:----------------------------------------:|:---------------:|:--------------------------:|:------------:|:----------:|
| **dc:language property values in Europeana** |    23,988,536   |          5,485,168         |   9,792,054  | 39,265,758 |
|       **(percentage of total values)**       |      (61.1%)     |            (14.0%)           |     (24.9%)    |   (100.0%)  |

The second table, shown below, presents the number of dc:language values that can be normalized by applying the string matching techniques implemented in this tool. The table contains the number of values that can be obtained with each of the string matching methods, and the confidence we assigned to the method. The different matching techniques address several types of language codes and names, but, underlying their algorithms, is a core vocabulary of languages. This vocabulary contains all ISO language codes and language names, in all european languages. It is the the Languages Name Authority List (NAL) published in the European Union Open Data Portal  - https://open-data.europa.eu/en/data/dataset/language				

|                     Description of normalization                     | Confidence Level | Normalization to ISO-639-1 | Normalization to Languages NAL |
|:--------------------------------------------------------------------:|:----------------:|:--------------------------:|:-----------------------------:|
|  Matching with a code from ISO-639-1 (currently in use at Europeana) |  Almost certain  |         23,988,536         |           23,988,536           |
|                        Match with any ISO code                       |  Almost certain  |          4,200,398         |            5,485,168           |
|      Match with language name in any language (full field value)     |     Very high    |          3,329,964         |            3,337,461           |
| Match by name in any language or ISO code (words within field value) |       High       |           768,733          |             771,472            |
|             **Total number of values that can be normalized**           |         -        |         **32,287,631**         |           **33,582,637**           |
|                     **(percentage of total values in Europeana)**                     |         -        |           **(82.23%)**           |             **(85.53%)**             |
