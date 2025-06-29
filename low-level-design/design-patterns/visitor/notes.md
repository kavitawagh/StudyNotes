Lets you separate algorithms from objects on which they operate.
Consider a graph with multiple types of node. Nodes and have node in side it.
We want to build a functionality to export a graph to XML
Tommorrow new requirement might come to export graph in another format.

Created Visitor interface and a concrete class to transform in XML.
Add methods to handle different types of nodes in Visitor
```
XMLVisitor

+ doForCity(City c)
+ doForIndustry(Industry i)
+ doForSightSeeing(SightSeeing s)
```

Let the main object decid which method of visitor to use. We need to modiy main object code for this once.
```
// Client code
foreach node in graph:
  node.accept(xmlVisitor)

// City
def accept(Visitor v):
  v.doForCity(this)

// SightSeeing
def accept(Visitor v):
  v.doForSightSeeing(this)
```

In future we can add other transformations by creating new concrete visitor and main object code will not need to be modified.
