# E-commerce API com Flask

Este projeto é uma API para um sistema de e-commerce simples, construído com Flask. Ele oferece funcionalidades para gerenciar produtos, usuários e carrinhos de compras. A API permite que os usuários façam login, adicione produtos ao carrinho, vejam detalhes de produtos e realizem checkouts.

## Tecnologias Utilizadas

- **Flask** - Framework web em Python.
- **Flask-SQLAlchemy** - ORM para interagir com o banco de dados.
- **Flask-Login** - Gerenciamento de autenticação de usuários.
- **Flask-CORS** - Habilitar Cross-Origin Resource Sharing.
- **SQLite** - Banco de dados relacional embutido.

## Funcionalidades

- **Autenticação**:
  - Login de usuários.
  - Logout.
- **Gerenciamento de Produtos**:
  - Adicionar, atualizar e deletar produtos.
  - Listar todos os produtos.
  - Visualizar detalhes de um produto específico.
- **Carrinho de Compras**:
  - Adicionar e remover produtos no carrinho.
  - Exibir o conteúdo do carrinho.
  - Finalizar compra (checkout).
  
## Rotas da API

### Autenticação

- **Login**: `POST /login`
- **Logout**: `POST /logout`
  
### Usuários

- **Adicionar usuário**: `POST /api/users/add`

### Produtos

- **Listar produtos**: `GET /api/products`
- **Detalhes de produto**: `GET /api/products/<product_id>`
- **Adicionar produto**: `POST /api/products/add` *(Requer autenticação)*
- **Atualizar produto**: `PUT /api/products/update/<product_id>` *(Requer autenticação)*
- **Deletar produto**: `DELETE /api/products/delete/<product_id>` *(Requer autenticação)*

### Carrinho

- **Adicionar ao carrinho**: `POST /api/cart/add/<product_id>` *(Requer autenticação)*
- **Remover do carrinho**: `DELETE /api/cart/remove/<item_id>` *(Requer autenticação)*
- **Visualizar carrinho**: `GET /api/cart` *(Requer autenticação)*
- **Finalizar compra (Checkout)**: `POST /api/cart/checkout` *(Requer autenticação)*

## Requisitos

- **Python 3.8+**
- **Flask 2.0+**
- **SQLite** (ou qualquer outro banco de dados suportado pelo SQLAlchemy)

## Como Rodar o Projeto

1. **Clone o repositório**:
   ```bash
   git clone <url-do-repositorio>
   cd ecommerce-flask
   ```

2. **Crie e ative um ambiente virtual**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # Linux/MacOS
   venv\Scripts\activate     # Windows
   ```

3. **Instale as dependências**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Inicialize o banco de dados**:
   ```bash
   flask shell
   >>> from app import db
   >>> db.create_all()
   >>> exit()
   ```

5. **Rode o servidor**:
   ```bash
   flask run
   ```

6. **Acesse a aplicação**:
   O servidor estará rodando em `http://127.0.0.1:5000`.

## Autenticação

Esta API usa `Flask-Login` para gerenciar sessões de usuário. A autenticação é necessária para certas rotas, como adicionar produtos ao carrinho, finalizar compras e gerenciar produtos.

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou fazer pull requests para melhorias.

## Licença

Este projeto está sob a licença MIT.

--- 

Esse README fornece uma visão geral do projeto, as funcionalidades disponíveis e como configurar o ambiente local para execução.