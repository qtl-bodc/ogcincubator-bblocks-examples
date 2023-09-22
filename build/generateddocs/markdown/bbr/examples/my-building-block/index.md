
# My Building Block (Schema)

`ogc.bbr.examples.my-building-block` *v0.1*

This Building Block serves as a template to create new ones

[*Status*](http://www.opengis.net/def/status): Invalid

## Description

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
## Examples

### This is an example with just a description and no code snippets.
This is the content of the example.

In **Markdown** format.

### Examples can have content and/or code snippets.
The content of this example. 
#### json
```json
{
  "a": 1,
  "b": 2
}

```

#### ttl
```ttl
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
<http://example.com/my/resource> rdfs:label "My Label" .
```

#### jsonld
```jsonld
{
  "a": 1,
  "b": 2,
  "@context": "https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/my-building-block/context.jsonld"
}
```

## Schema

```yaml
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

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/my-building-block/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/my-building-block/schema.yaml)


# JSON-LD Context

```jsonld
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

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/my-building-block/context.jsonld)

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-examples](https://github.com/ogcincubator/bblocks-examples)
* Path: `_sources/my-building-block`

