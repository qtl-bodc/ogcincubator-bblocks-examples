
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

#### jsonld
```jsonld
{
  "@context": "https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/propertySet/context.jsonld",
  "myProp": "Very smooth"
}
```

#### ttl
```ttl
@prefix ns1: <http://example.org/myModel/> .

[] ns1:myProp "Very smooth" .


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
      x-jsonld-id: http://example.org/myModel/myProp
  required:
  - myProp

```

Links to the schema:

* YAML version: [schema.yaml](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.json)
* JSON version: [schema.json](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "myProp": "http://example.org/myModel/myProp",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/propertySet/context.jsonld)

## Sources

* [Semantic Sensor Network Ontology](https://www.w3.org/TR/vocab-ssn/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/qtl-bodc/ogcincubator-bblocks-examples](https://github.com/qtl-bodc/ogcincubator-bblocks-examples)
* Path: `_sources/feature/propertySet`

