# Introduction

![InRule DMN Step By Step Guide Step 2](/images/shoppingcartmodel.png)

### DMN Modeler 1.1 Release
We are pleased to announce the availability of DMN Modeler 1.1.  This release includes many new features that improve usability and provide full participation in the rule application lifecycle when using irCatalog.  Read more about specific features and release notes [here](/install/readme.md).

### Welcome
Welcome to the DMN Modeler repository on GitHub.  This repository contains everything you need to model decisions using Decision Model and Notation (DMN) 1.3 (as established by OMG) in conjuction with irAuthor® from InRule Technology®.

DMN, as a practice, provides a formal approach to discover decisions, inventory existing decisions, and implement them progressively while minimizing friction.  The standard also describes implementation for executable logic beyond modeling, such as expressions and specific rule artifacts like decision tables.  At a very high level, DMN provides a rich canvas to quickly discover which decisions are public or private, the data they rely on and the supporting aspects covering topics like requirements, dependencies on machine learning models and notes (Annotations).  While conducting workshops for a new project, DMN is a great way for the team to share what they know, document it and prepare a backlog of work that will be assigned to team members.

### Who is this for?
DMN is for anyone who must understand the automation that exists (under management) and any backlog of automation waiting to be implemented by a team.  DMN models can be quickly understood at a high level without getting into the implementation details.  

### What can I do with this DMN capability?
irAuthor users can create decision models based on the [DMN 1.3 specification](https://www.omg.org/spec/DMN/1.3/PDF).  This means that all of the shapes within the specification can be used to create a model.  Moreover, the same capability allows for the importing and exporting of decision tables using the specification.  Imported decision tables execute natively on the InRule Decision Platform with the same performance as other decision tables created by irAuthor.

### What is InRule's level of participation in the DMN standard?
InRule is an active member of [DecisionAutomation.org](https://www.decisionautomation.org).  This consortium consists of working groups focused on adoption and sponsoring requierments for DMN.  You can read more about our charter and the [DMN On-ramp Group](https://www.decisionautomation.org/dmn-on-ramp-group) and follow our activities.

### Why is DMN Modeler released as an extension?
There is currently a lot of innovation taking place around the standard.  For this reason, we decided an extension would provide more rapid access to changes independent of our traditional release cadences.  

### What is the support model for DMN Modeler?
DMN Modeler is released as a managed extension.  This means that it is fully supported by InRule's support team.  Any question or issue may be submitted to [support@inrule.com].

### Licensing
DMN requires a valid irAuthor license to run.

### System Requirements
* irAuthor version 5.7.2 or newer
* irAuthor System Requirements
* Microsoft WebView2 Runtime Fixed Version, version 91.0.864.64 will be installed as part of the intallation process of this extension, as silent install.  

### Installation
Installation instructions are located [here](/install/readme.md).

### Documentation and Samples:

- [Support for DMN Models](/doc/DMNModels.md)
   * [Where do Decision Models fit into irAuthor?](/doc/DMNModels.md)
   * [Import/Export of models](/doc/DMNModels.md#importexport-of-models)
   * [Explore shapes and connectors](/doc/DMNModels.md#explore-shapes-and-connectors)
   * [Step by step guide on how to design a decision model](/doc/DMNModels.md#step-by-step-guide-on-how-to-design-a-decision-model)
- [Support for Decision Tables](/doc/DecisionTables.md)
   * [When and how to define a Decision Table](/doc/DecisionTables.md#when-and-how-to-define-a-decision-tables)
   * [Hit policy](/doc/DecisionTables.md#hit-policy)
   * [Data types and S-FEEL](/doc/DecisionTables.md#data-types-and-s-feel)
   * [Import/Export](/doc/DecisionTables.md#importexport)
- [Keyboard Shortcuts](/doc/KeyboardShortcuts.md)
- [Public API](/doc/PublicAPIForDMNModeler.md)
- [Samples](/samples/)
    * Industry models
      * [Mortgage Pre-Qualification](/samples/PreQualificationModel.dmn)
    * Decision Tables
      * [Basic sample "WhatToWear"](/samples/InRuleDMN_SampleDecisionTable_WhatToWear.dmn)
      * [Automotive sample "TireTesting"](/samples/InRuleDMN_SampleDecisionTable_TireTesting.dmn)
