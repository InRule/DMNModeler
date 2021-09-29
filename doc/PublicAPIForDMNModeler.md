# DMN Public API 

DMN Modeler includes a public API consisting of a set of classes that import/export DMN models and decision tables.  More specifically, a developer has the classes to do the following:
-  Import and export DMN decision table(s) to and from a rule application
-  Import and export DMN model(s) to and from a rule application

The rule application used in an import or export operation might be:
- A rule application saved on the local file system
- A reference to an object representing a rule application definition
- A rule application from irCatalog®

Prerequisites:
-  irSDK® (5.7.2)
-  if a reference to a rule application from irCatalog is used, the version of irCatalog should be the same as irAuthor®.
-  Assembly InRuleLabs.Authoring.Extensions.DMNAPI.dll

Below are the list of classes and methods available in the API using the InRuleLabs.Authoring.Extensions.DMNAPI namespace.

## DMNDecisionTableAPI class

Method ImportIntoLocalRuleApp: Use the this method for importing one or more decision tables into a local rule application. The rule application might be a reference to an existing one, or, if paramter is omitted, a new rule application will be created from scratch. The resulting rule application, after import, is validated and if no validation errors are found, will be saved to the provided local path on file system.

Method signature 1:

```C#
public static string ImportIntoLocalRuleApp(string dmnFilePath, string ruleAppFilePath)
```

Sample code for Method signature 1:
```C#
    Console.WriteLine("Start importing Decision Tables into local Rule Application...");
    InRuleLabs.Authoring.Extensions.DMNAPI.DMNDecisionTableAPI.ImportIntoLocalRuleApp(@"D:\sample_DT.dmn", @"D:\TestRuleAppForDMNAPI.ruleappx");
    Console.WriteLine("Finished");
```

Method signature 2:
```C#
    public static RuleApplicationDef ImportIntoLocalRuleApp(string dmnFilePath, RuleApplicationDef ruleAppDef)
```

Sample code for Method signature 2:
```C#
    Console.WriteLine("Start importing Decision Tables into local Rule Application...");
    string ruleAppFilePath = @"D:\TestRuleAppForDMNAPI.ruleappx";
    // Create rule application reference
    var ruleApp = new FileSystemRuleApplicationReference(ruleAppFilePath);
    RuleApplicationDef ruleAppDef = ruleApp.GetRuleApplicationDef();
    // Import decision table(s)
    DMNDecisionTableAPI.ImportIntoLocalRuleApp(@"D:\sample_DT.dmn", ruleAppDef);
    // Save the rule application after import
    ruleAppDef.SaveToFile(ruleAppFilePath);
    Console.WriteLine("Finished");
```
Method ImportIntoCatalogRuleApp: Use this method for importing one or more decision tables into a Catalog rule application. A new revision will be automatically created after a successfull import.

Method signature:

```C#
public static string ImportIntoCatalogRuleApp(string dmnFilePath, Uri catalogServiceUri, string username, string password, string ruleAppNameInCatalog)
```

Sample code (please replace the values for parameters catalogServiceUri, username and password with your access credentials):
```C#
    Console.WriteLine("Start importing Decision Tables into Catalog Rule Application...");
    DMNDecisionTableAPI.ImportIntoCatalogRuleApp(@"D:\sample_DT.dmn", new Uri("YOUR_SERVICE_URI_FOR_THE_CATALOG"), "username", "password", "MortgageLendingKit");
    Console.WriteLine("Finished");
```

Method ExportFromLocalRuleAppToDMNFormat: Use this method for exporting one or more decision tables from a rule application reference, to a local .dmn file on file system.

Method signature 1:

```C#
public static void ExportFromLocalRuleAppToDMNFormat(string ruleAppFilePath, string dmnDirectoryFilePath, string decisionTableName)
```

Sample code for Method signature 1:
```C#
   Console.WriteLine("Start exporting Decision Tables from a local Rule Application...");
   DMNDecisionTableAPI.ExportFromLocalRuleAppToDMNFormat(@"D:\TestRuleAppForDMNAPI.ruleappx", @"D:\", "WhatToWear");
   Console.WriteLine("Finished");
```

Method signature 2:

```C#
public static string ExportFromLocalRuleAppToDMNFormat(RuleApplicationDef ruleAppDef, string dmnDirectoryLocation, InRule.Repository.Decisions.DecisionDef decDef = null, RuleSetDef decRuleSetDef = null, DecisionTableDef dtDef = null)
```

Sample code for Method signature 2:
```C#
   Console.WriteLine("Start exporting Decision Tables from the first Decisions node of a local Rule Application...");
   string ruleAppFilePath = @"D:\TestRuleAppForDMNAPI.ruleappx";
   // Create rule application reference
   var ruleApp = new FileSystemRuleApplicationReference(ruleAppFilePath);
   RuleApplicationDef ruleAppDef = ruleApp.GetRuleApplicationDef();
   DMNDecisionTableAPI.ExportFromLocalRuleAppToDMNFormat(ruleAppDef, @"D:\", ruleAppDef.Decisions[0]);
   Console.WriteLine("Finished");
```

## DMNModelAPI class

Method ImportIntoLocalRuleApp: Use this method for importing a DRG (Decision Requirements Graph) into the referenced rule application.

Method signature 1:

```C#
public static string ImportIntoLocalRuleApp(string dmnFilePath, string ruleAppFilePath)
```

Sample code for Method signature 1:
```C#
   Console.WriteLine("Start importing Decision Model into local Rule Application...");
   DMNDecisionTableAPI.ImportIntoLocalRuleApp(@"D:\sample_Model.dmn", @"D:\TestRuleAppForDMNAPI.ruleappx");
   Console.WriteLine("Finished");
```

Method signature 2:

```C#
public static RuleApplicationDef ImportIntoLocalRuleApp(string dmnFilePath, RuleApplicationDef ruleAppDef)
```

Sample code for Method signature 2:
```C#
   Console.WriteLine("Start importing Decision Model into local Rule Application...");
   string ruleAppFilePath = @"D:\TestRuleAppForDMNAPI.ruleappx";
   // Create rule application reference
   var ruleApp = new FileSystemRuleApplicationReference(ruleAppFilePath);
   RuleApplicationDef ruleAppDef = ruleApp.GetRuleApplicationDef();
   // Import decision table(s)
   DMNDecisionTableAPI.ImportIntoLocalRuleApp(@"D:\sample_Model.dmn", ruleAppDef);
   // Save the rule application after import
   ruleAppDef.SaveToFile(ruleAppFilePath);
   Console.WriteLine("Finished");
```
