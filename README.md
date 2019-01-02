# Acadgild-Data-Analytics-Session-2_Assignment-2.2

 Problem Statement

1. Read multiple json files into a working directory for further converting into a dataset.

I have files text1, text2, text3 in the directory json.


2.	Parse the following JSON into a data frame

js<-'{
"name": null, "release_date_local": null, "title": "3 (2011)",

"opening_weekend_take": 1234, "year": 2011, "release_date_wide": "2011-09-16", "gross": 59954 }'

3.	Write a script for variable binning using R.

 SOLUTION :
 
1.  The sample json files text1.json, text2.json and text3.json are present in the folder “json” in F:\\ACADGILD - Online Course\\1. DATA SETS

Jsonlite and dplyr packages are installed and then following commands are executed using R-studio:

# Reading multiple files using for loop and convert into a dataset

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

Hence multiple json files are read into the working directory and are then converted into datasets.

The current working directory may be obtained by using getwd()

# Reading multiple files one by one and convert into a dataset

library(jsonlite) 

library(dplyr) 

y1<-read_json("F:\\ACADGILD - Online Course\\1. DATA SETS\\text1.json") 

View(y1)

result1<- as.data.frame(do.call("rbind",y1))

result1

y2<-read_json("F:\\ACADGILD - Online Course\\1. DATA SETS\\text2.json") 

View(y2)

result2<- as.data.frame(do.call("rbind",y2)) 

result2

y3<-read_json("F:\\ACADGILD - Online Course\\1. DATA SETS\\text3.json") 

View(y3) 

result3<- as.data.frame(do.call("rbind",y3)) 

result3

       
2.
js<-'{
"name": null, "release_date_local": null, "title": "3 (2011)",

"opening_weekend_take": 1234, "year": 2011, "release_date_wide": "2011-09-16", "gross": 59954 }'

mydf <- fromJSON(js) 

mydf

Here the given Jason is stored in variable named js.fromJSON() function is used for the parsing the data into dataframe. The resultant data frame is stored in mydf.

3.
 Binning is the process of transforming numerical variables into categorical counterparts.

# VARIABLE BINNING USING cut() function

v <-1:400

print(v)

v<-seq(1:100)

print(v)

tapply(v,cut(v,60))
