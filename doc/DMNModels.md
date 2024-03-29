# Where does decision modeling fit in the authoring process? 
Decision modeling is appropriate for all types of initiatives. Perhaps you want to model existing decisions to help stakeholders understand your current inventory, or maybe you want to bootstrap a new team for a new initiative. Once you have made the choice to model, there two patterns we believe you should consider.

### Model-only Lifecycle
DMN Modeler is implemented as an irAuthor® extension. As an extension, all models you create are stored within a rule application and participate with the irCatalog® lifecycle. This means you can save your models to irCatalog and revise them. That said, it is possible to save your models to irCatalog and have no other implementation in the rule application. This is what we call a "model-only" lifecycle. With this approach, you can create one or more models that represent many other rule applications. This is an ideal pattern for decision inventories.

### Local Model Lifecycle
There are times when the rule author would like to develop models for local decisions in a rule application. This approach helps the author know when they have discovered all of the details they need and can help stakeholders. In this approach, models are lifecycled with the implemented decisions and participate in the revision/deployment cycle.

### Making Models
With DMN Modeler, it is possible to create a Decision Requirements Graph (DRG) from scratch. One way to think of a DRG is as the available canvas for designing the model. As the first shape is being dragged from the palette on the canvas, the Decision Requirements Diagram (DRD) is created and enriched step by step with decisions and any other shape added from the palette. While there can be a lot of complexity around filtered views of a DRG by using multiple DRDs according to DMN spec, our implementation supports a single DRD per DRG. This means that every time a new item is added in the "DMN Models" pane, the rule application receives a new graph and one associated diagram per item.

A compatibility summary between DMN 1.3 spec and InRule's DMN Modeler extension is below.

DMN spec category | DMN spec sub-category | DMN Modeler Compatibility | Comments
------------ | ---------------------------------------------|---------------------|-------------------------------------------------------
Decision Requirements | DRG | Yes |
   | DRD | Partial | 1 DRD per DRG
   | Elements of a DRD: Decision, Business Knowledge Model, Input Data, Knowledge Source, Decision Service | Yes |
   | Artifacts: Text Annotation, Association, Group | Yes |
   | Dependencies between DRD elements: Information Requirement, Knowledge Requirement, Authority Requirement | Yes
Decision Logic | Decision Table - Structure: Input clauses, Output clauses, Rules, Annotation clauses | Partial | Because InRule implements natively Decision Table, it does not support DMN visualization of it. InRule does not implement Annotation clauses for Decision Table.
   | Decision Table - Hit Policy | Partial | [see more details here](../doc/DecisionTables.md#hit-policy)
   | Decision Table - Orientation | Partial | InRule implements Horizontally orientation, with rules on rows.
   | S-FEEL Data Types and Expressions | Partial | [see more details here](../doc/DecisionTables.md#data-types-and-s-feel)
   | FEEL | None | 
 Visual Appearance | DMN Models: zoom in, zoom out | Yes |
   | Shapes: Decision, Business Knowledge Model, Input Data, Knowledge Source, Expanded and Collapsed Decision Service, Group, Text Annotation | Yes |
   | Connectors: Requirement, Knowledge Requirement, Authority Requirement, Association | Yes |
 Connection rules when connecting DRD elements | All possible connection rules between DRD elements | Yes | 
 Referencing external DMN elements | | None |
 External invocation of Decision Services | | None |
 DMN Diagram Interchange (DMN DI) | DMNDI, DMNDiagram, DMNDiagramElement, DMNShape, DMNEdge | Yes |
  

## Add a new DMN Model
Once the DMN Modeler extension is enabled, a new component is visible on the left navigation pane of irAuthor, named “DMN Models”. To create a DMN model from scratch, navigate to the DMN Models component and press the Add button (just as you would do in any other component of the navigation pane: Entities, Rules, Decisions, etc.). 

![irAuthor Add DMN Model Button](../images/InRuleDMN_AddModelButton.PNG) 

Renaming and removing models in the "DMN Models" component also works in the same way as renaming and removing items in the other components of irAuthor.


## Modify an existing DMN Model

Once the user selects a DMN model from the list in the left navigation pane, the canvas shows the selected model, ready to be modified. Possible modifications of the model are:
* Add a shape from the palette by drag and drop onto the canvas.
* Modify the position of a shape, with a mouse-drag from the middle area of the shape, and mouse-drop it to the desired location.
* Resize a shape by selecting the shape with a mouse click and then dragging one of the 8 resize handles highlighted with light blue dots around the shape. The middle-top and middle-bottom resize handles modify the shape's height; the middle-left and middle-right resize handles modify the shape's width; the 4 resize handles in the corners resize both the shape's height and width at the same time.

  ![InRule DMN shape resize handles](../images/InRuleDMN_DecisionShapeSelected.PNG) 

  _**Note:**  Resizing multiple shapes at one time is not supported._

* Rotate a shape, by selecting the shape with a mouse click and use the rotating handle. To discover the rotating handle, select the shape with a mouse click and notice the upper light-blue dot (see image above)
  _**Note:**  Rotating handle is not available for Groups and Decision Services._

* Connect two shapes using a mouse-drag operation from one shape's port to the other shape. To discover available ports on a shape, simply place the mouse over a shape: there are 4 available ports on each shape, highlighted with grey dots. A successful link will result in a link drawn between the two shapes.

  ![irAuthor DMN connect 2 shapes](../images/InRuleDMN_DecisionShapeMouseOver.PNG) 

* Remove elements from the model, by selecting the shape or connector between shapes and press Delete or Backspace from the keyboard. When removing a shape that is connected to other shape, the link will also be removed from the model.
  _**Note:**  Deleting a shape or link from the model will remove the element both from the DRD and DRG of the current model._
  _**Note:**  Deleting multiple elements at one time is possible, by selecting first the elements to be removed and then pressing the Delete or Backspace key._

* Rename a shape: double click the shape if it's unselected, or click if the shape is selected
  _**Note:**  When adding a shape from the palette on the canvas, irAuthor automatically adds a default name of the shape, in accordance with the shape type (example: "Decision" name is assigned to a decision dragged on the canvas)._

## Delete a DMN Model
To delete a DMN Model, locate it from the available items in the left navigation pane "DMN Models", right-click and choose "Delete" option.

![irAuthor Delete DMN Model](../images/InRuleDMN_DeleteModel.PNG)

A confirmation dialog box appears, where the final deletion may be confirmed or cancelled.

![irAuthor Delete DMN Model](../images/InRuleDMN_ConfirmDeleteModel.PNG)

# Import/Export of models

The menus for importing or exporting a DMN model can be found on the Home ribbon tab, group "DMN".

![irAuthor Import Export_Menu](../images/InRuleDMN_Import_Export_Menu.PNG) 

_**Note:** The group "DMN" on the Home ribbon tab is visible only while the DMN Modeler extension is enabled for irAuthor._

Even though current DMN spec is at 1.3 version, there is still a lot of variation across vendors because there are some areas of the specification which are open to interpretation. For this reason, there are cases where model might not import correctly or might need modifications after import. The same is true for Decision Tables.

To import a DMN model from an external .dmn file, find the "Import" menu on the "DMN" group on the Home ribbon tab, and click on the menu option "Decision Model from .dmn file". This menu option is always visible and enabled, no matter what item is currently selected in the left navigation pane or what is the current context of the user's selection. 

![InRule Import DMN Model](../images/InRuleDMN_Import_Model.PNG) 

Then, locate the file on the local file system and confirm the selection. Note that the file has to have the extension .dmn, otherwise an error dialog box is presented and no import is performed.

![InRule Invalid File on Import DMN Model](../images/InRuleDMN_InvalidFileForImport.PNG) 

_**Note:**  When importing a model (DRG) that contains multiple DRDs, a best effort merge is done to flatten the DRDs into one._

If another model with the same name already exists in the rule application, irAuthor will automatically add a prefix counter at the end of the imported DMN model name, or increment the number at the end of the name, if it ends with a digit. For example, if the rule application has a DMN model named DMNModel1 and the model to be imported has the same name DMNModel1, after the import irAuthor will automatically increment the prefix counter and assign the name DMNModel2 to the newly imported object.

A successful import will add a new item in the DMN Models navigation pane and will update the canvas to display the imported model.

_**Note:**  There is no report available for the import process results. In case some elements were not imported due to inconsistency or lack of support in our extension, those elements will not exist in the model, therefore will be lost._

To export a DMN Model, select the desired model from the models list and click on the "Export" menu found on the Home ribbon tab, group "DMN". Then, from the menu options available, click on the "Selected Decision Model to .dmn file" option. 

![InRule Export DMN Model](../images/InRuleDMN_Export_Model.PNG) 

# Explore shapes and connectors

Shapes represent the visual representation of every piece of information or data that help taking a decision. 

Shapes are connected by links. The links are unidirectional, having an arrow at one end. Only one exception exists to arrows: annotations are linked to shapes only with a dotted line, without having a specific direction designed with an arrow. Between 2 shapes there is only one valid link type defined by the DMN spec and irAuthor will automatically design it as soon as the connection is made by the user.

The following table lists all the shapes found in the DMN Modeler extension for irAuthor.
Shape Name | Shape Design | Description
------------ | ---------------------- | ---------------------------------------------------------------------------------------------------
Decision | ![InRule DMN Decision Shape](../images/InRuleDMN_Shape_Decision.PNG) | A decision represents the act of determining an outcome from several inputs, using decision logic.
Input Data | ![InRule DMN Input Data Shape](../images/InRuleDMN_Shape_InputData.PNG) | Input data denotes the information needed as input by one or multiple decisions
Business Knowledge Model | ![InRule DMN Business Knowledge Model Shape](../images/InRuleDMN_Shape_BusinessKnowledgeModel.PNG) | A business knowledge model represents reusable business logic. Technically, it is a function with optional parameters (inputs) that can be invoked from decisions or other business knowledge models.
Knowledge Source | ![InRule DMN Knowledge Source Shape](../images/InRuleDMN_Shape_KnowledgeSource.PNG) | Knowledge sources represent authorities for a decision, for a business knowledge model or for another knowledge source. These can, for example, be policies, regulations, or people that have an influence on the contents of the element.
Annotation | ![InRule DMN Annotation Shape](../images/InRuleDMN_Shape_Annotation.PNG) | Annotations are simply notes to any of the shapes that are not containers for other shapes: decisions, input data, knowledge source, business knowledge model. Any text can be inserted into annotations. They can be used like sticky notes, or as a sort of container for additional attributes for the shape (like owner, or due date).
Group | ![InRule DMN Group Shape](../images/InRuleDMN_Shape_Group.PNG) | A Group is a way to capture information during modelling requirements. Groups can be added or removed from the diagram, without having an impact on the decision model execution. Examples of situations when a group might be useful include: when a discussion is around a certain subject, so  related shapes to that subject are put visually together, without the need to connect them; or when the highlighted property for a group of shapes is the owner.
Decision Service | ![InRule DMN Decision Service Shape](../images/InRuleDMN_Shape_DecisionService.PNG) | A Decision Service defines reusable logic within a decision model. The upper portion shows the public decisions, while any decisions they require to produce their results, but that are not themselves to be exposed publicly, go in the lower (private) section.
Simplified Decision Service | ![InRule DMN Simplified Decision Service Shape](../images/InRuleDMN_Shape_SimplifiedDecisionService.PNG) | Simplified Decision Service is similar to the Decision Service, except for the fact that it does not differentiate between public and private decisions.


The following table lists the visual representation of all possible links, when connecting two shapes. Not every two shape types can be connected, but only those ones meaningful to decision logic. See also the following table, listing those valid connections.

Connector Name | Connector Design | Description
----------------------- | --------------------------------- | -------------------------------------------------------------------------------------------------------------------
Information Requirement | ![InRule DMN Information Requirement Link](../images/InRuleDMN_Link_InformationRequirement.PNG) | Information Requirement denotes Input Data or Decision output being used as input to a Decision
Knowledge Requirement | ![InRule DMN Knowledge Requirement Link](../images/InRuleDMN_Link_KnowledgeRequirement.PNG) | Knowledge requirements are like information requirements, but are used to indicate the invocation of a business knowledge model.
Authority Requirement | ![InRule DMN Authority Requirement Link](../images/InRuleDMN_Link_AuthorityRequirement.PNG) | They are drawn between knowledge sources and other elements to indicate that the knowledge source has an influence there, i.e. is an "authority" for it.
Association | ![InRule DMN Association Link](../images/InRuleDMN_Link_Association.PNG) | They connect a text annotation to an input data, decision, business knowledge model or knowledge source.

_**Note:**  There is no constraint on the number of shapes or links you can use in a decision requirement diagram; you can design the DRD using the needed shapes and the most adequate position for each one of them, but take in consideration that a functional DRD should have all the shapes connected._


# Shape Properties

DMN Modeler 1.1 introduced shape properties accessed from the 'mini menu' using the gear icon.  Properties include Name, Description, Link and colors (Text, Border, Fill).  Links are the most notable of the properties.

#### Link

![Link](../images/Link2.png)

#### General Behavior
Links allow shapes to navigate to external content or internal components of a Rule Application.  Once established, a link icon is available from the 'mini menu'.  Links are removed by removing the text.

#### Create Decision/Entity
If a user does not find a specific Decision or Entity to link to using the menu, they can click on the 'Create Decision/Entity' link.  After providing a Name and a Description, clicking 'Save' will both create the component and link it to the shape in a single action.

#### Colors
Default colors are set by DMN Modeler; however, users may set their own colors on individual shapes.  Colors do not export with models.


# Step-by-step guide on how to design a decision model 

There are some very good books on decision modeling from James Taylor and Jan Purchase that cover in-depth practice (see [Real World Decision Modeling with DMN](https://www.amazon.com/Real-World-Decision-Modeling-James-Taylor/dp/0929652592/ref=sr_1_3?dchild=1&keywords=James+Taylor+dmn&qid=1632853023&sr=8-3)). At the same time, we believe there are fundamental practices you can do on your own to get started with your first model.

#### Questions to ask
1. Brainstorm and/or journey map your business process. What aspects of this journey (or business process) should be automated with a decision?  The decision should solve a specific automation problem.
2. Explore all of the aspects of the candidate decisions and examine if they have sub-decisions (dependent decisions). If you have a couple in mind, then let's model those. Start a new irAuthor DMN model and begin the design by dragging decisions identified so far and put an identification label on each.
3. Once you have a couple of decisions on the canvas, it's time to think about data. Data are represented as inputs in DMN. See if you can establish which field-level data is required to drive the decisions you are thinking about.
4. Now connect your decisions to each other. The entry-point decision should be at the top while dependent decisions connect from below. The lowest-level decisions should have the inputs (data) connected to them. Once your shapes are connected, you have a valid DRD.
5. If you want to specify which decisions are public versus private, you can add the decision service shape to your canvas. Place the entry point decision in the top portion and dependent decisions in the lower portion. Inputs remain outside of the decision service shape.
6. As a stretch goal, try grouping some of your shapes for clarity in the model. 

As your model grows, it may make sense to break out the work into different models. As stated above, you can have as many models as you need in a single rule application. 

Here is a practical example of an online store that is in need of shopping cart automation. It's a simple calculation for a shopping cart total. We also know that that the order total requires a line item calculation: price per item * quantity:

![InRule DMN Step By Step Guide Step 1](../images/InRuleDMN_Model_Step1.PNG)

Now let's document more about this decision. Let's take into consideration that some products might have a discount, or the customer might have a promo code on the order. Discounts and promo codes are detailed requirements we can explicitly add to our model.

![InRule DMN Step By Step Guide Step 2](../images/InRuleDMN_Model_Step2.PNG)

As our guide above suggests, it's time to consider which decisions might be public decision services and which are private. Indeed, all the discounts and promotion calculations are likely internal and we should separate that from the final price calculation. So a Decision Service can be added to our model:

![InRule DMN Step By Step Guide Step 3](../images/InRuleDMN_Model_Step3.PNG)

Many other details can be discovered by the team while modeling. For example, shipping is a common problem but complexities can emerge with different types of shipping, fees and offers. Perhaps some customers are willing to pay more for a speedy shipping and in other cases the business might inject an offer for preferred shipping. It's important to keep the team exploring, modeling, and discovering all of the aspects of each decision until it's unambiguous. This means that once complete, anyone on the team would know what to implement even though explicit logic is not yet defined.








