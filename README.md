# Practice GraphQL

## Query / Mutations / Enums / Composed Queries

## Packages
- axios => fetch data
- apollo-server => GraphQL server compatible with any GraphQL Client
- uuid => ID generator
- json-server => json server db

## Simple Query
`
query {
  personCount
}
`

# Mutations 
`
mutation($name: String!, $phone: String, $street: String!, $city: String!) {
  addPerson(
    name: $name
    phone: $phone
    street: $street
    city: $city
  ) {
    name
    phone
    address {
      city
      street
    }
    id
  }
}
`
- Variables
`
{
  "name": "Name Y",
  "street": "Calle A",
  "city": "Mercurio",
  "phone": "123-123"
}
`



## Composed Query with Enum query
`
query {
  personCount
  allPersonsData: allPersons {
    name
  }
  personsWithPhone: allPersons(phone: YES) {
    name
  }
  personsWithoutPhone: allPersons(phone: NO) {
    name
  }
}
`