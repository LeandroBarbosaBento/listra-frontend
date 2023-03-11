# Listra - Frontend

Este projeto é uma página para simulação de financiamento de veículos. 

## Rodando o projeto

Rodar os comandos abaixo no terminal, na pasta raiz do projeto. 

Para instalar as dependências do projeto:

```bash
yarn install
```

Para iniciar o servidor local: 
```bash
yarn run dev
```
## Observações
* Foi utilizado o Vuetify para personalização
* Foi utilizado o Axios para as requisições feitas para a API
* ___IMPORTANTE:___ No arquivo *src/api/index.js* basta alterar o valor da variável *baseURL* (na linha 4) para a URL da API para o sistema funcionar corretamente. 
* Foi configurado o layout para telas grandes e para telas menores. Não foi feita nenhum tipo de otimização para telas de tamanho médio. 