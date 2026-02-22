# Workshop Computational access to digital collections - University of Strathclyde

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/hibernator11/workshop-notebooks-scotland-wikidata/HEAD)

This is a colletion of Jupyter Notebooks used for a workshop in collaboration with the [University of Strathclyde, MSc Information and Library Studies, Library Technology and Systems](https://www.strath.ac.uk/courses/postgraduatetaught/informationlibrarystudies).

These examples explore the extraction of Collections as data from Wikidata according to different topics and institutions.

<img width="30%" src="https://www.strath.ac.uk/media/1newwebsite/webteam/logos/crest-jubilee-390x60.svg">

## Authors

- Gustavo Candela, University of Alicante
- Milena Dobreva, University of Strathclyde

Note that in previous years, another project was used as training material: https://github.com/hibernator11/workshop-notebooks-scotland

## Examples provided
- Hello World - [HelloWorld.ipynb](notebooks/HelloWorld.ipynb)
- Extracting authors from the National Library of France - [wikidata-bnf-example.ipynb](notebooks/wikidata-bnf-example.ipynb)
- Extracting authors related to the movement Spanish Golden Age from the Biblioteca Virtual Miguel de Cervantes - [wikidata-bvmc-example.ipynb](notebooks/wikidata-bvmc-example.ipynb)
- Extracting artists from Museo el Prado - [wikidata-prado-example.ipynb](notebooks/wikidata-prado-example.ipynb)

All of them retrieve the data using a SPARQL query and store the data in a JSON file.

We can also create visualisations with Wikidata. For example, using a selection of 100 artists from El Prado and nacionalities. You can run the example here [https://w.wiki/Hx2M](https://w.wiki/Hx2a)

```
#defaultView:Map
SELECT DISTINCT ?author ?authorLabel (SAMPLE(?image) as ?img) ?coord
WHERE {   
       ?author wdt:P5321 ?idprado.
       ?author wdt:P27 ?country .
       ?country wdt:P625 ?coord.
       OPTIONAL {?author wdt:P18 ?image .}      
    SERVICE wikibase:label { bd:serviceParam wikibase:language "es" }
} GROUP BY ?author ?authorLabel ?coord
LIMIT 100
```

<img src="https://github.com/hibernator11/workshop-notebooks-scotland-wikidata/blob/main/map-prado.png?raw=true" width="60%">


## Tasks

1. Review the notebooks provided. Check how the SPARQL queries can be executed and the data retrieved. You can also try using https://query.wikidata.org
2. Using the code provided, would you be able to create a new notebook and retrieve 100 artworks from El Prado? Please, note that you will have to use the property [wdt:P8905](https://www.wikidata.org/wiki/Property:P8905).
3. Try to improve the SPARQL queries provided (e.g., include new properties such as place of birth or nickname). Would you be able to use another properties from other institutions? How can you find them?
4. Try to create some notes as a documentation of the process.
5. Run and explore the notebooks provided in this project: https://github.com/hibernator11/Spanish-Civil-War-KGs

## Licence
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Licence Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/80x15.png" /></a><br />Content is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International license</a>.

Please, note that the datasets used in this project have separate licences.

## Acknowledgments
This work was possible thanks to many researchers, labbers, librarians and initiatives from around the world. First of all, I would like to thank Milena Dobreva for inviting me to give this workshop. This work would not have been possible without the help and inspiration of the [International GLAM Labs Community](glamlabs.io), the [Collections as data](https://collectionsasdata.github.io/) initiative, the [National Library of Scotland](https://data.nls.uk/), [Wikimedia Spain](https://wikimedia.es/), the [GLAM Workbench](https://glam-workbench.net/) and [DARIAH-EU](https://www.dariah.eu/).

## References
- https://data.nls.uk/projects/the-national-librarians-research-fellowship-in-digital-scholarship-2022-23/
- https://glam-workbench.net/
- https://github.com/hibernator11/notebook-EADH-2021-workshop
- Candela, G., Chambers, S., & Sherratt, T. (2023). An approach to assess the quality of Jupyter projects published by GLAM institutions. Journal of the Association for Information Science and Technology, 74(13), 1550–1564. https://doi.org/10.1002/asi.24835
- Candela, G. (2023). Towards a semantic approach in GLAM Labs: The case of the Data Foundry at the National Library of Scotland. Journal of Information Science. https://doi.org/10.1177/01655515231174386
- Candela, G., Gabriëls, N., Chambers, S., Dobreva, M., Ames, S., Ferriter, M., Fitzgerald, N., Harbo, V., Hofmann, K., Holownia, O., Irollo, A., Mahey, M., Manchester, E., Pham, T.-A., Potter, A., & Van Keer, E. (2023). A checklist to publish collections as data in GLAM institutions. Global Knowledge, Memory and Communication. Advance online publication. https://doi.org/10.1108/GKMC-06-2023-0195
- https://github.com/hibernator11/hdh-compartir-pantalla-2023
- https://wikimedia.es/abiertas-las-inscripciones-para-wikidata-en-el-contexto-glam-ii-patrimonio-conectado-en-el-museo-del-prado/
