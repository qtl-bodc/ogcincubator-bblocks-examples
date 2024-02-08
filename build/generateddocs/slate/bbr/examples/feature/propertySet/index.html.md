---
title: Example property set for Features (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 1.0
  - <a href='#'>Example property set for Features</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: Example property set for Features (Schema)
---


# Example property set for Features `ogc.bbr.examples.feature.propertySet`

This shows how to define a propertyset for a feature - which can be re-used in different containers - such as a GeoJSON Feature schema

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/bblocks-examples/blob/master/build/tests/bbr/examples/feature/propertySet/" target="_blank">valid</a></strong>
</aside>

# Examples

## Example 1



```json
{
  "myProp": "Very smooth"
}

```

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/propertySet/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Ffeature%2FpropertySet%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "myProp": "Very smooth",
  "@context": "https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/propertySet/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Ffeature%2FpropertySet%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix ns1: <http://example.org/myModel/> .

[] ns1:myProp "Very smooth" .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/propertySet/example_1_1.ttl">Open in new window</a>
</blockquote>



# JSON Schema

```yaml--schema
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

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Ffeature%2FpropertySet%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.yaml" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.yaml</a>
* JSON version: <a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.json" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "myProp": "http://example.org/myModel/myProp",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Ffeature%2FpropertySet%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/context.jsonld" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/context.jsonld</a>

# Validation

## SHACL Shapes

The following sets of SHACL shapes are used for validating this building block:

* Observation Properties <small><code>ogc.sosa.properties.observation</code></small>
  * [https://opengeospatial.github.io/ogcapi-sosa/_sources/properties/observation/rules.shacl](https://opengeospatial.github.io/ogcapi-sosa/_sources/properties/observation/rules.shacl)

# References

* [Semantic Sensor Network Ontology](https://www.w3.org/TR/vocab-ssn/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/bblocks-examples" target="_blank">https://github.com/ogcincubator/bblocks-examples</a>
* Path:
<code><a href="https://github.com/ogcincubator/bblocks-examples/blob/HEAD/_sources/feature/propertySet" target="_blank">_sources/feature/propertySet</a></code>

