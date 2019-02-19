# Análise do mini projeto quanto ao uso do MongoDB 

---
### 1. Pontos positivos 
```
	Para o tipo do projeto e o escopo, a vantagem de ter tudo numa consulta só é muito boa e otimiza bastante o tempo da query. Também é interessante poder omitir alguns campos não necessários na inserção dos documentos. 
```

---
### 2. Pontos negativos
```
	Não ter integridade referencial pode se tornar um problema conforme o projeto vai aumentando, ter que manualmente atualizar os dados quando mudam é uma desvantagem. A inserção tende a ficar mais verbosa do que na linguagem SQL e precisa de cuidado para não se misturar com tantos {}().
```