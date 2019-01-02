# Acadgild-Session-2_Assignment-2.2

5. Problem Statement

1. Read multiple json files into a working directory for further converting into a dataset.

I have files text1, text2, text3 in the directory json.


2.	Parse the following JSON into a data frame

js<-'{
"name": null, "release_date_local": null, "title": "3 (2011)",

"opening_weekend_take": 1234, "year": 2011, "release_date_wide": "2011-09-16", "gross": 59954 }'

3.	Write a script for variable binning using R.

 ANSWERS :
 
1.  

ls <- list("F:\\ACADGILD - Online Course\\1. DATA SETS\\text1.json",
           "F:\\ACADGILD - Online Course\\1. DATA SETS\\text2.json",
           "F:\\ACADGILD - Online Course\\1. DATA SETS\\text3.json")
           
2.

for (i in ls){

  a[i] <- read_json(i, simplifyVector = TRUE)
  
  z[i] <- data.frame( i,row.names = NULL, check.rows = FALSE,
  
                      check.names = TRUE, fix.empty.names = TRUE,
                      
                      stringsAsFactors = default.stringsAsFactors())
                      
3.

library(jsonlite)

library(dplyr)

ls <- list("F:\\ACADGILD - Online Course\\1. DATA SETS\\text1.json",
           "F:\\ACADGILD - Online Course\\1. DATA SETS\\text2.json",
           "F:\\ACADGILD - Online Course\\1. DATA SETS\\text3.json")
           
for (i in ls){

  a[i] <- read_json(i, simplifyVector = TRUE)
  
  z[i] <- data.frame( i,row.names = NULL, check.rows = FALSE,
  
                      check.names = TRUE, fix.empty.names = TRUE,
                      
                      stringsAsFactors = default.stringsAsFactors())
  
  z[i] <- cbind(z[i],a[i])
  
}
View(a)

View(z) 


