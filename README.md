# NoSQL Studio


## This is a simple project for uni where I implement a script for a document-based database.
## It's a musical estudio

### Creating the Collection:
```javascript
db.createCollection("estudio");
```

## DML Operations

### Inserting data:
```javascript
db.estudio.insertOne({quantidade_horas: 3, data: new Date(2019,2,18,10,15), horario: "10:00/13:00", status: "agendado", sala: {nome: "Sala A", valor_hora: 45}, tecnico_som: {nome: "Albertio Jones", telefone: ["9999-1234", "9999-4321"], endereco: {logradouro: "Rua Uma", numero: 44}}, banda: {nome: "Albertio e banda", lider_banda: "albertio", estilo_musical:"rock", integrante: [{nome: "albertio jones", cpf: "123.432.456.99", telefone: ["9999-1234"]}, {nome: "Aba Lolo"}]}})
```
```javascript
db.estudio.insertOne({quantidade_horas: 6, data: new Date(2019,2,18,20,0), horario: "20:00/02:00", status: "agendado", sala: {nome: "Sala B", valor_hora: 35}, tecnico_som: {nome: "Jose", telefone: ["9999-1147", "9999-4277"], endereco: {logradouro: "Avenida Dois", numero: 1}}, banda: {nome: "63 decibeis", lider_banda: "Samuel", estilo_musical:"rock n roll", integrante: [{nome: "Samuel Cabral", cpf: "111.222.333.45", telefone: ["9999-2222", "9999-2211"]},  {nome: "Gabriel Ramalho", cpf: "222.111.333.45", telefone: ["9999-3333", "9999-4445"]}, {nome: "Douglas Oliver", cpf: "888.444.555.45", telefone: ["9999-2112", "9999-6651"]}]}})
```