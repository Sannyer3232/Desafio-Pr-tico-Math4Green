# 🚀 Feedback Board - Desafio Técnico

Solução Full Stack para gerenciamento de sugestões e feedbacks, desenvolvida com **.NET 9** e **Angular**. O sistema permite que usuários criem sugestões, votem em ideias da comunidade e visualizem tendências em tempo real.

![Badge .NET](https://img.shields.io/badge/.NET-9.0-512bd4?style=flat&logo=dotnet)
![Badge Angular](https://img.shields.io/badge/Angular-18%2B-dd0031?style=flat&logo=angular)
![Badge MySQL](https://img.shields.io/badge/Database-MySQL-4479a1?style=flat&logo=mysql)
![Badge Swagger](https://img.shields.io/badge/Docs-Swagger-85ea2d?style=flat&logo=swagger)

## ✨ Funcionalidades

### 🔐 Autenticação & Segurança
* **Login & Registro:** Sistema de autenticação via **JWT (JSON Web Token)**.
* **Segurança:** Senhas criptografadas usando **BCrypt**.
* **Proteção:** Endpoints de votação protegidos (apenas usuários autenticados).

### 💡 Gestão de Sugestões (Board)
* **CRUD Completo:** Criação e listagem de sugestões.
* **Trending Topics:** Algoritmo que identifica e destaca sugestões com votos recentes (última hora) com a flag "🔥 EM ALTA".
* **UX/UI:** Interface limpa com **CSS Puro** (Flexbox/Grid), sem dependência de frameworks pesados como Bootstrap.
* **Feedback Visual:** Sistema de notificações (Toasts) customizado para ações de sucesso/erro.

### ⚖️ Regras de Negócio (O Desafio)
1.  **Limite de Votos:** O sistema bloqueia automaticamente se o usuário tentar votar mais de **3 vezes no mesmo dia**.
2.  **Anti-Self-Vote:** Usuários não podem votar nas próprias sugestões.
3.  **Voto Único:** Impede múltiplos votos na mesma sugestão.

---

## 🛠️ Tecnologias Utilizadas

### Backend (.NET 9 Web API)
* **Framework:** .NET 9.0 (C#)
* **ORM:** Entity Framework Core 9.0
* **Database Provider:** Pomelo.EntityFrameworkCore.MySql
* **Docs:** Swashbuckle (Swagger UI)
* **Architecture:** Camadas separadas (Models, DTOs, Services, Controllers).

### Frontend (Angular)
* **Framework:** Angular (Standalone Components).
* **Estilização:** CSS Vanilla (Variáveis, Grid Layout, Responsividade).
* **Comunicação:** HttpClient com Interceptors (para envio de Token).
* **Components:** Modal reutilizável e Toast Notification Service.

---

## 🚀 Como Rodar o Projeto

### Pré-requisitos
* [.NET 9 SDK](https://dotnet.microsoft.com/download) instalado.
* [Node.js](https://nodejs.org/) (LTS) instalado.
* MySQL Server rodando.

### 1️⃣ Configuração do Backend

1.  Clone o repositório:
    ```bash
    git clone [https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git](https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git)
    cd feedback-board/FeedbackAPI
    ```

2.  Configure o Banco de Dados:
    Abra o arquivo `appsettings.json` e ajuste a **ConnectionStrings** com seu usuário e senha do MySQL.

3.  Aplique as Migrations (Criação do Banco):
    ```bash
    dotnet ef database update
    ```

4.  Rode a API:
    ```bash
    dotnet run
    ```
    *A API estará rodando em: `http://localhost:5262`*
    *Swagger disponível em: `http://localhost:5262/swagger`*

### 2️⃣ Configuração do Frontend

1.  Em outro terminal, entre na pasta do front:
    ```bash
    cd ../feedback-front
    ```

2.  Instale as dependências:
    ```bash
    npm install
    ```

3.  Rode o projeto:
    ```bash
    ng serve
    ```

4.  Acesse no navegador: `http://localhost:4200`

---

## 🧠 Decisões de Arquitetura

* **Uso de DTOs (Data Transfer Objects):** Para não expor as Entidades do banco diretamente na API, garantindo segurança (ex: não retornar senha do usuário) e desacoplamento.
* **Service Pattern:** Toda a regra de negócio (validação de 3 votos, cálculo de trending) foi isolada em Services (`SuggestionService`, `UserService`), deixando os Controllers limpos.
* **Angular Standalone:** Utilizei a abordagem moderna do Angular sem `NgModules`, reduzindo o boilerplate e melhorando a performance.
* **Custom CSS:** Optei por não usar bibliotecas de UI para demonstrar domínio dos fundamentos de CSS (Grid, Flexbox, Animações) e manter o bundle leve.

---

## 📸 Screenshots

*(Espaço reservado para você colocar prints da tela de Login e do Board)*

---

Desenvolvido por **[Seu Nome]** 🚀