# NoSQL Studio


## This is a simple project for uni where I implement a script for a document-based database.
## It's a musical estudio

### Creating the Collection:
```javascript
db.createCollection("estudio");
```
### Inserting data:
```javascript
db.estudio.insertOne({quantidade_horas: 3, data: new Date(2019,2,18,10,15), horario: "10:00/13:00", status: "agendado", sala: {nome: "Sala A", valor_hora: 45}, tecnico_som: {nome: "Albertio Jones", telefone: ["9999-1234", "9999-4321"], endereco: {logradouro: "Rua Uma", numero: 44}}, banda: {nome: "Albertio e banda", lider_banda: "albertio", estilo_musical:"rock", integrante: [{nome: "albertio jones", cpf: "123.432.456.99", telefone: ["9999-1234"]}, {nome: "Aba Lolo"}]}})
```
