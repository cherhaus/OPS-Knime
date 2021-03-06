OPS-Knime
=========

OPS-Knime is a project devoted to ease the process of including <a href="http://dev.openphacts.org">OpenPHACTS services </a> into the <a href="http://www.knime.org/">Knime</a> workflow engine.
where:<br/>
<ul><li>OpenPHACTS reduces the barriers to drug discovery in industry, academia and for small businesses. </li>
<li>
Knime offers a workflow system by implementing a low-barrier visual programming environment for researchers dependent on data and statistical data-crunching methods/algorithms.
</li> 
</ul>
In other words: <b>OpenPHACTS</b> gives pharmacologists easy access to a wide range of data relevant to their research and <b>Knime</b> allows scientists to partially automate their research workflows which
are part of their research process.   
The more generic purpose of OPS-Knime is to make it easier to integrate Restful services in Knime via some utility nodes that are able to deal with SWAGGER files and JSON files.



KNIME-UTILS: SWAGGER & JSON
----------
The <a href="http://dev.openphacts.org">OpenPHACTS services</a> are accessible via HTTP-GET .
These services are described in <a href="https://developers.helloreverb.com/swagger/">SWAGGER</a>, and rendered by <a href="http://www.3scale.net/">3scale</a> into convenient, human-readable html documentation. 
The latest swagger file for the OpenPHACTS version 1.3 can be found <a href="https://raw.github.com/openphacts/OPS_LinkedDataApi/1.3.0/api-config-files/swagger.json">here </a>, and the visualisation is <a href="https://dev.openphacts.org/docs/1.3"> here </a>
SWAGGER is an easy way to describe REST services. 
It contains all the necessary information needed to be able
to understand the purpose and how to technically invoke  services that are provided. For example the address of the server, the path to the services and the parameters
that the services require or which are optional to fine-tune the desired functionality of the service.


The OPS-Knime project is mainly concerned to give the Knime community easy access to the OpenPHACTS services. 


<ul><li><b>JSON_to_Knime</b><br/>

This node parses the JSON from a given url to a KNIME table by a recursive traversal through the JSON objects and JSON arrays. The column names
are a concatenation of the keys found when walking through the hierarchical path. The resulting tables looks quite similar to an online JSON-to-CSV tool
found <a href="http://json-csv.com"> here </a>.
 
</li>
<li><b>SWAGGER_to_ServiceTemplates</b><br/>
The combination of these two KNIME nodes provides access to REST services accessible via HTTP-GET described by a SWAGGER file.
</li></ul>

#Installation

To run the Open PHACTS nodes you need to install both the JSON+SWAGGER nodes and the metanodes. 

Installing the JSON and SWAGGER nodes
------------
* Download "org.openphacts.utils.json_1.0.0.jar" and put it in the plugins folder of your KNIME installation



OpenPHACTS Services (metanodes)
----------
KNIME allows workflows to be wrapped as "meta nodes". In the "metanodes.zip" the functionality of the Open PHACTS platform is exposed by wrapping SWAGGER+JSON nodes (described below)
The more skilled user can 'zoom in' into the meta-node and change the settings according
to his/her preferences.

The following metanodes are implemented and have an example workflow:
<ul><li>OPS_activity_types</li><li>OPS_ChEBI_class_pharmacology_count</li><li>OPS_ChEBI_ontology_class_pharmacology_paginated</li><li>OPS_chemical_structure_exact_search</li><li>OPS_chemical_structure_similarity_search</li><li>OPS_chemical_structure_substructure_search</li><li>OPS_compound_information</li><li>OPS_compound_pharmacology_paginated</li><li>OPS_data_sources</li><li>OPS_enzyme_pharmacology_count</li><li>OPS_enzyme_pharmacology_paginated</li><li>OPS_get_ChEBI_ontology_class</li><li>OPS_get_ChEBI_ontology_class_members</li><li>OPS_get_ChEBI_ontology_root_classes</li><li>OPS_get_concept_description</li><li>OPS_get_enzyme_classification_class</li><li>OPS_get_enzyme_classification_class_members</li><li>OPS_get_enzyme_classification_root_classes</li><li>OPS_InChI_key_to_URL</li><li>OPS_InChI_to_URL</li><li>OPS_map_free_text_to_concept_URL_by_semantic_tag</li><li>OPS_map_URL</li><li>OPS_pathway_information</li><li>OPS_search_freetext</li><li>OPS_SMILES_to_URL</li><li>OPS_target_information</li><li>OPS_target_pharmacology_count</li><li>OPS_target_pharmacology_paginated</li><li>OPS_units_for_activity_type</li></ul>

Installing the OpenPHACTS meta nodes
----------
Perform the previous step and do the following:
* Download "metanodes.zip" and unpack it 
* Open your KNIME environment
* Goto "file>>import workflow..."
* select from the unpacked zip the workflow you need




Development - Source
----------
The source code of the plugins are in the folder "OPS-Knime" folder which can be checked out as
a java project in Knime-Eclipse.

The source of the metanodes is in the 'metanodes' directory

TODO
-------------
* more nodes
* better nodes

for any questions or feedback, please send a mail to rm.siebes'''''AT'''''few.vu.nl
