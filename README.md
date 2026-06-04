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

### Front-end em funcionamento

<img width="1835" height="909" alt="image" src="https://github.com/user-attachments/assets/76ac1a59-e0ab-4b65-a63d-2d79407165c3" />

### Requisição da API no DevTools (Network)

<img width="1886" height="933" alt="image" src="https://github.com/user-attachments/assets/656328f1-cf86-4e38-8b2f-deb4b3103acd" />

<img width="1920" height="941" alt="image" src="https://github.com/user-attachments/assets/b8815b42-5de5-4a03-bb2e-d91a62f9391c" />

<img width="1481" height="809" alt="image" src="https://github.com/user-attachments/assets/f8020a9f-8206-4740-80dd-2994b331f06f" />


Neste print é possível visualizar a requisição realizada pelo front-end para a API hospedada no Render, incluindo a URL da requisição, o status de resposta e os dados retornados pela API.

## 3. Como o GitHub conecta tudo

O GitHub funciona como o repositório central do meu projeto, onde fica todo o código do front-end e do back-end versionado.

No meu caso, o front-end e a API estão em repositórios separados, o que facilita a organização e permite fazer deploy de cada parte de forma independente.

Sempre que eu faço um git push, a plataforma de hospedagem (Netlify no front-end e Render no back-end) detecta automaticamente essa atualização no repositório e inicia um novo processo de deploy.

Isso significa que o GitHub não apenas guarda o código, mas também atua como gatilho para atualização da aplicação em produção.

📌 PRINT DO PAINEL DE DEPLOY DO NETLIFY
<img width="1794" height="890" alt="image" src="https://github.com/user-attachments/assets/bec129b1-ab82-42bf-a9d0-ab409cae318c" />

📌 PRINT DO PAINEL DE DEPLOY DO RENDER (mostrando deploy da API atualizado)
<img width="1780" height="965" alt="image" src="https://github.com/user-attachments/assets/777039d9-3134-486b-a577-039a623cf742" />

## 4. O que é CI/CD e por que existe

CI/CD é um conjunto de práticas que ajudam a automatizar o desenvolvimento, os testes e a publicação de aplicações, tornando o processo mais rápido e confiável.

## Continuous Integration (CI)

Continuous Integration (Integração Contínua) consiste em integrar frequentemente as alterações de código ao repositório principal. Isso ajuda a identificar erros mais rapidamente e evita problemas quando várias pessoas trabalham no mesmo projeto ao mesmo tempo.

Em equipes de desenvolvimento, a CI reduz conflitos entre versões e garante que o código enviado por diferentes desenvolvedores seja validado constantemente.

## Continuous Delivery e Continuous Deployment (CD)

Continuous Delivery (Entrega Contínua) é o processo de preparar automaticamente uma nova versão da aplicação para publicação. Após passar pelas verificações necessárias, a versão fica pronta para ser disponibilizada, mas ainda depende de uma aprovação manual.

Já o Continuous Deployment (Implantação Contínua) vai além, realizando automaticamente a publicação da nova versão após todas as validações serem concluídas com sucesso, sem necessidade de intervenção manual.

Relação com este projeto

Durante o desenvolvimento desta atividade, realizei manualmente etapas como a hospedagem do banco de dados, a publicação da API e a configuração do front-end para consumir a API em produção.

Quando faço um git push para o GitHub, plataformas como Netlify e Render detectam automaticamente as alterações no repositório e iniciam um novo processo de build e deploy. Esse comportamento é um exemplo prático de automação relacionada aos conceitos de CI/CD.

## Exemplo de problema sem CI/CD

Em uma equipe com cinco desenvolvedores trabalhando na mesma API, um programador poderia enviar uma alteração que causasse falhas na aplicação sem perceber. Sem um processo automatizado de validação e deploy, o erro poderia chegar ao ambiente de produção e afetar os usuários.

Com uma pipeline de CI/CD, testes e verificações seriam executados automaticamente antes da publicação, reduzindo significativamente o risco de disponibilizar uma versão com problemas.
