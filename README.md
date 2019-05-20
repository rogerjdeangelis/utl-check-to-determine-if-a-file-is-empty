# utl-check-to-determine-if-a-file-is-empty
Check to determine if a file is empty
    Check to determine if a file is empty

    related to
    https://tinyurl.com/y65uss8w
    https://communities.sas.com/t5/SAS-Programming/Loop-through-files-in-folder-and-import-if-not-empty/m-p/560206

    I think Paul Dorfman first proposed this. I lost the link?
    Paul Dorfman
    sashole@bellsouth.net

    * create empty file;
    data _null_;
      file "d:/txt/empty.txt";
    run;quit;

    data _null_ ;
     infile "d:/txt/empty.txt" end = empty ;
     call symputx("empty",empty); /* 1 if empty */
    run;
    %put %sysfunc(ifc(&empty,file is empty,file is not empty));;
