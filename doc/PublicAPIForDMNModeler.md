# DMN Public API 

DMN Modeler includes a public API consisting of a set of classes that import/export DMN models and decision tables.  More specifically, a developer has the classes to do the following:
-	Import and Export DMN Decision Table(s) to and from a Rule Application
-	Import and Export DMN Model(s) to and from a Rule Application

The Rule Application used in an import or export operation might be:
- A Rule Application saved on the local file system
- A reference to an object representing a Rule Application definition
- A Rule Application from irCatalog

Prerequisites:
-	InRule irAuthor SDK (5.7.2)
-	if a reference to a Rule Application from irCatalog is used, the version of irCatalog should be the same as irAuthor.
-	Assembly InRuleLabs.Authoring.Extensions.DMNAPI.dll

Below are the list of classes and methods available in the API using the InRuleLabs.Authoring.Extensions.DMNAPI namespace.

## DMNDecisionTableAPI class

Method ImportIntoLocalRuleApp: Use the this method for importing one or more Decision Tables into a local Rule Application. The Rule Application might be a reference to an existing one, or, if paramter is omitted, a new Rule Application will be created from scratch. The resulting Rule Application, after import, is validated and if no validation errors are found, will be saved to the provided local path on file system.

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
    // Import Decision Table(s)
    DMNDecisionTableAPI.ImportIntoLocalRuleApp(@"D:\sample_DT.dmn", ruleAppDef);
    // Save the Rule Application after import
    ruleAppDef.SaveToFile(ruleAppFilePath);
    Console.WriteLine("Finished");
```
Method ImportIntoCatalogRuleApp: Use this method for importing one or more Decision Tables into a Catalog Rule Application. A new revision will be automatically created after a successfull import.

Method signature:

```C#
public static string ImportIntoCatalogRuleApp(string dmnFilePath, Uri catalogServiceUri, string username, string password, string ruleAppNameInCatalog)
```

Sample code:
```C#
    Console.WriteLine("Start importing Decision Tables into Catalog Rule Application...");
    DMNDecisionTableAPI.ImportIntoCatalogRuleApp(@"D:\sample_DT.dmn", new Uri("https://inrule-catalog.azurewebsites.net/service.svc"), "RuleAuthor", "password", "MortgageLendingKit");
    Console.WriteLine("Finished");
```

Method ExportFromLocalRuleAppToDMNFormat: Use this method for exporting one or more Decision Tables from a Rule Application reference, to a local .dmn file on file system.

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

Method ImportIntoLocalRuleApp: Use this method for importing a DRG (Decision Requirements Graph) into the referenced Rule Application.

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
   // Import Decision Table(s)
   DMNDecisionTableAPI.ImportIntoLocalRuleApp(@"D:\sample_Model.dmn", ruleAppDef);
   // Save the Rule Application after import
   ruleAppDef.SaveToFile(ruleAppFilePath);
   Console.WriteLine("Finished");
```
