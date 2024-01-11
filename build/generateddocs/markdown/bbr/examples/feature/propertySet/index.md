
# Example property set for Features (Schema)

`ogc.bbr.examples.feature.propertySet` *v1.0*

This shows how to define a propertyset for a feature - which can be re-used in different containers - such as a GeoJSON Feature schema

[*Status*](http://www.opengis.net/def/status): Under development

## Examples

### Example 1
#### json
```json
{
  "myProp": "Very smooth"
}

```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Example SOSA Vector Observation
allOf:
- type: object
  properties:
    myProp:
      type: string
  required:
  - myProp

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.yaml)

## Sources

* [Semantic Sensor Network Ontology](https://www.w3.org/TR/vocab-ssn/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples](https://github.com/ogcincubator/bblocks-examples)
* Path: `_sources/feature/propertySet`

