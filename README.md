# NoSQL - Musical Studio

## This is a simple project for uni where I implement a script for a document-based database.
## It's a musical studio! Rock On!

# i. Concept Model
![Concept Model](https://i.imgur.com/FMvV9jw.jpg "Concept Model")

# ii. Operations
---
### Creating the Collection:
```javascript
db.createCollection("estudio");
```

---
### Creating Indexes
```javascript
db.estudio.createIndex( { "banda.nome": 1 } )
```

### Creating Indexes
```javascript
db.estudio.createIndex( { "data": 1 } )
```

---
### Inserting data:
##### Albertio e Banda
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,18,10,15), 
  horario: "10:00/13:00", 
  status: "agendado", 
  sala: {nome: "Sala A", valor_hora: 45}, 
  tecnico_som: {nome: "Albertio Jones", telefone: ["9999-1234", "9999-4321"], endereco: {logradouro: "Rua Uma", numero: 44}}, 
  banda: {nome: "Albertio e banda", lider_banda: "albertio", estilo_musical:"rock", integrante: [{nome: "albertio jones", cpf: "123.432.456.99", telefone: ["9999-1234"]}, {nome: "Aba Lolo"}]}
  })
```

##### 63 Decibeis
```javascript
db.estudio.insertOne(
  {quantidade_horas: 6, 
  data: new Date(2019,2,18,20,0), 
  horario: "20:00/02:00", 
  status: "agendado", 
  sala: {nome: "Sala B", valor_hora: 35}, 
  tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}}, 
  banda: {nome: "63 decibeis", lider_banda: "Samuel", estilo_musical:"rock n roll", integrante: [{nome: "Samuel Cabral", cpf: "111.222.333.45", telefone: ["9999-2222", "9999-2211"]},  {nome: "Gabriel Ramalho", cpf: "222.111.333.45", telefone: ["9999-3333", "9999-4445"]}, {nome: "Douglas Oliver", cpf: "888.444.555.45", telefone: ["9999-2112", "9999-6651"]}]}
  })
```

##### Papaninfa
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,19,07,0), 
  horario: "07:00/10:00", 
  status: "agendado", 
  sala: {nome: "Sala C", valor_hora: 55}, 
  tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}},
  banda: {nome: "Papaninfa", lider_banda: "Daniel", estilo_musical:"pop/rock", integrante: [{nome: "Daniel Mendes", cpf: "111.222.333.46", telefone: ["9234-2222", "9959-2241"]},  {nome: "Joao do Pao"}, {nome: "Marcos Maria"}, {nome: "Kailth Justin"}]}
  })
```

##### Fith Monkeys
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,18,15,0), 
  horario: "15:00/18:00", 
  status: "finalizado", 
  forma_pagamento: "Dinheiro", 
  sala: {nome: "Sala A", valor_hora: 45}, 
  tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}}, 
  banda: {nome: "Fith Monkeys", lider_banda: "Marcos", estilo_musical:"pop/rock", integrante: [{nome: "Marcos Hugo", cpf: "431.252.333.46", telefone: ["9234-2554", "9959-2231"]},  {nome: "Carlos Claviar"}, {nome: "BonJose"}, {nome: "Abraao Mitico"}]}
  })
```

##### Fith Monkeys (entrada incorreta no nome da banda para deletar na frente)
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,18,15,0), 
  horario: "15:00/18:00", 
  status: "finalizado", 
  forma_pagamento: "Dinheiro", 
  sala: {nome: "Sala A", valor_hora: 45}, 
  tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}}, 
  banda: {nome: "Fithar Monkeys", lider_banda: "Marcos", estilo_musical:"pop/rock", integrante: [{nome: "Marcos Hugo", cpf: "431.252.333.46", telefone: ["9234-2554", "9959-2231"]},  {nome: "Carlos Claviar"}, {nome: "BonJose"}, {nome: "Abraao Mitico"}]}
  })
```

##### Zero Bronca
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,19,18,0), 
  horario: "18:00/21:00", 
  status: "agendado", 
  sala: {nome: "Sala D", valor_hora: 75}, 
  tecnico_som: {nome: " Maria", telefone: ["9999-1149"], endereco: {logradouro: "Avenida Tres", numero: 13}}, 
  banda: {nome: "Zero Bronca", lider_banda: "Renan Cunha Goncalves", estilo_musical:"pop/rock", integrante: [{nome: "Renan Cunha Goncalves", telefone: ["9234-4262", "9959-2232"]},  {nome: "Nicolas Cardoso Pinto"}, {nome: "Luiz Lima Almeida"}, {nome: "Vinicius Araujo"}, {nome: "Erick Costa"}]}
  })
```

##### Firebolt Of The Explosive Tripper
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,20,07,0), 
  horario: "07:00/10:00", 
  status: "agendado", 
  sala: {nome: "Sala A", valor_hora: 45}, 
  tecnico_som: {nome: "Luis Ferreira Castro", telefone: ["98765-4321"], endereco: {logradouro: "Avenida Cinco", numero: 55}},
  banda: {nome: "Firebolt Of The Explosive Tripper", lider_banda: "Enzo Silva Santos", estilo_musical:"metal rock", integrante: [{nome: "Enzo Silva Santos", telefone: ["95534-4262", "99529-2232"]},  {nome: "Amanda Rocha Fernandes"}, {nome: "Beatrice Barbosa Gomes"}]}
  })
```

##### Slow Stroller And The Princess
```javascript
db.estudio.insertOne(
  {quantidade_horas: 6, 
  data: new Date(2019,2,20,10,0), 
  horario: "10:00/16:00", 
  status: "finalizado",
  forma_pagamento: "cartao credito", 
  sala: {nome: "Sala B", valor_hora: 55}, 
  tecnico_som: {nome: "Tiago Alves", telefone: ["97864-2311"], endereco: {logradouro: "Avenida Seis", numero: 66}},
  banda: {nome: "Slow Stroller And The Princess", lider_banda: "Bruno Araujo Cunha", estilo_musical:"Punk rock", integrante: [{nome: "Bruno Araujo Cunha", telefone: ["4895-2117", "4895-2417"]},  {nome: "Arthur Dias Cunhas"}, {nome: "Kauan Correia Azevedo"}, {nome: "Eduardo Pereira Rocha"}, {nome: "Evelyn Dias Cunha"}]}
  })
```

##### Gorgeous Granola
```javascript
db.estudio.insertOne(
  {quantidade_horas: 6, 
  data: new Date(2019,2,20,13,0), 
  horario: "13:00/19:00", 
  status: "finalizado",
  forma_pagamento: "cartao debito", 
  sala: {nome: "Sala C", valor_hora: 65}, 
  tecnico_som: {nome: "Tiago Alves", telefone: ["97864-2311"], endereco: {logradouro: "Avenida Seis", numero: 66}},
  banda: {nome: "Gorgeous Granola", lider_banda: "Luís Ferreira Barbosa", estilo_musical:"rock", integrante: [{nome: "Luís Ferreira Barbosa", telefone: ["2047-7551", "2337-7551"]},  {nome: "Estevan Barros Melo"}, {nome: "Vitór Gomes Castro"}, {nome: "Gabriel Melo Goncalves"}]}
  })
```

##### Definite Of The Catholic
```javascript
db.estudio.insertOne(
  {quantidade_horas: 9, 
  data: new Date(2019,2,20,9,0), 
  horario: "09:00/18:00", 
  status: "finalizado",
  forma_pagamento: "dinheiro", 
  sala: {nome: "Sala D", valor_hora: 75}, 
  tecnico_som: {nome: "Alex Gomes Pinto", telefone: ["98822-0029"], endereco: {logradouro: "Avenida Sete", numero: 7}},
  banda: {nome: "Definite Of The Catholic", lider_banda: "Eduarda Goncalves Araujo", estilo_musical:"Catholic rock", integrante: [{nome: "Eduarda Goncalves Araujo", telefone: ["9218-5654", "8218-5654"]},  {nome: "Julia Ferreira Azevedo"}, {nome: "Fernanda Silva Cavalcanti"}]}
  })
```

##### Witty Hustler
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,20,16,0), 
  horario: "16:00/19:00", 
  status: "agendado",
  sala: {nome: "Sala E", valor_hora: 85}, 
  tecnico_som: {nome: "Alex Gomes Pinto", telefone: ["98822-0029"], endereco: {logradouro: "Avenida Sete", numero: 7}},
  banda: {nome: "Witty Hustler", lider_banda: "Anna Ferreira Alves", estilo_musical:"Catholic rock", integrante: [{nome: "Anna Ferreira Alves", telefone: ["9704-7817", "9701-7817"]},  {nome: "Nicolash Souza Cunha"}, {nome: "Linda G. Filkins"}, {nome: "Billy A. Brink"}, {nome: "Mackenzie Bethel"}]}
  })
```

##### Sambalele
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,20,16,0), 
  horario: "16:00/19:00", 
  status: "agendado",
  sala: {nome: "Sala E", valor_hora: 85}, 
  tecnico_som: {nome: "Luis Ferreira Castro", telefone: ["98765-4321"], endereco: {logradouro: "Avenida Quatro", numero: 447}},
  banda: {nome: "Sambalele", lider_banda: "Jamie Munz", estilo_musical:"Samba", integrante: [{nome: "Jamie Munz", telefone: ["9744-7317", "9721-7317"]},  {nome: "Zoe Meyer"}, {nome: "Jacob Cooper"}, {nome: "Elliot Dennis"}, {nome: "Diego Dias Carvalho"}, {nome: "Carlos Sousa"}]}
  })
```

##### The Brazils
```javascript
db.estudio.insertOne(
  {quantidade_horas: 3, 
  data: new Date(2019,2,20,19,0), 
  horario: "19:00/21:00", 
  status: "agendado",
  sala: {nome: "Sala D", valor_hora: 75}, 
  tecnico_som: {nome: "Melissa Santos Sousa", telefone: ["92222-4838"], endereco: {logradouro: "Avenida Dez", numero: 12447}},
  banda: {nome: "The Brazils", lider_banda: "Ryan Gomes Santos", estilo_musical:"Pop", integrante: [{nome: "Ryan Gomes Santos", telefone: ["7987-6183", "3987-6183"]},  {nome: "Anna Ribeiro Cavalcanti"}, {nome: "Joao Gomes Cavalcanti"}]}
  })
```

##### Out Abortion
```javascript
db.estudio.insertOne(
  {quantidade_horas: 1, 
  data: new Date(2019,2,20,10,0), 
  horario: "10:00/11:00", 
  status: "agendado",
  sala: {nome: "Sala A", valor_hora: 45}, 
  tecnico_som: {nome: "Melissa Santos Sousa", telefone: ["92222-4838"], endereco: {logradouro: "Avenida Dez", numero: 12447}},
  banda: {nome: "Out Abortion", lider_banda: "Giovanna Rocha Almeida", estilo_musical:"Grothesque Metal", integrante: [{nome: "Giovanna Rocha Almeida", telefone: ["6653-9249", "6653-9211"]},  {nome: "Gennady Abramoff"}, {nome: "Vladlen Kovalyov"}, {nome: "Yaropolk Shubin"}, {nome: "Frida Bakken"}, {nome: "Odin Anderssen"}]}
  })
```

##### The Blanket
```javascript
db.estudio.insertOne(
  {quantidade_horas: 2, 
  data: new Date(2019,2,20,10,0), 
  horario: "10:00/12:00", 
  status: "finalizado",
  forma_pagamento: "dinheiro",
  sala: {nome: "Sala C", valor_hora: 65}, 
  tecnico_som: {nome: "Luis Ferreira Castro", telefone: ["98765-4321"], endereco: {logradouro: "Avenida Cinco", numero: 5}},
  banda: {nome: "The Blanket", lider_banda: "Rinkimirikakuta", estilo_musical:"Prog Metal", integrante: [{nome: "Rinkimirikakuta", telefone: ["6423-9149", "1253-9211"]},  {nome: "Zukarinkuari"}, {nome: "Zumoshijiku"}, {nome: "Shifukato"}, {nome: "Arichikatotakufu"}]}
  })
```

##### Inside The Elvis
```javascript
db.estudio.insertOne(
  {quantidade_horas: 6, 
  data: new Date(2019,2,20,16,0), 
  horario: "16:00/22:00", 
  status: "cancelado",
  sala: {nome: "Sala B", valor_hora: 55}, 
  tecnico_som: {nome: "Luis Ferreira Castro", telefone: ["98765-4321"], endereco: {logradouro: "Avenida Cinco", numero: 5}},
  banda: {nome: "Inside The Elvis", lider_banda: "Tyson Goguen", estilo_musical:"Cover Classic", integrante: [{nome: "Tyson Goguen", telefone: ["3801-9889", "3801-9339"]},  {nome: "Cosette Angélil"}, {nome: "Matthieu"}, {nome: "Adrienne"}, {nome: "Thiery Aupry"}]}
  })
```

##### Avenging Strokes
```javascript
db.estudio.insertOne(
  {quantidade_horas: 12, 
  data: new Date(2019,2,20,07,0), 
  horario: "07:00/19:00", 
  status: "cancelado",
  sala: {nome: "Sala A", valor_hora: 45}, 
  tecnico_som: {nome: "Alex Gomes Pinto", telefone: ["98822-0029"], endereco: {logradouro: "Avenida Edede", numero: 45}},
  banda: {nome: "Avenging Strokes", lider_banda: "Bronislav", estilo_musical:"Classical Rock", integrante: [{nome: "Bronislav", telefone: ["34421-9489", "3123-9339"]},  {nome: "Ana Gabrijela Doler"}, {nome: "Fahrija Auda"}, {nome: "Sehare"}, {nome: "Alojzija"}]}
  })
```

##### Rolling Confrontation
```javascript
db.estudio.insertOne(
  {quantidade_horas: 6, 
  data: new Date(2019,2,20,07,0), 
  horario: "07:00/13:00", 
  status: "agendado",
  sala: {nome: "Sala E", valor_hora: 85}, 
  tecnico_som: {nome: "Alex Gomes Pinto", telefone: ["98822-0029"], endereco: {logradouro: "Avenida Edede", numero: 45}},
  banda: {nome: "Rolling Confrontation", lider_banda: "Duje", estilo_musical:"Classical Rock", integrante: [{nome: "Duje", telefone: ["341349489", "3123-9339"]},  {nome: "Kong Pan"}, {nome: "Li Chiu"}]}
  })
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

---
### Deleting data:
##### Deleting the document with the incorrect band name: Fithar Monkeys
```javascript
db.estudio.deleteOne( { "banda.nome": "Fithar Monkeys" } )
```

--- 
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

##### Find all documents with the quantity of hours greater than or equal to 6
```javascript
db.estudio.find({quantidade_horas: {$gte: 6}})
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

##### Find bands using Regex to find all occurences that the name of the musical style begins with rock
```javascript
db.estudio.find({"banda.estilo_musical": /rock$/}, {"banda.nome":1, "banda.estilo_musical": 1})
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

---
### Conceptual Model to NoSQL Mapping:

![1](https://i.imgur.com/NuvkQzD.png "1")
![2](https://i.imgur.com/i8ITMou.png "2")
![3](https://i.imgur.com/w0Guv5H.png "3")
