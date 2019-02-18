# NoSQL Studio

## This is a simple project for uni where I implement a script for a document-based database.
## It's a musical estudio

#i. Concept Model
![Concept Model](https://i.imgur.com/FMvV9jw.jpg "Concept Model")

#ii. Operations
---
## Creating the Collection:
```javascript
db.createCollection("estudio");
```

---
### Inserting data:
##### Albertio e Banda
```javascript
db.estudio.insertOne({quantidade_horas: 3, data: new Date(2019,2,18,10,15), horario: "10:00/13:00", status: "agendado", sala: {nome: "Sala A", valor_hora: 45}, tecnico_som: {nome: "Albertio Jones", telefone: ["9999-1234", "9999-4321"], endereco: {logradouro: "Rua Uma", numero: 44}}, banda: {nome: "Albertio e banda", lider_banda: "albertio", estilo_musical:"rock", integrante: [{nome: "albertio jones", cpf: "123.432.456.99", telefone: ["9999-1234"]}, {nome: "Aba Lolo"}]}})
```

##### 63 Decibeis
```javascript
db.estudio.insertOne({quantidade_horas: 6, data: new Date(2019,2,18,20,0), horario: "20:00/02:00", status: "agendado", sala: {nome: "Sala B", valor_hora: 35}, tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}}, banda: {nome: "63 decibeis", lider_banda: "Samuel", estilo_musical:"rock n roll", integrante: [{nome: "Samuel Cabral", cpf: "111.222.333.45", telefone: ["9999-2222", "9999-2211"]},  {nome: "Gabriel Ramalho", cpf: "222.111.333.45", telefone: ["9999-3333", "9999-4445"]}, {nome: "Douglas Oliver", cpf: "888.444.555.45", telefone: ["9999-2112", "9999-6651"]}]}})
```

##### Papaninfa
```javascript
db.estudio.insertOne({quantidade_horas: 3, data: new Date(2019,2,19,07,0), horario: "07:00/10:00", status: "agendado", sala: {nome: "Sala C", valor_hora: 55}, tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}}, banda: {nome: "Papaninfa", lider_banda: "Daniel", estilo_musical:"pop/rock", integrante: [{nome: "Daniel Mendes", cpf: "111.222.333.46", telefone: ["9234-2222", "9959-2241"]},  {nome: "Joao do Pao"}, {nome: "Marcos Maria"}, {nome: "Kailth Justin"}]}})
```

##### Fith Monkeys
```javascript
db.estudio.insertOne({quantidade_horas: 3, data: new Date(2019,2,18,15,0), horario: "15:00/18:00", status: "finalizado", forma_pagamento: "Dinheiro", sala: {nome: "Sala A", valor_hora: 45}, tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}}, banda: {nome: "Fith Monkeys", lider_banda: "Marcos", estilo_musical:"pop/rock", integrante: [{nome: "Marcos Hugo", cpf: "431.252.333.46", telefone: ["9234-2554", "9959-2231"]},  {nome: "Carlos Claviar"}, {nome: "BonJose"}, {nome: "Abraao Mitico"}]}})
```

##### Fith Monkeys (entrada incorreta no nome da banda para deletar na frente)
```javascript
db.estudio.insertOne({quantidade_horas: 3, data: new Date(2019,2,18,15,0), horario: "15:00/18:00", status: "finalizado", forma_pagamento: "Dinheiro", sala: {nome: "Sala A", valor_hora: 45}, tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}}, banda: {nome: "Fithar Monkeys", lider_banda: "Marcos", estilo_musical:"pop/rock", integrante: [{nome: "Marcos Hugo", cpf: "431.252.333.46", telefone: ["9234-2554", "9959-2231"]},  {nome: "Carlos Claviar"}, {nome: "BonJose"}, {nome: "Abraao Mitico"}]}})
```

##### Zero Bronca
```javascript
db.estudio.insertOne({quantidade_horas: 3, data: new Date(2019,2,19,18,0), horario: "18:00/21:00", status: "agendado", sala: {nome: "Sala D", valor_hora: 75}, tecnico_som: {nome: " Maria", telefone: ["9999-1149"], endereco: {logradouro: "Avenida Tres", numero: 13}}, banda: {nome: "Zero Bronca", lider_banda: "Renan Cunha Goncalves", estilo_musical:"pop/rock", integrante: [{nome: "Renan Cunha Goncalves", telefone: ["9234-4262", "9959-2232"]},  {nome: "Nicolas Cardoso Pinto"}, {nome: "Luiz Lima Almeida"}, {nome: "Vinicius Araujo"}, {nome: "Erick Costa"}]}})
```
---
### Updating data:
##### Setting reharsal status to ended on the Papaninfa Band
```javascript
db.estudio.update({"banda.nome": "Papaninfa"}, {$set:{"status":"finalizado"}})
```
##### Updating the name of the Zero Bronca band from Nicolas Cardoso Pinto to Luan Alves
```javascript
db.estudio.update({"banda.nome": "Zero Bronca"}, {$set:{"banda.integrante.1.nome":"Luan Alves"}})
```

### Deleting data:
##### Deleting the document with the incorrect band name: Fithar Monkeys
```javascript
db.estudio.deleteOne( { "banda.nome": "Fithar Monkeys" } )
```

### Reading data:
##### Find all documents in the estudio collection
```javascript 
db.estudio.find()
```
##### Find all documents later than 2019-02-01, in this case it will show all ocurrences
```javascript
db.estudio.find({data: {$gt: new Date(2019, 02, 1)}})
```

##### Count all the documents in this collection
```javascript
db.estudio.count()
```
##### List all the documents with the Room Hourly Price greater than 50 bucks.
```javascript
db.estudio.find({"sala.valor_hora": {$gt:50}})
```
##### Find all documents earlier than 2019-02-19
```javascript
db.estudio.find({data: {$lt: new Date(2019, 02, 19)}})
```
##### Find all documents with the quantity of hours greater than or equal to 3
```javascript
db.estudio.find({quantidade_horas: {$gte: 3}})
```

##### Fetch data with projection, in this case only showing the name of the band, the name of the studio room they selected and ommiting the _id
```javascript
db.estudio.find({"banda.nome": {$in: ["Zero Bronca", "Papaninfa"]}}, {"banda.nome": 1, "sala.nome":1, "_id":0})
```

##### All documents with the status different than "agendado" with the name of the band, status and quantity of hours projection
```javascript
db.estudio.find({"status": {$ne: "agendado"}}, {"banda.nome":1, "status":1, "quantidade_horas": 1})
```

##### Documents where the bands musical style is not "rock" and with the musical style and band name projections
```javascript
db.estudio.find({"banda.estilo_musical": {$ne:"rock"}}, {"banda.estilo_musical":1,"banda.nome":1})
```

##### Find bands using Regex to find all occurences that the name of the band starts with "Papa"
```javascript
db.estudio.find({"banda.nome": /^Papa/}, {"banda.nome":1})
```

##### Accessing array
```javascript
db.estudio.find({"tecnico_som.telefone.0": "9999-1234"})
```

##### Accessing embedded structure
```javascript
db.estudio.find({"tecnico_som.endereco.logradouro": /^Rua/})
```

##### Personalized query, show all the documents where the hourly price of the room is greater than or equal to 35 and the quantity of hours are bigger than 3
```javascript
db.estudio.find({"sala.valor_hora": {$gte: 35},"quantidade_horas": {$gt: 3}})
```
