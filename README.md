# Web Camadas - ADO 3

Este projeto representa a entrega da disciplina de Aplicações Web em Camadas, mostrando uma aplicação completa em produção com front-end, back-end, banco de dados e integração via GitHub com CI/CD.

---

## 1. Diagrama da arquitetura em produção

Aqui está o diagrama que representa como minha aplicação está funcionando em produção:

📌 <img width="455" height="602" alt="image" src="https://github.com/user-attachments/assets/2832857e-00db-40ed-b9c9-f23be20cbe1f" />

### Explicação do diagrama

No meu projeto, o front-end está hospedado na plataforma Netlify e é responsável por fazer requisições HTTP para a API.

A API está hospedada na plataforma Render e recebe essas requisições, processa as regras de negócio e se comunica com o banco de dados.

O banco de dados PostgreSQL está hospedado em Railway e armazena todas as informações persistentes da aplicação.

A comunicação acontece via JSON através de requisições HTTP (GET, POST, PUT, DELETE).

O GitHub entra como repositório central do código. Sempre que há um push, as plataformas de deploy detectam a mudança e fazem o rebuild automático da aplicação.

---

## 2. Front-end consumindo a API em produção

### Tecnologias usadas
Meu front-end foi desenvolvido utilizando: HTML CSS E JS

Ele está hospedado em: https://rafarifas.netlify.app/

### Configuração da API

No front-end, a URL da API foi configurada para apontar para o ambiente de produção, e não mais para localhost.

Exemplo:

```js
const API_URL = "https://api-rifas-i7qy.onrender.com";
