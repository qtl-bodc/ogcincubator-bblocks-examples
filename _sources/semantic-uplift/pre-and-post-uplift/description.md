This building block defines two custom semantic uplift steps:

* A pre-processing (i.e, on the JSON documents, before applying the JSON-LD context) JQ step to create two
  properties (`three` with the value `3`, and `doubleString` with the value of the `string` property twice).
* A post-processing (i.e., on the RDF graph, after the JSON-LD context has been applied) SPARQL Update
  query where two new predicates (`ex2:hasFour` and `ex2:nineBound`) are added to all subjects of `ex:hasTwo`.
