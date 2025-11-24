# API REST Node.js - Sistema de Transações

API RESTful desenvolvida com Node.js, TypeScript, Fastify e Knex para gerenciamento de transações financeiras.

## 📋 Descrição

Esta aplicação permite criar e gerenciar transações financeiras (créditos e débitos), com controle de sessão por usuário e cálculo automático de saldo.

## 🚀 Tecnologias

- **Node.js** - Runtime JavaScript
- **TypeScript** - Superset JavaScript com tipagem estática
- **Fastify** - Framework web rápido e eficiente
- **Knex.js** - Query builder SQL
- **SQLite** - Banco de dados
- **Zod** - Validação de schemas
- **Vitest** - Framework de testes
- **Supertest** - Testes de requisições HTTP

## 📁 Estrutura do Projeto

```
.
├── src/
│   ├── @types/          # Definições de tipos TypeScript
│   ├── env/             # Configurações de variáveis de ambiente
│   ├── middlewares/     # Middlewares da aplicação
│   ├── routes/          # Rotas da API
│   ├── app.ts           # Configuração do Fastify
│   ├── database.ts      # Configuração do Knex
│   └── server.ts        # Inicialização do servidor
├── db/
│   └── migrations/      # Migrações do banco de dados
├── test/
│   └── transactions.spec.ts  # Testes E2E
├── .env                 # Variáveis de ambiente (não versionado)
├── .env.example         # Exemplo de variáveis de ambiente
└── knexfile.ts          # Configuração do Knex CLI
```

## 🔧 Instalação

1. Clone o repositório
2. Instale as dependências:

```bash
npm install
```

3. Configure as variáveis de ambiente:

```bash
cp .env.example .env
cp .env.test.example .env.test
```

4. Execute as migrações do banco de dados:

```bash
npm run knex -- migrate:latest
```

## 🏃 Executando a Aplicação

### Modo Desenvolvimento

```bash
npm run dev
```

### Build para Produção

```bash
npm run build
```

## 🧪 Testes

Execute os testes com:

```bash
npm test
```

## 📚 Rotas da API

### Transações

- **POST** `/transactions` - Cria uma nova transação
  - Body: `{ title: string, amount: number, type: 'credit' | 'debit' }`
- **GET** `/transactions` - Lista todas as transações do usuário
- **GET** `/transactions/:id` - Busca uma transação específica
- **GET** `/transactions/summary` - Retorna o resumo (saldo total)

## 🔐 Autenticação

A API utiliza cookies de sessão (`sessionId`) para identificar usuários. O cookie é criado automaticamente na primeira transação e deve ser enviado nas requisições subsequentes.

## 💾 Banco de Dados

O projeto utiliza SQLite com as seguintes tabelas:

- **transactions**: Armazena as transações financeiras
  - `id`: UUID único
  - `title`: Título da transação
  - `amount`: Valor
  - `created_at`: Data de criação
  - `session_id`: Identificador da sessão do usuário

## 📝 Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo desenvolvimento
- `npm run build` - Compila o projeto TypeScript
- `npm test` - Executa os testes
- `npm run knex` - Interface CLI do Knex para migrações

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests.

## 📄 Licença

ISC

```

```
