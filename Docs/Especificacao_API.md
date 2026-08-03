Especificação das APIs
Objetivo

Definir integralmente o contrato das APIs antes da implementação, permitindo que backend, frontend e testes sejam desenvolvidos sobre a mesma especificação.

Todos os endpoints seguirão o padrão REST, serão documentados automaticamente pelo OpenAPI (Swagger) e utilizarão autenticação JWT quando necessário.

Convenções
URL Base
/api/v1
Content-Type
application/json
Autenticação
Authorization: Bearer <JWT>
Paginação
?page=1

&page_size=20
Ordenação
?sort=name

?sort=-price
Pesquisa
?q=notebook
Filtros
?category=3

?active=true

?min_price=100

?max_price=5000
Padrão de Resposta
Sucesso
{
  "success": true,
  "message": "Operação realizada com sucesso.",
  "data": {},
  "metadata": {}
}
Erro
{
  "success": false,
  "message": "Erro de validação.",
  "errors": [
    {
      "field":"email",
      "message":"E-mail inválido."
    }
  ]
}
Códigos HTTP Padronizados
Código	Utilização
200	Consulta realizada
201	Recurso criado
204	Exclusão sem retorno
400	Dados inválidos
401	Não autenticado
403	Sem permissão
404	Recurso inexistente
409	Violação de regra de negócio
422	Erro de validação
500	Erro interno
Organização das APIs

Teremos aproximadamente 75 endpoints, organizados por domínio.

AUTH
POST /auth/register

Cadastro.

Payload

{
    "full_name":"João Silva",
    "email":"joao@email.com",
    "password":"Senha123"
}

Retorno

201 Created
POST /auth/login

Entrada

{
    "email":"joao@email.com",
    "password":"Senha123"
}

Saída

{
  "token":"JWT",
  "expires_in":1800
}
POST /auth/logout
POST /auth/forgot-password
POST /auth/reset-password
GET /auth/me
USERS
GET /users

Lista usuários.

GET /users/{id}
PUT /users/{id}
DELETE /users/{id}

Soft Delete.

PATCH /users/{id}/activate
PATCH /users/{id}/deactivate
ADDRESSES

GET

POST

PUT

DELETE

CATEGORIES

GET

POST

PUT

DELETE

PRODUCTS
GET /products

Filtros:

categoria
nome
preço
disponibilidade
GET /products/{id}
POST /products
PUT /products/{id}
DELETE /products/{id}
GET /products/{id}/reviews
POST /products/{id}/reviews
GET /products/{id}/images
WISHLIST
GET /wishlist
POST /wishlist/items

Adicionar favorito.

DELETE /wishlist/items/{id}
POST /wishlist/move-to-cart

Excelente cenário para testes de integração.

CART
GET /cart
POST /cart/items

Adicionar produto.

PUT /cart/items/{id}

Alterar quantidade.

DELETE /cart/items/{id}
DELETE /cart

Limpar carrinho.

POST /cart/apply-coupon
DELETE /cart/coupon
COUPONS
GET /coupons
POST /coupons
PUT /coupons/{id}
DELETE /coupons/{id}
CHECKOUT
POST /checkout

Cria pedido.

GET /checkout/summary
POST /checkout/simulate-freight
ORDERS
GET /orders
GET /orders/{id}
PATCH /orders/{id}/cancel
PATCH /orders/{id}/status

(Admin)

PAYMENTS
POST /payments/process

Pagamento simulado.

GET /payments/{id}
POST /payments/refund
REVIEWS
POST /reviews
PUT /reviews/{id}
DELETE /reviews/{id}
NOTIFICATIONS
GET /notifications
PATCH /notifications/{id}/read
PATCH /notifications/read-all
AUDIT
GET /audit

Administrador.

GET /audit/{id}
DASHBOARD
GET /dashboard/admin

Retorna indicadores.

vendas
pedidos
usuários
ticket médio
GET /dashboard/quality

Muito importante para nossa disciplina.

Retornará:

{
   "users":61,
   "orders":355,
   "products":180,
   "stock_alerts":8,
   "inactive_products":14
}

Esse endpoint será utilizado em diversas aulas de testes funcionais, integração e automação.

HEALTH CHECK
GET /health

Retorna:

{
   "status":"UP",
   "database":"UP",
   "version":"1.0"
}

Excelente para CI/CD.

Estrutura dos testes por endpoint

Cada endpoint já nascerá com sua estratégia de validação definida.

Endpoint	Unitário	API	UI	Integração	Performance	Segurança
Login	✔	✔	✔	✔	✔	✔
Cadastro	✔	✔	✔	✔		✔
Produtos	✔	✔	✔	✔	✔	
Carrinho	✔	✔	✔	✔	✔	
Checkout	✔	✔	✔	✔	✔	✔
Pagamento	✔	✔		✔	✔	✔
Dashboard		✔	✔	✔	✔	
Auditoria	✔	✔		✔		✔
Wishlist	✔	✔	✔	✔		
Notificações	✔	✔	✔	✔		
Organização dos Controllers

A implementação seguirá exatamente essa divisão:

app/api/

auth.py

users.py

addresses.py

categories.py

products.py

wishlist.py

cart.py

checkout.py

orders.py

payments.py

reviews.py

notifications.py

audit.py

dashboard.py

health.py

Cada arquivo será responsável apenas por um domínio de negócio, facilitando manutenção e testes.

Evolução da API ao longo da disciplina

O sistema evoluirá em versões controladas para introduzir novos cenários de teste.

Versão	Objetivo didático	Mudanças
1.0	Testes manuais e exploração	CRUDs, autenticação, catálogo, carrinho
1.1	Testes de regressão	Correções e novos bugs planejados
2.0	Testes de API	Endpoints completos, filtros e paginação
2.1	Testes de integração	Auditoria, notificações e histórico
3.0	Performance e CI/CD	Otimizações, métricas, pipeline e observabilidade
