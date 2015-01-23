# ideditor_transl_qa20150122
iD Editor translations QA reports 

This repo contains some basic prototype reports  helping [OpenStreetMap iD Editor](https://github.com/openstreetmap/iD) translators.
This is the alpha release


quick tip:
*  download this repo ;  see -> "Download ZIP"
*  unzip 
*  go  ./qadata_20150122/  and select your languages code.
*  open the id_presets_translation_**.xlsx with  Excel or LibreOffice Calc
*  examine sheets and analyse data with spreadsheet functions. ( Filter, see context ... )


# Example report files : 

directory ./qadata_20150122/de/   ( de = German language  )

##  id_jsondiff_v1.6.2_de.txt	   
   json diff file  iD v1.6.2 and latest transifex (2015.01.2?)

   What is changed since iD v1.6.2 release? 

```txt     
       building/detached: {
-        name: "Doppelhaus"
+        name: "freistehendes Haus"
-        terms: "Haushälfte, Doppelhaus"
+        terms: "freistehendes Haus, Einfamilienhaus"
       }
```

## id_presets_translation_de.json	
  Special json file with
  *  "english" - ./dist/locales/en.json ->   keys with '*__en'  postfix   
  *  "translated" - ./dist/locales/de.json -> keys with '*__transl' postfix  

  Why ?   I would like to analyse  all json config files together :
    * translations files : ./dist/locales/de.json ; ./dist/locales/en.json ;     
    * config files: ./presets/data/categories.json ;   ./presets/data/fields.json; ./presets/data/presets.json

example     
```json
"building/detached": {
        "fields": [
          "address",
          "levels"
        ],
        "geometry": [
          "point",
          "area"
        ],
        "icon": "building",
        "name": "Detached Home",
        "name__en": "Detached Home",
        "name__transl": "freistehendes Haus",
        "tags": {
          "building": "detached"
        },
        "terms__en": "",
        "terms__transl": "freistehendes Haus, Einfamilienhaus"
      },
```

            
## id_presets_translation_de.xlsx	
special XLS file -  3 sheets 

####  sheet : 'meta_de' 
  some statistics and meta information

####  sheet : 'iPresets' 
you have to manually add "AutoFilter" 

this is based iD Editor - preset schema 
  schema:  https://github.com/openstreetmap/iD/blob/master/data/presets/schema/preset.json
and added some translation fileds  
- nameEn             ( name - english )	
- nameTransl         ( name - translated )    
And  some special variable
- duplicateTranslation  :  check "nameTransl" duplicates
- nameTranslWarnings    :  DoubleSpace,LineFeed,FormFeed,Tab  checking  at the translated  "name" field 
- termsTranslWarnings   :  DoubleSpace,LineFeed,FormFeed,Tab  checking  at the translated  "terms" field 
- ....

####  sheet : 'iFields' 
you have to manually add "AutoFilter" 

this is based iD Editor - field schema: https://github.com/openstreetmap/iD/blob/master/data/presets/schema/field.json
Some type:"combo" parameter expanded - see [ r, optionskey,	valueEn ,	valueTransl ] columns.

# id_presets_translation_fields_de.csv	
  this file contains same data  as id_presets_translation_de.xlsx - 'iFields' sheet - only csv format
# id_presets_translation_fields_de.md	
  this file contains same data  as id_presets_translation_de.xlsx - 'iFields' sheet - only markdown format
  
# id_presets_translation_presets_de.csv	
  this file contains same data  as id_presets_translation_de.xlsx - ''iPresets' sheet - only csv format
  
# id_presets_translation_presets_de.md
  this file contains same data  as id_presets_translation_de.xlsx - ''iPresets' sheet - only markdown format
