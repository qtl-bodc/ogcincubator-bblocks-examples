---
title: My Building Block (Schema)

language_tabs:
  - json: JSON
  - turtle: RDF/Turtle
  - jsonld: JSON-LD

toc_footers:
  - Version 0.1
  - <a href='#'>My Building Block</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: My Building Block (Schema)
---


# My Building Block `ogc.bbr.examples.my-building-block`

This Building Block serves as a template to create new ones

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/invalid" target="_blank" data-rainbow-uri>Invalid</a>
</p>

<aside class="warning">
Validation for this building block has <strong><a href="https://github.com/ogcincubator/bblocks-examples/blob/master/build/tests/bbr/examples/my-building-block/" target="_blank">failed</a></strong>
</aside>

# Description

## Qui hastarum tectus Cithaeron iuvabat

Lorem markdownum vestigia sanguine rursus undis, suspenderat meo mox conlegerat
temperat sucos. Est graves dant sentire sanguinis flores respondent testari.

> Videri vias quid Ausoniae sua flores ante, reminiscitur fuit est. Semel
> [hectora](http://silvaque.org/) peregrinaeque rudem exercent in, Troiana si
> Asida instabilesque somno sed.

## Iam vota cui dilataque peterem

Tinxit lumina lacer liquidarum Aiax si mergitur sed fueris capitisque **et
cadit** contigerant rectum [ferar](http://prosternit.com/quoque.html) temperat.
Monet caput adsensere Ityn furentibus gelidos.
# Examples

## This is an example with just a description and no code snippets.

This is the content of the example.

In **Markdown** format.


## Examples can have content and/or code snippets.

The content of this example. 



```json
{
  "a": 1,
  "b": 2
}

```

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/tests/bbr/examples/my-building-block/example_2_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fbblocks-examples%2Fmaster%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Fmy-building-block%2Fexample_2_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```turtle
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
<http://example.com/my/resource> rdfs:label "My Label" .
```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/tests/bbr/examples/my-building-block/example_2_2.ttl">Open in new window</a>
</blockquote>




```jsonld
{
  "a": 1,
  "b": 2,
  "@context": "https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/annotated/bbr/examples/my-building-block/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/tests/bbr/examples/my-building-block/example_2_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fbblocks-examples%2Fmaster%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Fmy-building-block%2Fexample_2_1.jsonld">View on JSON-LD Playground</a>
</blockquote>



# JSON Schema

```yaml--schema
$schema: https://json-schema.org/draft/2020-12/schema
description: Schema for my building block
type: object
properties:
  a:
    type: string
    format: uri
    x-jsonld-id: https://example.org/my-bb-model/a
    x-jsonld-type: '@id'
  b:
    type: number
    x-jsonld-id: https://example.org/my-bb-model/b
required:
- a
- b

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fbblocks-examples%2Fmaster%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Fmy-building-block%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/annotated/bbr/examples/my-building-block/schema.yaml" target="_blank">https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/annotated/bbr/examples/my-building-block/schema.yaml</a>
* JSON version: <a href="https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/annotated/bbr/examples/my-building-block/schema.json" target="_blank">https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/annotated/bbr/examples/my-building-block/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "a": {
      "@id": "https://example.org/my-bb-model/a",
      "@type": "@id"
    },
    "b": "https://example.org/my-bb-model/b",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fraw.githubusercontent.com%2Fogcincubator%2Fbblocks-examples%2Fmaster%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Fmy-building-block%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/annotated/bbr/examples/my-building-block/context.jsonld" target="_blank">https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/build/annotated/bbr/examples/my-building-block/context.jsonld</a>

# Transforms

## SHACL example <small>shacl</small>

```
@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

<urn:example:LabelToDCTERMS>
    a sh:NodeShape ;
    sh:targetSubjectsOf rdfs:label ;
    sh:rule [
        a sh:SPARQLRule ;
        sh:construct """
            prefix dcterms: <http://purl.org/dc/terms/>
            prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>
            CONSTRUCT {
                $this dcterms:title ?label
            } WHERE {
                $this rdfs:label ?label
            }
        """
    ] ;
.
```
* Source MIME type: `text/turtle`
* Target MIME type: `text/turtle`
* Link: [https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/_sources/my-building-block/transforms/sample.shacl](https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/_sources/my-building-block/transforms/sample.shacl)

## JQ example <small>jq</small>

```
.b2 = .b * .b
```
* Source MIME type: `application/json`
* Target MIME type: `application/json`
* Link: [https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/_sources/my-building-block/transforms/sample.jq](https://raw.githubusercontent.com/ogcincubator/bblocks-examples/master/_sources/my-building-block/transforms/sample.jq)

# References

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/bblocks-examples" target="_blank">https://github.com/ogcincubator/bblocks-examples</a>
* Path:
<code><a href="https://github.com/ogcincubator/bblocks-examples/blob/HEAD/_sources/my-building-block" target="_blank">_sources/my-building-block</a></code>

