# Projeto Laravel com Autenticação (Breeze + SQLite)

Esta é uma aplicação base construída com o framework PHP **Laravel 11**. O projeto inclui um sistema completo de autenticação de usuários (login, registro, recuperação de senha) implementado utilizando o pacote oficial **Laravel Breeze**.

Este projeto foi pré-configurado para usar **SQLite** como banco de dados, tornando o ambiente de desenvolvimento extremamente simples e rápido de configurar, sem a necessidade de um servidor de banco de dados separado.

## Requisitos do Ambiente

Para rodar este projeto, você precisará ter o seguinte software instalado em sua máquina:

- **PHP**: Versão `8.2` ou superior, com a extensão **SQLite3** habilitada (`php-sqlite3`).
- **Composer**: A versão mais recente é recomendada. ([Como instalar](https://getcomposer.org/))
- **Node.js**: Versão `20.x` (LTS) ou superior.
- **NPM**: Geralmente instalado junto com o Node.js.
- **Git**: Para clonar o repositório.

---

## Passo a Passo da Instalação

Siga as instruções abaixo para configurar o ambiente de desenvolvimento e rodar a aplicação.

### 1. Clonar o Repositório

Primeiro, clone este repositório para sua máquina local usando Git:
```bash
git clone https://github.com/RailsonF/auth-breezer-app.git
cd auth-breezer-app
```


### 2. Instalar Dependências

O projeto possui dependências de backend (PHP) e frontend (JavaScript) que precisam ser instaladas.

**a) Instalar dependências do PHP com Composer:**
```bash
composer install
```
> **O que este comando faz?** Ele lê o arquivo `composer.json` e baixa todas as bibliotecas PHP necessárias (incluindo o próprio Laravel) para a pasta `vendor/`.

**b) Instalar dependências do JavaScript com NPM:**
```bash
npm install
```
> **O que este comando faz?** Ele lê o arquivo `package.json` e baixa todas as dependências de frontend (como Tailwind CSS, Alpine.js e Vite) para a pasta `node_modules/`.

### 3. Configurar o Ambiente

**a) Crie seu arquivo de configuração local:**
Copie o arquivo de exemplo `.env.example` para criar seu próprio arquivo de ambiente `.env`.
```bash
cp .env.example .env
```

**b) Gere a chave da aplicação:**
Esta chave é única para cada instalação e é usada para criptografia.
```bash
php artisan key:generate
```

### 4. Preparar o Banco de Dados SQLite

A configuração é simples e direta.

**a) Configure o arquivo `.env`:**
Abra o arquivo `.env` e garanta que a variável `DB_CONNECTION` esteja definida como `sqlite`. As outras variáveis de banco de dados (`DB_HOST`, `DB_DATABASE`, etc.) podem ser removidas ou comentadas, pois não são necessárias.

```env
DB_CONNECTION=sqlite
# DB_HOST=127.0.0.1
# ... (o resto pode ser ignorado)
```

**b) Crie o arquivo do banco de dados:**
Este comando cria o arquivo físico que funcionará como seu banco de dados.
```bash
touch database/database.sqlite
```

### 5. Executar as Migrations

Com o banco de dados pronto, este comando criará todas as tabelas necessárias (como a tabela `users`) dentro do arquivo `database.sqlite`.

```bash
php artisan migrate
```

---

## Rodando a Aplicação

Para rodar a aplicação, você precisará iniciar dois processos em **dois terminais separados**, dentro da pasta do projeto.

### Terminal 1: Servidor de Backend (Laravel)

Este comando inicia o servidor de desenvolvimento do PHP.

```bash
php artisan serve
```
> Por padrão, a aplicação estará disponível em: [http://127.0.0.1:8000](http://127.0.0.1:8000)

### Terminal 2: Servidor de Frontend (Vite)

Este comando compila os arquivos CSS e JavaScript e os mantém atualizados enquanto você desenvolve. **É essencial para que o visual da aplicação funcione corretamente.**

```bash
npm run dev
```

**Pronto!** Com os dois servidores rodando, acesse a URL no seu navegador. Você verá a página inicial com os links de "Log in" e "Register" prontos para uso.

---

## Tecnologias Utilizadas

- **Laravel 11**: Framework PHP.
- **Laravel Breeze**: Pacote de autenticação.
- **SQLite**: Banco de dados embarcado.
- **Blade**: Motor de templates do Laravel.
- **Tailwind CSS**: Framework de CSS utility-first.
- **Alpine.js**: Framework JavaScript minimalista.
- **Vite**: Ferramenta de build para o frontend.