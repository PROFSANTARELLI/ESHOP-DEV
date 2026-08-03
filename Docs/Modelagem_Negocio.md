Modelagem do Domínio do Negócio

Esta etapa normalmente é ignorada em projetos acadêmicos, mas ela é praticamente obrigatória em projetos profissionais.

O maior erro que vejo em equipes iniciantes é começar modelando tabelas do banco de dados. Em empresas maduras, primeiro se modela o negócio, depois o banco.

Como o EasyShop será utilizado durante toda a disciplina, precisamos definir com precisão quais são as entidades do domínio e como elas se relacionam.

Essa etapa servirá como base para:

banco de dados;
APIs REST;
backend;
frontend;
casos de teste;
massa de dados;
testes de integração;
testes de API.

Ou seja, ela será reutilizada praticamente em todas as fases seguintes.

Objetivos da Etapa

Ao final desta etapa teremos:

Modelo conceitual do domínio
Glossário de negócio
Entidades do domínio
Relacionamentos
Regras de cardinalidade
Ciclo de vida das entidades
Diagrama conceitual
Dicionário de domínio

Ainda não definiremos tipos de dados nem tabelas. Estamos modelando o negócio.

Entidades do Domínio

Proponho as seguintes entidades principais.

Usuário (User)

Representa qualquer pessoa cadastrada na plataforma.

Responsabilidades:

autenticação;
manutenção de perfil;
realização de compras;
gerenciamento de endereços.
Perfil (Role)

Define o nível de acesso.

Perfis previstos:

Cliente
Administrador

No futuro, poderemos incluir Operador ou Analista sem alterar a arquitetura.

Endereço (Address)

Cada usuário poderá possuir vários endereços.

Utilizado para:

entrega;
cobrança.
Categoria (Category)

Agrupa produtos semelhantes.

Exemplos:

Informática
Livros
Eletrônicos
Casa
Produto (Product)

Principal entidade comercial.

Possui:

nome;
descrição;
preço;
estoque;
categoria;
imagens;
avaliações.
Imagem do Produto (ProductImage)

Permite múltiplas imagens para um mesmo produto.

Avaliação (Review)

Relaciona:

Usuário → Produto.

Contém:

nota;
comentário;
data.
Carrinho (Cart)

Existe um carrinho por usuário.

Pode estar:

ativo;
convertido em pedido;
abandonado.
Item do Carrinho (CartItem)

Representa um produto dentro do carrinho.

Cupom (Coupon)

Possui:

código;
validade;
percentual ou valor;
regras de utilização.
Pedido (Order)

Representa uma compra concluída.

Possui estados bem definidos.

Item do Pedido (OrderItem)

Congela as informações do produto no momento da compra.

Isso evita inconsistências quando o produto muda de preço.

Pagamento (Payment)

Nesta primeira versão será totalmente simulado.

Estados:

Pendente
Aprovado
Recusado
Cancelado
Auditoria (AuditLog)

Registra operações importantes.

Relacionamentos:

<img width="385" height="598" alt="image" src="https://github.com/user-attachments/assets/c7c0fc5f-bf94-4d7b-96df-cf2984f5d246" />

Ciclo de Vida das Entidades

Uma parte importante para os testes será definir o ciclo de vida de cada entidade.

Pedido
Criado

↓

Pagamento Pendente

↓

Pagamento Aprovado

↓

Separação

↓

Enviado

↓

Entregue

Fluxos alternativos:

Pagamento Recusado

↓

Cancelado

ou

Pagamento Aprovado

↓

Cancelado
Carrinho
Criado

↓

Ativo

↓

Checkout

↓

Convertido em Pedido
Pagamento
Pendente

↓

Aprovado

ou

Pendente

↓

Recusado
Glossário do Domínio

Este documento eliminará ambiguidades.

Exemplos:

Termo	Definição
Cliente	Usuário autenticado com permissão para realizar compras
Carrinho	Conjunto temporário de produtos selecionados
Pedido	Registro permanente de uma compra
Item do Pedido	Cópia imutável dos dados do produto no momento da compra
Cupom	Código promocional com regras de desconto
Checkout	Processo de conversão do carrinho em pedido
Pagamento	Registro da autorização da compra
Auditoria	Histórico das operações críticas do sistema
Eventos de Negócio

Também proponho documentar os eventos principais, pois eles serão úteis para testes de integração e auditoria.

Usuário cadastrado
Usuário autenticado
Produto criado
Produto atualizado
Produto removido
Produto adicionado ao carrinho
Carrinho atualizado
Cupom aplicado
Checkout iniciado
Pedido criado
Pagamento aprovado
Pagamento recusado
Pedido cancelado
Estoque atualizado

Esses eventos futuramente alimentarão os logs e os testes de auditoria.

Decisões arquiteturais do domínio

Para garantir consistência, proponho algumas decisões desde já:

Todos os identificadores utilizarão UUID, evitando dependência de IDs sequenciais.
Exclusão lógica (soft delete) será aplicada a Usuário, Produto, Categoria e Cupom, preservando o histórico.
Os pedidos serão imutáveis após a confirmação; alterações ocorrerão apenas por mudança de status.
O preço gravado em OrderItem será uma cópia do valor vigente no momento da compra, independentemente de alterações futuras no catálogo.
O histórico de auditoria nunca poderá ser alterado ou excluído pela aplicação.


