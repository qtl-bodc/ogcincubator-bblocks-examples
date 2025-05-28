
# Transforms example (Schema)

`ogc.bbr.examples.transforms.transforms-example` *v0.1*

A sample building block to showcase transforms

[*Status*](http://www.opengis.net/def/status): Under development

## Examples

### Example for transforms
#### json
```json
{
  "one": 1,
  "two": 2,
  "string": "value"
}

```

#### jsonld
```jsonld
{
  "@context": "https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/transforms/transforms-example/context.jsonld",
  "one": 1,
  "two": 2,
  "string": "value"
}
```

#### ttl
```ttl
@prefix ex: <http://example.com/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] ex:hasOne 1 ;
    ex:hasString "value" ;
    ex:hasTwo 2 .


```


### Example for XSLT transform
#### xml
```xml
<?xml version="1.0"?>
<Article>
  <Title>My Article</Title>
  <Authors>
    <Author>Mr. Foo</Author>
    <Author>Mr. Bar</Author>
  </Authors>
  <Body>This is my article text.</Body>
</Article>
```

## Schema

```yaml
type: object
properties:
  one:
    type: number
    x-jsonld-id: http://example.com/hasOne
  two:
    type: number
    x-jsonld-id: http://example.com/hasTwo
  string:
    type: string
    x-jsonld-id: http://example.com/hasString
x-jsonld-prefixes:
  ex: http://example.com/

```

Links to the schema:

* YAML version: [schema.yaml](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/transforms/transforms-example/schema.json)
* JSON version: [schema.json](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/transforms/transforms-example/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "one": "ex:hasOne",
    "two": "ex:hasTwo",
    "string": "ex:hasString",
    "ex": "http://example.com/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/transforms/transforms-example/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/qtl-bodc/ogcincubator-bblocks-examples](https://github.com/qtl-bodc/ogcincubator-bblocks-examples)
* Path: `_sources/transforms/transforms-example`

