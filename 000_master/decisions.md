# General Guideline
Best practices mentioned here: https://www.moesif.com/blog/api-guide/graphql-best-practices-resources-and-design-patterns/

# Schema Types

- GraphQL doesn't support regex or any constraint on string, so `AbstractLanguage` and some other types are just duplicate. However, there are [additional directives](https://www.npmjs.com/package/graphql-constraint-directive) that you can use. For this reason, and keep the schema kinda similar to openapi schema, i didn't remove anything.

![image](https://github.com/mhrimaz/aas-connect-schema/assets/17963017/13699bf2-f7e5-475d-91c5-0819d3bb6849)

## Limitations

it is not possible that an interface extend another interface, but anyway, you need to repeat the definitions.
https://discuss.dgraph.io/t/can-interfaces-implement-other-interfaces-in-graphql/10013/4

so instead of `interface SubmodelElement implements Referable & HasSemantics & Qualifiable & HasDataSpecification`
it is possible to have `type SubmodelElement implements Referable & HasSemantics & Qualifiable & HasDataSpecification`
however `SubmodelElement` is actually an interface so

`interface SubmodelElement` and we repeat the definitions.

# Query

- How should be the interaction? It can mimic the REST api endpoints, or be GraphQL style? How should be the naming convention?

![image](https://github.com/mhrimaz/aas-connect-schema/assets/17963017/4ee2ac54-d3f6-4b5f-8065-50fee1ed7aba)

An example from https://demo.saleor.io/graphql/:

![image](https://github.com/mhrimaz/aas-connect-schema/assets/17963017/ad528023-1283-43d9-af02-b8d98dc814b4)


List of Examples:
- https://github.com/graphql-kit/graphql-apis
