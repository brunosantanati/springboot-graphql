## Run Configuration

Use this VM Option `-Dspring.profiles.active=dev`

## URLs

[Playground](https://github.com/graphql/graphql-playground)  
[Graphql doc](https://graphql.org/learn/)  
[Scalar types](https://graphql.org/learn/schema/#scalar-types)  

## Local URLs

```
Hello World Rest to test application:
http://localhost:5000/hello

GraphiQL URL:
http://localhost:5000/graphiql

Playground URL:
http://localhost:5000/playground
```

### GraphQL Queries

```js
{
  hello
}
```

```js
{
  hello,
  soma(a:1, b:2)
}
```

```js
{
  hello,
  clientes {
    id, nome, email,
  }
}
```

```js
{
  hello,
  cliente(id:1) {
    id, nome, email,
  }
}
```

```js
{
  hello,
  c1: cliente(id:1) {
    id, nome, email,
  },
  c2: cliente(id:2) {
    id, nome, email,
  },
}
```

```js
{
  hello,
  produtos {
    id, nome, valor
  },
}
```

```js
mutation {
  saveProduto(produto: {
    nome: "Teste",
    valor: 150
  }) {
    id, nome, valor
  }
}
```

```js
{
  hello,
  clientes {
    id, nome, email,
    compras {
      quantidade, status, data
    }
  }
}
```

```js
{
  hello,
  clientes {
    id, nome, email,
    compras {
      quantidade, status, data,
      produto {
        nome, valor
      }
    }
  }
}
```

```js
{
  compras(page:0, size:2) {
    id, quantidade, status, data,
    produto {
      nome, valor
    }
  }
}
```

```js
{
  compras(page:1, size:2) {
    id, quantidade, status, data,
    produto {
      nome, valor
    }
  }
}
```

```js
{
  compras {
    id, quantidade, status, data
    produto {
      nome
      valor
    }
    cliente {
      nome
      email
    }
  }
}
```

## Live demo (graphiql)

[graphiql](https://github.com/graphql/graphiql)  
[Live demo](https://graphql.github.io/swapi-graphql/)

## Queries live demo

```js
{
  allFilms {
    films {
      title
      director
    }
  }
}
```

## Docker commands

```
Spin up a MySQL container:
docker run --name my-mysql --network my-bridge-network -e MYSQL_ROOT_PASSWORD=mypass -d mysql:latest

Find out the IP of the MySQL container:
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-mysql

Connect in the MySQL using a client:
docker run -it --network my-bridge-network --rm mysql mysql -h172.21.0.2 -uroot -p
```
