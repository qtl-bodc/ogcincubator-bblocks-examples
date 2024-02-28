## Custom Feature Type 

This building block illustrates a typical "Feature Type" - where an object is modelled as a "Feature with geometry", but has its own "native schema" - or "domain model".

This is an **interoperable** approach to defining a Feature, allowing re-use of a well-defined domain model.

i.e. the attributes (properties) are managed independently of the packaging container (Feature) 

the **propertySet** building block referenced by this container may be used independently of the FeatureModel structure, and is where semantic annotations are provided.

This building block **inherits** reusable semantic annotations for the Feature structure from a common library, simplifying implementation. 



