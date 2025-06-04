# 🧾 Roteiro Explicativo do Diagrama de Pacotes – Sistema Web (Frontend + Backend + Database)

## 📁 1. FRONTEND
Estrutura organizada em três grandes divisões dentro da pasta `src`:

### 1.1. `pages`
Contém as páginas principais da aplicação (ex: login, cadastro, home, perfil, detalhes do produto e carrinho).

- Importa componentes (seta: `<<import>>`) da pasta `components` para montar a UI.
- Importa rotas da pasta `routes` (seta: `<<import>>`) para configurar a navegação interna entre páginas.
- Utiliza os serviços da pasta `services` (seta: `<<request>>`) para se comunicar com o backend via chamadas HTTP (ex: login, cadastro, obter produtos, etc).

### 1.2. `components`
Contém os elementos reutilizáveis da interface, como:

- `navbar`, `card`, `modalProduto`, etc.
- É importado pelas páginas (`pages`) para compor as interfaces.
- Também pode importar recursos de `assets` (ex: imagens e ícones).

### 1.3. `routes`
Define as rotas e seus respectivos componentes de página.

- Importado por `pages` ou diretamente no arquivo principal de roteamento (ex: `App.tsx`).
- Serve para organizar a navegação SPA (Single Page Application).

### 1.4. `config`
Contém funções responsáveis pelas chamadas HTTP para o backend (ex: `axios`, `fetch`, etc).

- Importado por `pages` para enviar e receber dados via API.
- Seta `<<request>>` conecta `config` ao backend.

### 1.5. `assets`
Contém arquivos estáticos (imagens, ícones, etc.).

- Importado por `components` ou `pages` conforme necessário.

## 📁 2. BACKEND
Estruturado na pasta `src` com camadas bem definidas:

### 2.1. `routes`
Contém os arquivos de definição de rotas da API (ex: `/login`, `/produtos`, `/usuarios`).

- Importa os `controllers` responsáveis pelas lógicas de cada endpoint (`<<import>>`).
- Recebe chamadas do frontend, representadas por uma seta `<<API call>>` partindo de `services` no frontend.

### 2.2. `controllers`
Executam a lógica de negócios com base nas requisições (ex: login, cadastro, CRUD de produtos).

- Importam os `models` para acessar/manipular dados (`<<import>>`).
- Processam os dados e retornam respostas para as rotas, que respondem ao frontend.

### 2.3. `models`
Contêm a definição das entidades e interações com o banco de dados.

- Importam `db/connection` para realizar as queries no banco (`<<connect>>`).

### 2.4. `db/connection`
Define e exporta a configuração de conexão com o banco de dados (ex: Sequelize, Prisma, Knex, etc).

- Conecta diretamente ao banco de dados, conforme representado por uma seta `<<connect>>` até o ícone de "Database".

## 🧪 3. TESTES
Organizados fora da `src`, na pasta `tests`, com duas divisões:

- `unit`: Testa unidades isoladas (ex: controllers, funções puras).
- `integration`: Testa a integração entre camadas (ex: rota + controller + model).

Ambas as pastas de teste importam elementos da `src` para realizar os testes (seta `<<test>>`).

## 🧩 4. INTEGRAÇÃO ENTRE SISTEMAS

### 🔁 Comunicação entre Frontend e Backend
A seta `<<API call>>` representa as chamadas HTTP feitas por `services` no frontend para `routes` no backend.


### 🗄️ Acesso ao Banco de Dados
O backend acessa o **Database** por meio da estrutura:

routes → controllers → models → db/connection → Database