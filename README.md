# Excel Add-in: JavaScript Communication Between plug-ins

**Table of contents**

* [Summary](#summary)
* [Prerequisites](#prerequisites)
* [Key components of the sample](#components)
* [Description of the code](#codedescription)
* [Build and debug](#build)
* [Troubleshooting](#troubleshooting)
* [Questions and comments](#questions)
* [Additional resources](#additional-resources)

<a name="summary"></a>
##Summary
There are There are two parts to this sample, a task pane plug-in for Excel, and a content plug-in for Excel.

- The code in the task pane plug-in for Excel demonstrates how to build a simple user interface that saves data to cross-session web browser storage (localStorage). It also shows how to use a dynamically generated div to surface errors to the user.

- The code in the content plug-in for Excel demonstrates how to detect when the selection in the spreadsheet changes, how to get the data selected after that event, and how to monitor the shared data source for changes. It captures the data from the spreadsheet in an array, evaluates the spreadsheet data with the data from the task pane plug-in, and then displays the results in a table.

<a name="prerequisites"></a>
## Prerequisites ##

This sample requires the following:  

  - Excel 2013.
  - Visual Studio 2013 with Update 5 or Visual Studio 2015.
  - Any browser that supports ECMAScript 5.1, HTML5, and CSS3, such as Internet Explorer 9, Edge, Chrome 13, Firefox 5, Safari 5.0.6, or a later version of these browsers.
  - Familiarity with JavaScript, CSS, jQuery, and HTML5.

<a name="components"></a>
## Key components of the sample
The Excel Add-in: JavaScript Communication Between plug-ins sample contains the following important files:

**CommunicationBetweenPlugInsContent** project, including:

- CommunicationBetweenPlugInsContent.xml manifest 
- ContentHome.js file 
- ContentHome.html file 
- MortgageCalculator.js file

**CommunicationBetweenPlugInsTaskPane** project, including:

- CommunicationBetweenPlugInsTaskPane.xml manifest 
- TaskPaneTaskPaneHome.js file 
- TaskPaneTaskPaneHome.html file 
- toast.js file 

<a name="build"></a>
## Build and debug ##
1. Choose the F5 key to build and deploy the plug-ins. Two instances of Excel 2013 will open, one with the content plug-in (“Mortgage Calculator”) displayed and the other with the task pane plug-in (“Mortgage Info plug-in”) displayed. 
1. In one of the two instances of Excel 2013, on the Insert tab, in the plug-ins for Office group, choose the arrow below plug-in, and then choose the plug-in that you want to insert.
1. The other plug-in will be inserted into the current instance of Excel. Both plug-ins should now be inserted in the same Excel session. 
1. In the content plug-in (“Mortgage Calculator”), choose Connect to Data to establish a connection between the two plug-ins (listening for changes in the data source). 
1. In the task pane plug-in, enter numbers into the two text box inputs and select an option from the drop-down list. Choose the Submit button when you have entered your data. 
1. In the Excel spreadsheet, enter numbers into one or more rows in a single column. Select the rows singly or as a range in a single column. 


<a name="troubleshooting"></a>
##Troubleshooting


If the plug-inplug-in fails to install, ensure that the  SourceLocation element in the CommunicationBetweenPlugInsContent.xml and CommunicationBetweenPlugInsTaskPane.xml files has the correct URL value for the DefaultValue attribute.

<a name="questions"></a>
##Questions and comments##

- If you have any trouble running this sample, please [log an issue](https://github.com/OfficeDev/Outlook-Add-in-Javascript-MakeEWSRequest/issues).
- Questions about Office Add-in development in general should be posted to [Stack Overflow](http://stackoverflow.com/questions/tagged/office-addins). Make sure that your questions or comments are tagged with [office-addins].


<a name="additional-resources"></a>
## Additional resources ##

- [Introduction to Web Storage](https://msdn.microsoft.com/en-us/library/bg142799(v=vs.85).aspx)
- [Document.SelectionChanged event](https://msdn.microsoft.com/library/4cbc527c-a1d5-4fb0-b6db-28cc40c5d5e2)
- [Document.getSelectedDataAsync method](https://msdn.microsoft.com/en-us/library/fp142294(v=office.15))

## Copyright
Copyright (c) 2015 Microsoft. All rights reserved.

