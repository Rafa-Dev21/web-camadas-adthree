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
const API_URL = "https://api-rifas-i7qy.onrender.com";


## 3. Como o GitHub conecta tudo

O GitHub funciona como o repositório central do meu projeto, onde fica todo o código do front-end e do back-end versionado.

No meu caso, o front-end e a API estão em repositórios separados, o que facilita a organização e permite fazer deploy de cada parte de forma independente.

Sempre que eu faço um git push, a plataforma de hospedagem (Netlify no front-end e Render no back-end) detecta automaticamente essa atualização no repositório e inicia um novo processo de deploy.

Isso significa que o GitHub não apenas guarda o código, mas também atua como gatilho para atualização da aplicação em produção.

📌 PRINT DO PAINEL DE DEPLOY DO NETLIFY
<img width="1794" height="890" alt="image" src="https://github.com/user-attachments/assets/bec129b1-ab82-42bf-a9d0-ab409cae318c" />

📌 PRINT DO PAINEL DE DEPLOY DO RENDER (mostrando deploy da API atualizado)
<img width="1780" height="965" alt="image" src="https://github.com/user-attachments/assets/777039d9-3134-486b-a577-039a623cf742" />
