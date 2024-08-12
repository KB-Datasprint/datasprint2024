This is a description of the different folders and files.

The folder "kb_xml_files" contains xml files with metadata about historical material from The Royal Danish Library.
The Xml files originally originate from data from the "marc records" found in the library system. 
The data in the "marc records" consists of numerical codes that do not make sense to people outside the library.

Description of numerical codes.

    008 - a language_tag.
    041 - an additional language_tag. It occurs, for example, when 008 is taken equal to 'mul'.
    096 - There are several fields in 096.
    100 - author tag 1
    198 - (300 + 500 + 505 fields that are mapped together) is a field with various metadata
    245 - title field
    260 - place of publication, publisher and year of publication
    650 - subject field1.
    651 - subject field2
    653 - subject field3
    084 - subject field4
    700 - author tag 2 (if not content in 100 and sometimes there is data in both fields)


The file "From xml to csv" is written in jupyter notebook. 
The file contains a short description of the various numerical codes, 
an example of how the xml files in the folder "kb_xml_files" can be loaded into a Pandas dataframe using Python; 
and an example of how to build a new data frame consisting of metadata about historical Danish literature.


The folder "kb_csv_files" contains csv files with metadata extracted from the xml files in the folder "kb_xml_files" 
using a script similar to the script in the notebook "From xml to csv".
Their are two kinds of file names i the folder. 
The first is "KB_metadata_(n)". These holds all records from the corresponding xml file.
The second is "KB_metadata_dan(n)". These holds only those records from the corresponding xml file, 
that holds the value 'dan' in the language column.

The file "From multiple csv files to one csv file" is a jupyter notebook file, and an example on how to combine 
the multiple csv files that are stored in the folder "kb_csv_files" into a larger csv file. 
This would often be easier to work with the data when it is aggregated into one larger file.

In the folder "Kb_metadata_set" two files can be found. The files are produced by the script 
"From multiple csv files to one csv file".

The file "Filter and clean" is a jupyter notebook that gives an example on how to filter and clean the 
relative raw data that is stored in the file "kb_metadata_set_dan_raw.csv" that is in the folder "Kb_metadata_set".

The folder "kb_filtered_datasets" contains one csv file that is the data that have be manipulated by the script in the 
"Filter and clean" notebook.

The folder "openRefine_projects" contains two files; 1. "openrefine_operation_history.txt" and 2. "kb_metadata_dan_filtered_openrefine_v_1.csv".
The first is the operation history made in OpenRefine on the file "kb_metadata_set_dan_raw.csv". When the file is opened in OpenRefine, 
the operation history can be added to preform a great deal of cleaning to the dataset. The second file is the result of the operation history.

Much more can be done to tidy up the dataset even more. For example can further cleaning be added to the columns "author_st" and title, 
and the column sub_4 can be enriched. 