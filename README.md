# Introduction

![InRule DMN Step By Step Guide Step 2](/images/InRuleDMN_Model_Step2.PNG)

Welcome to the DMNModeler repository on GitHub.  This repository contains everything you need to model decisions using Decision Model and Notation (DMN) 1.3 (as established by OMG) in conjuction with InRule irAuthor.

DMN as a practice, provides a formal approach to discover decisions, inventory existing decisions and implement them progressively without a lot of friction.  The standard also describes implementation for executable logic beyond modeling such as expressions and specific rule artifacts like decision tables.  At a very high level, DMN provides a rich canvas to quickly discover which decisions are public/private, the data they rely on and the supporting aspects covering topics like requirements, dependencies on Machine Learning models and notes (Annotations).  While conducting workshops for a new project, DMN is a great way for the team to share what they know, document it and prepare a backlog of work that will be assigned to team members.

### Who is this for?
DMN is for everyone that must understand the automation that is exists (under management) and any backlog of automation waiting to be implemented by a team.  DMN models can be quickly understood at a high level without getting into the implementation details.  

### What can I do with this DMN capability?
irAuthor users can create decision models based on the DMN 1.3 specification.  This means that all of the shapes within the specification can be used to create a model.  Moreover, the same capability allows for the importing and exporting of decision tables using the specificaiton.  Imported decision tables execute natively on the InRule Decision Platform with the same performance as other decision tables created by irAuthor.

### What is InRule's level of participation in the DMN standard?
InRule is an active member of [DecisionAutomation.org].  This consortium consists of working groups focused on adoption and sponsoring requirments for DMN.  You can read more about our charter and the [DMN On-ramp Group](https://www.decisionautomation.org/dmn-on-ramp-group) and follow our activities.

### Why is DMN released as an Extension?
There is currently a lot of innovation taking place around the standard.  For this reason, we decided an extension would provide more rapid access to changes independent of our standard release cadences.  

### What is the support model for DMN?
DMN is released as a "Managed" extension.  This means that it is fully supported by InRule's support team.  Any question or issue may be submitted to [support@inrule.com].

### Licensing
DMN requires a valid irAuthor license to run.

### System Requirements
* IrAuthor version 5.7.2 or newer
* IrAuthor System Requirements
* Microsoft WebView2 Runtime Fixed Version, version 91.0.864.64 will be installed as part of the intallation process of this extension, as silent install.  

### Installation
Installation instructions are located [here](/install/readme.md).

### Documentation and Samples:

- [Support for DMN Models](/doc/DMNModels.md)
   * [What is DMN and where Decision Model fits into irAuthor?](/doc/DMNModels.md)
   * [Import/Export of models](/doc/DMNModels.md#importexport-of-models)
   * [Explore shapes and connectors](/doc/DMNModels.md#explore-shapes-and-connectors)
   * [Step by step guide on how to design a decision model](/doc/DMNModels.md#step-by-step-guide-on-how-to-design-a-decision-model)
- [Support for Decision Tables](/doc/DecisionTables.md)
   * [When and how to define a Decision Table](/doc/DecisionTables.md#when-and-how-to-define-a-decision-tables)
   * [Hit policy](/doc/DecisionTables.md#hit-policy)
   * [Data types and S-FEEL](/doc/DecisionTables.md#data-types-and-s-feel)
   * [Import/Export](/doc/DecisionTables.md#importexport)
- [Keyboard Shortcuts](/doc/KeyboardShortcuts.md)
- [Samples](/samples/)
    * Progressive samples of DMN models
    * Industry models (lending kit, etc)
    * Decision Tables
      * [Basic sample "WhatToWear"](/samples/InRuleDMN_SampleDecisionTable_WhatToWear.dmn)
      * [Automotive sample "TireTesting"](/samples/InRuleDMN_SampleDecisionTable_TireTesting.dmn)
