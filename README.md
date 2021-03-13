# QA-Automation Educational Repository. 
_Contains bare-bones test scripts to get you started quickly._ 

##### Running postman collections in your cli or pipeline

_the basic command requires that you have nodejs and the newman package installed_
```
newman run /path/to/your/collection/myCollection.postman_collection.json
```

_the expanded command with more detail_
```
newman run ./myCollection.postman_collection.json -e ./envFile.postman_environment.json -d ./data/myCsvOrJsonDataFileForMultipleIterations.json -g ./globals/postmanGlobalVariablesFile.json -i 2 -r cli,html,htmlextra
```

```
-e   to pass in the path to your environment file. 
    Example use case: a {{host}} variable in the event that you have the app deployed in multiple datacenters and the URL changes depending on the DC.

-d   to pass in the path to your data file.
-i   integer of how many iterations to run. 
-g   to pass in the path to a globals file is you use them. _I tend not to use this_ 

-r   reporters. in this case the 'cli' arg enables outputting to the console. The 'html' option makes newman generate an html report. 
The 'htmlextra' option is another package that you can install that makes for a more developed static webpage report. 



```

[HTML Extra on NPM](https://www.npmjs.com/package/newman-reporter-htmlextra)


##### Example with the welcome-service

```
 newman run qa-automation/welcome-service/welcome-service.postman_collection.json -e qa-automation/welcome-service/welcome-service-local.postman_environment.json 

```

##### Reference Materials

[Postman Test Examples](https://learning.postman.com/docs/writing-scripts/script-references/test-examples/)
[Postman Sandbox API Scripting Reference](https://learning.postman.com/docs/writing-scripts/script-references/postman-sandbox-api-reference/)



_Brandon Morris_ 
_DevOps Engineer_ 