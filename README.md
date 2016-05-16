# metis-language-normalization

This project provides a tool for normalizing language related metadata, such as dc:language properties. The tool was designed after an investigation of how the dc:language property was being used by data providers of Europeana.

The project provides a normalization tool that is able to recognize language names in all European languages, and the codes of the ISO-639 family of standards.
The tool has been designed to suport the integration into Metis, but without dependencies of the Metis framework. It can be used through:
- A Java class (provided in a .jar package)
- A REST API (the project contains the implementation as a REST service, as well as a corresponding Client for networked Java applications)

The tool implements an matching algorithm that makes extensive use of the Languages Name Authority List (NAL) published in the European Union Open Data Portal (https://open-data.europa.eu/en/data/dataset/language)

The normalized language output of the tools, can be configured for ISO-639-1 language codes (currently, the standard adopted by Europeana), ISO-639-2r, ISO-639-2t, ISO-639-3 (with limititations) and to the Languages NAL.
