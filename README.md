# Glosario de Términos de cómputo en la nube
## General:
 - Cashflow: Flujo de efectivo: dinero.
 - FrontEnd: En diseño de software el front-end es la parte del software que interactua con el o los usuarios, siendo el responsable de
   recolectar los datos de entrada del usuario, que pueden ser de muchas y variadas formas, y los tranforma ajustandolos a las 
   especificaciones demandadas por el back-end.
 - Backend: Es la parte que procesa la entrada desde el front-end, devolviendo generalmente una respuesta que el front-end recibe y expone al    usuario de una forma entendible para este. 
 - Workflow:
 - Monolithic App:

## Workflow:
 - IDE:
 - Sublime:
 - Vi/vim:
 - Emacd:
 - Atom:
 - TextWrangler:
 - Notepad++:
 - Yeoman:
 - Grunt:
 - Bower:
 - Gulp:
 - LAMP:
 LAMP es el acrónimo usado para describir un sistema de infraestructura de internet que usa las siguientes herramientas:

    Linux, el sistema operativo; En algunos casos también se refiere a LDAP.
    Apache, el servidor web;
    MySQL/MariaDB, el gestor de bases de datos;
    Perl, PHP, o Python, los lenguajes de programación.

 - WAMP:
 WAMP es el acrónimo usado para describir un sistema de infraestructura de internet que usa las siguientes herramientas:

    Windows, como sistema operativo;
    Apache, como servidor web;
    MySQL, como gestor de bases de datos;
    PHP (generalmente), Perl, o Python, como lenguajes de programación.

 - XAMP:
 XAMPP es un servidor independiente de plataforma, software libre, que consiste principalmente en el sistema de gestión de bases de datos MySQL, el servidor web Apache y los intérpretes para lenguajes de script: PHP y Perl. El nombre proviene del acrónimo de X (para cualquiera de los diferentes sistemas operativos), Apache, MySQL, PHP, Perl.

 - LEMP:
 - NOLEG:

## Amazon:
 - AWS: ([Amazon Web Services](https://aws.amazon.com/es/)) ![AWS logo](https://a0.awsstatic.com/main/images/logos/aws_logo_105x39.png)
 - EC2: (Elastic Cloud Computing) Virtual Servers in the Cloud.
 - S3: (Simple Storage Service) Scalable Storage in the Cloud.
 - Route 53: Scalable DNS and Domain Name Registration.

## Javascript:
  - blocking:
  - nonblocking:
  - node:
  - npm: (Node Package Manager)

### Libraries:
   - require:

### Frameworks:
 - Frontend:
  1. Bootstrap:
  2. Foundation:
  3. Materialize:
  4. AngularJS:
 - Backend:
  1. Backbone:
  2. Ember.js:
  3. Express.js:
  4. Sails:

## MongoDB
### CRUD
Create, Read, Update, Delete

#### Create
` db.collection.insert() `
Returns an object: `WriteResult({ "nInserted" : 1 })`, where `nInserted` is the number of document insertions. If the operation encounters an error, the `WriteResult` object will contain the error information. You can also insert an array of documents.

#### Rread
`db.collection.find() `
Returns a cursor to the retrieved documents. This method receives a condition which can be one of the following:

##### Equality
`{ <field>: <value> }`: Where `field` has an exact value of `value`

##### AND
```mongo
{
  <field1>: <value1>,
  <field2>: <value2>
}
```

##### OR
Using the `$or` operator, you can specify a compound query that joins each clause with a logical OR conjunction so that the query selects the documents in the collection that match at least one condition.

```mongo
{
  $or: [
    { <field1>: <value1> },
    { <field2>: <value2> }
  ]
}
```
#### Update
```mongo
 db.collection.update(
   { <field1>: <value1> },
   $set: {
        { <field2>: <NewValue> }
      }
   )
```
This function updates a single document. The update operation returns a `WriteResult` object which contains the status of the operation. A successful update of the document returns the following object:
`WriteResult({ "nMatched" : a, "nUpserted" : b, "nModified" : c })`
The `nMatched` field specifies the number of existing documents matched for the update, and `nModified` specifies the number of existing documents modified.

##### Update multiple documents
To update multiple documents with the same key:value pair simply add the following object to the update function:
`{ multi: true }`

##### `upsert` Option
`{ upsert: true }`
By default, if no document matches the update query, the `update()` method does nothing. However, by specifying `upsert: true`, the `update()` method either updates matching document or documents, or inserts a new document using the update specification if no matching document exists.
In the return object, the `nUpserted` of 1 shows that the update added a document.

#### Remove
The `db.collection.remove()` method removes documents from a collection. You can remove all documents from a collection, remove all documents that match a condition, or limit the operation to remove just a single document.

##### Remove all documents
`db.inventory.remove({})`
To remove all documents from a collection, pass an empty query document `{}` to the `remove()` method. The `remove()` method does not remove the indexes.

##### Remove Documents that Match a Condition
```mongo
db.inventory.remove(
  { <field>: <value> }
)
```
To remove the documents that match a deletion criteria, call the `remove()` method with the `<query>` parameter.

##### Remove a Single Document that Matches a Condition
```mongo
db.inventory.remove(
  { <field>: <value> },
  1
)
```
To remove a single document, call the `remove()` method with the `justOne` parameter set to `true` or `1`.
