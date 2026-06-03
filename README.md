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

---

## 3. Como o GitHub conecta tudo

O GitHub funciona como o repositório central do meu projeto, onde fica todo o código do front-end e do back-end versionado.

No meu caso, o front-end e a API estão em repositórios separados, o que facilita a organização e permite fazer deploy de cada parte de forma independente.

Sempre que eu faço um `git push`, a plataforma de hospedagem (Netlify no front-end e Render no back-end) detecta automaticamente essa atualização no repositório e inicia um novo processo de deploy.

Isso significa que o GitHub não apenas guarda o código, mas também atua como gatilho para atualização da aplicação em produção.

---

📌 **PRINT DO PAINEL DE DEPLOY DO NETLIFY**
<img width="1794" height="890" alt="image" src="https://github.com/user-attachments/assets/bec129b1-ab82-42bf-a9d0-ab409cae318c" />


📌 **PRINT DO PAINEL DE DEPLOY DO RENDER (mostrando deploy da API atualizado)**
<img width="1780" height="965" alt="image" src="https://github.com/user-attachments/assets/777039d9-3134-486b-a577-039a623cf742" />


---

## 4. O que é CI/CD e por que existe

CI/CD é um conjunto de práticas usadas para automatizar o processo de desenvolvimento e entrega de aplicações.

### Continuous Integration (CI)

CI significa Integração Contínua.  
Ela garante que o código enviado pelos desenvolvedores seja integrado com frequência em um repositório principal, evitando conflitos grandes e facilitando a detecção de erros.

### Continuous Delivery / Deployment (CD)

CD significa Entrega ou Implantação Contínua.

- Continuous Delivery: o sistema fica sempre pronto para ser publicado, mas pode exigir uma ação manual.
- Continuous Deployment: qualquer alteração enviada já é automaticamente colocada em produção.

---

### Relação com meu projeto

No meu projeto, esse processo acontece automaticamente quando faço um push no GitHub:

- O código é enviado para o repositório
- O Netlify e o Render detectam a mudança
- O sistema é reconstruído automaticamente
- A nova versão já fica disponível online

Isso é um exemplo simples de CI/CD funcionando na prática.

---

### Exemplo de problema sem CI/CD

Sem CI/CD, em um time com vários desenvolvedores, podem ocorrer problemas como:

- código quebrado sendo enviado direto para produção
- conflitos entre versões diferentes da aplicação
- erros só sendo descobertos depois do deploy
- demora para atualizar o sistema manualmente

Com CI/CD, esses processos são automatizados e mais seguros.

---

📌 **PRINT DO SITE FUNCIONANDO EM PRODUÇÃO**
<img width="1902" height="961" alt="image" src="https://github.com/user-attachments/assets/7af424f1-8097-4ede-bcf6-27fe368f5132" />


📌 **PRINT DO DEVTOOLS (NETWORK) MOSTRANDO A REQUISIÇÃO PARA A API**
<img width="1904" height="979" alt="image" src="https://github.com/user-attachments/assets/77e4a4c3-a328-4269-a878-66fe17f581eb" />


PRINT DA RESPOSTA DA API (status 200 + JSON)
<img width="1883" height="944" alt="image" src="https://github.com/user-attachments/assets/3d10907b-88d0-40e6-9457-da0d81b4acc7" />

