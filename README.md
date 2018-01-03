# EspressoViews

EspressoViews is a reporting and data analysis environment. 
It generates fast, simple and efficient reports from relational databases (RDBMS). 

In a nutshell, Espresso View merges the results of many SQL queries to a hierarchically structured result and displays it in a tree structure, which can be manually expanded and collapsed. See below an example of a (simple) EspressoView report:

![](https://github.com/RaduMarcel/EspressoViews-/blob/master/DocImg/EspressoViewsImg1.png)

Currently (December 2017) it supports "only" the Oracle and MySQL database servers.

## **What are the special "skills" of EspressoViews?**


- The core feature is the human friendly ["narrative flow" approach][Ideas] which allows you to coagulate the information retrieved by many SQL queries to a new and higher unit of sense.

The smallest unit or module is built around a single SQL query. A report is made of at least two such SQL query units. The above example is made of three SQL query units, but theoretically there is no limitation. Any report definition, can be on his side embedded in another report definition, and so on. 

More details about this approach you can find in the chapters [The main ideas behind this tool][Ideas] and [Defining an EspressoViews report][ReportDef]

[Ideas]: https://github.com/RaduMarcel/EspressoViews-/wiki/2.-The-main-ideas-behind-this-tool
[Reportref]: https://github.com/RaduMarcel/EspressoViews-/wiki/3.-Defining-an-EspressoViews-report

- The goal of this report definition framework is not only to support the modularization of data retrieval in many loosely interconnected queries but also to induce SQL coding into a higher level design approach. 

If you have one monolithic SQL query which retrieves everything you need or if you plan to build such a query and you are looking forward to create a report around it, then this reporting tool will not be useful for you.

This tool is best suitable for use cases in which the data retrieval is made of a multitude of SQL queries, where at any time new queries have to be included, changed or removed. 


- Another aim of this tool is to maintain the human readability without reducing the complexity and/or the amount of data.

Espresso view first runs all SQL queries as specified in the report definition without prior filtering by the user. 
The first data shown to the user is the result of the root query, which can be used as a summary or as an introduction for the rest of the data tree. The user then decides which meaningful "data path" to follow further.

Though, a graphical user interface for filtering prior to and after the data retrieval is in some cases still necessary and will be supported in the future as optional features.




This tool is a dwarf standing on the shoulders of RDBMS giants.


## What should I do to give it a try? 

You need first to have a Java Runtime version 1.8 or higher installed installed on your machine (it works also with version 1.7 but it is not fully tested).
To do a quick check type in the command line:
```
java -version
```
If the version is lower or your system does not have Java then please download and install a newer Java version (https://java.com/de/download/). 
If you know that you have the right version but the Java executable was not found from the command line, then make sure the Java PATH system variable is set correctly (see more: https://www.java.com/en/download/help/path.xml).


Then download the EspressoViews file `EspressoViews.zip` and unpack it in an own folder. The application is started either by double-klicking Java runnable file `EspressoViews.jar` or by typing in the command line 
```
java -jar EspressoViews.jar
```

If the application has started correctly, then you should be able to see this database log-in dialog:

![](https://github.com/RaduMarcel/EspressoViews-/blob/master/DocImg/EspressoViewsInstall.png)



Now, to use and generate an EspressoViews report you need:

**1. An XML report definition file.**

This definition file is made of your SQLs queries and of instructions, which specify how to organize and display the data retrieved with these SQL queries. To see how such an EspressoViews definition is created please read first [these introductory words on how to define an Espresso Views report][ReportDef] and then [the XML report definition syntax][ReportSyntax]

[ReportDef]: https://github.com/RaduMarcel/EspressoViews-/wiki/3.-Defining-an-EspressoViews-report
[ReportSyntax]: https://github.com/RaduMarcel/EspressoViews-/wiki/4.-The-XML-report-definition-syntax

**2. The connection credentials for the (Oracle or MySQL) database server where the report definition file should be ran.**

The `EspressoViews.zip` file contains the JDBC driver packages for the suported database server. They are placed in the folder `EspressoViews_lib`. The provided JDBC diver for Oracle databases works with the Oracle Versions 11.2 and 12.1 and the JDBC driver for MySQL databases works at least with the MySQL versions from 5.1 to 5.7
These drivers can be also downloaded in internet and you should do so if the version provided is not compatible with the database system version you try to access.
If you replace the JDBC driver packages then make sure the new driver file name is also referenced in the path defintion in MANIFEST.MF file of the `EspressoViews.jar` package.  


**3. Press the OK Button on the bottom to generate the report**


## Contributing

To be continued

## Credits: 
Espresso Views, Version 0.5

Copyright © Radu-Marcel Dumitru

This program is free software; you can redistribute it and/or modify it under the terms of the GNU GENERAL PUBLIC LICENSE, Version 3 as published by the Free Software Foundation on 29 June 2007
This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. 
See the GNU General Public License for more details.


