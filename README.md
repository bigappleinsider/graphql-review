### Naming a query

```
query fetchCompany{
  company(id: "2") {
    id
    name
    description
    users {
      id
      firstName
      age
      company {
        name
        description
      }
    }
  }
}
```

### Renaming result
- cannot have duplicate keys

```
query fetchCompany{
  google: company(id: "2") {
    id
    name
    description
    users {
      id
      firstName
      age
      company {
        name
        description
      }
    }
  }
  apple: company(id: "1") {
    id
    name
    description
    users {
      id
      firstName
      age
      company {
        name
        description
      }
    }
  }
}

```

### Query fragments
- a list of props we want to get access to
- reduce duplication

```
fragment companyDetails on Company {
  id
  name
  description
}

query fetchCompany{
  google: company(id: "2") {
   ...companyDetails
  }
  apple: company(id: "1") {
    id
    name
    description
    users {
      id
      firstName
      age
      company {
        name
        description
      }
    }
  }
}
```

### Mutations
- updating data

