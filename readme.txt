This is a description of different folders with data files and files to handle the data in the folders.

The folders with data are for the moment available for download from this page: https://silo1.sciencedata.dk/themes/deic_theme_oc7/apps/files_sharing/public.php?t=eee6d992b9dd0b9331fc92614274856a&

The folder "kb_xml_files" contains xml files with metadata about historical material from The Royal Danish Library.

The xml files originally originate from data from the "marc records" found in the library system.

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

Of these fields, only the title field (245) is mandatory, the rest of the fields may be incomplete.

The file "From xml to csv" is written in jupyter notebook. 
The file contains a short description of the various numerical codes, 
an example of how the xml files in the folder "kb_xml_files" can be loaded into a Pandas dataframe using Python; 
and an example of how to build a new data frame consisting of metadata about historical Danish literature.


The folder "kb_csv_files" contains csv files with metadata extracted from the xml files in the folder "kb_xml_files" 
using a script similar to the script in the notebook "From xml to csv".

There are two kinds of file names i the folder. 
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
In the file, values ​​containing the text string "code o" are selected from the column "sub_3". "Code o" is linked to a numerical code, that is linked to a historical classification system previously used at The Royal Danish Library. By selecting only those values ​​that have "code o", the data set is reduced significantly; from 275521 rows to 87221 rows.

The folder "kb_filtered_datasets" contains one csv file that is the data that have be manipulated by the script in the 
"Filter and clean" notebook.

The folder "openRefine_projects" contains two files; 1. "openrefine_operation_history.txt" and 2. "kb_metadata_dan_filtered_openrefine_v_1.csv".
The first is the operation history made in OpenRefine on the file "kb_metadata_set_dan_raw.csv". When the file is opened in OpenRefine, the operation history can be added to preform a great deal of cleaning to the dataset. The second file is the result of the operation history.

Much more can be done to tidy up the dataset even more. For example can further cleaning be added to the columns "author_st" and title, and the column sub_4 can be enriched. 
