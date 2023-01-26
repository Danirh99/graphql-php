Pasos:
1 - Crear Carpeta con el proyecto
2 - Instalar Graph QL por composer -> composer require webonyx/graphql-php
3 - Instalar paquete para interactuar con la base de datos facilmente -> composer require illuminate/database
4 - Preparar en composer.json el autoload
5 - Crear index.php
6 - Preparar index.php
7 - Crear Modelos de las tablas de nuestra base de datos (como si fuese un laravel)
8 - Crear carpeta Graphql
///

Archivos Grahql
- mutations.php -> contiene las mutations creadas en la carpeta mutations (agregar, eliminar y actualizar)
- query.php -> Contiene las querys que usaremos para obtener datos de nuestra base de datos
- types.php -> Contiene los tipos, es como el modelo, con sus campos y demas, es lo que nos va a poder devolver el grafo
- boot.php -> Se encarga de preparar el entorno para realizar las pruebas



/*
Para mutations:
mutation {
  addUser(first_name: "prueba", last_name:"prueba 2", email:"hola@gola.com") {
    id
  }
}
*/

/*
Para queries:
{
  user(id: 3)
  {
    id
    email
  }
}
*/

/*
Para alias
{
  address(id: 1) {
    nombre: name
  }
}
*/

/*
Fragmentos
{
  query {
    ...nombreFragmento
  }
}
fragment nombreFragmento on Modelo {
  campos
  que
  queremos
}

{
  users {
    ...getUsersWithFullAddress
  }
}
fragment getUsersWithFullAddress on User {
  first_name
  last_name
  email
}

{
  user(id: 1) {
    ...getUsersWithFullAddress
  }
}
fragment getUsersWithFullAddress on User {
  first_name
  last_name
  email
}
*/