## Project

A Project represents an open-source project available in the Maven repository which might have direct/indirect associated NVD security vulnerabilities. 

### Properties (to be completed)
+ __id__
	The unique ID for the Project.

+ __name__
	The public name for this Project.

+ __groupID__
    The associated Maven groupId for the project.

+ __artifactID__
    The associated Maven artifactId for the project.

+ __version__
    The associated Maven version number for the project.

+ __cpeID__
    The associated NVD ID for the project.

+ __vulnerabilities__
    The directly associated NVD vulnerabilities for the project. This can be seen only when the "detailed" parameter is set to "true".
	
+ __dependencies__
    The transitive dependencies for the project. This can be seen only when the "detailed" parameter is set to "true".

### Making API Calls
These URLs allow you to access the search functionality of SE-GPS from any non-browser user agent. Note that the "wt" parameter present in every URL determines the format of the results. 
Setting "wt" equal to "json" will provide a JSON response, while setting "wt" equal to "xml" will provide the same response formatted as an XML document. 
Another common parameter is "rows," which limits the number of results returned by the server. 
The "detailed" parameter limits the details returned. Setting "detailed" to "false", will return only the basic details about the project(s); setting the value to "true" will return extra details such as transitive dependencies (Transitive dependency depth are limited to X at the moment).

NOTE: Most of the URLs in this document have been URL-decoded for the sake of readability. They should work when pasted into a web browser, but you may have to URL-encode them to function when called programmatically


To get a list of Projects:
```shell
curl https://aseg.cs.concordia.ca/segps/project/list?rows={rows}&wt={wt}&detailed={detailed}
```

To search project(s) based on criteria:
```shell
curl https://aseg.cs.concordia.ca/segps/search/project/select?{searchQuery}&rows={rows}&wt={wt}&detailed={detailed}
```


To get a single Project:
```shell
curl https://aseg.cs.concordia.ca/segps/project/{id}&wt={wt}&detailed={detailed}
```
