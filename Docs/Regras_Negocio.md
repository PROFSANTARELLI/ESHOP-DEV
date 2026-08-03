Documento de Regras de Negócio
Projeto: EasyShop Web Platform
Versão: 1.0
Objetivo: Definir todas as regras que governam o comportamento do sistema, estabelecendo critérios claros para implementação e validação das funcionalidades.
________________________________________
Organização das Regras
Assim como fizemos com os requisitos, todas as regras serão numeradas.
Módulo	Prefixo
Autenticação	RN-AUT
Usuários	RN-USR
Catálogo	RN-CAT
Produtos	RN-PRO
Carrinho	RN-CAR
Checkout	RN-CHK
Pedidos	RN-ORD
Administração	RN-ADM
Sistema	RN-SYS
Pretendo criar aproximadamente 90 regras de negócio, todas testáveis.
________________________________________
Estrutura Padrão
Cada regra seguirá exatamente este formato.
Código

Nome

Descrição

Justificativa

Requisitos relacionados

Impacto

Exemplo

Possíveis cenários de teste
Isso facilitará muito quando chegarmos às aulas de QA.
________________________________________
MÓDULO AUTENTICAÇÃO
________________________________________
RN-AUT-001 — E-mail único
Descrição
Cada usuário deverá possuir um endereço de e-mail exclusivo.
Não será permitido cadastrar duas contas utilizando o mesmo e-mail.
Requisitos relacionados
RF-AUT-001
RF-AUT-002
Impacto
Evita duplicidade de identidade.
Exemplo
joao@email.com

Cadastro permitido.

-----------------

joao@email.com

Novo cadastro.

Cadastro rejeitado.
Cenários futuros
•	e-mail duplicado; 
•	diferença entre maiúsculas e minúsculas; 
•	espaços antes/depois; 
•	caracteres Unicode. 
________________________________________
RN-AUT-002 — Complexidade da senha
A senha deverá possuir:
•	mínimo de 8 caracteres; 
•	uma letra maiúscula; 
•	uma letra minúscula; 
•	um número. 
Caracteres especiais serão recomendados, mas não obrigatórios.
Cenários
Senha curta.
Senha sem número.
Senha somente números.
Senha muito longa.
Senha com espaços.
________________________________________
RN-AUT-003 — Bloqueio por tentativas
Após cinco tentativas consecutivas de autenticação inválida, a conta permanecerá bloqueada por quinze minutos.
Objetivo
Mitigar ataques de força bruta.
________________________________________
RN-AUT-004 — Sessão
A sessão expirará após trinta minutos de inatividade.
________________________________________
RN-AUT-005 — Exclusão lógica
Usuários excluídos permanecerão armazenados no banco, sendo marcados como inativos.
________________________________________
MÓDULO PRODUTOS
________________________________________
RN-PRO-001 — Produto indisponível
Produtos com estoque igual a zero poderão ser visualizados, porém não poderão ser adicionados ao carrinho.
________________________________________
RN-PRO-002 — Preço
Todo produto deverá possuir preço maior que zero.
________________________________________
RN-PRO-003 — Categoria obrigatória
Todo produto deverá pertencer a uma categoria.
________________________________________
RN-PRO-004 — Nome único
Não poderão existir produtos ativos com o mesmo nome dentro da mesma categoria.
________________________________________
RN-PRO-005 — Avaliação
Somente clientes que compraram o produto poderão avaliá-lo.
________________________________________
RN-PRO-006 — Nota
As avaliações aceitarão apenas valores inteiros entre 1 e 5.
________________________________________
RN-PRO-007 — Exclusão
Produtos utilizados em pedidos não poderão ser removidos fisicamente.
________________________________________
RN-PRO-008 — Imagem principal
Todo produto deverá possuir pelo menos uma imagem.
________________________________________
MÓDULO CARRINHO
________________________________________
RN-CAR-001 — Quantidade
Cada item poderá possuir quantidade entre 1 e 99 unidades.
________________________________________
RN-CAR-002 — Produto repetido
Adicionar novamente o mesmo produto deverá incrementar sua quantidade, e não criar uma nova linha.
________________________________________
RN-CAR-003 — Estoque
A quantidade solicitada nunca poderá ultrapassar o estoque disponível.
________________________________________
RN-CAR-004 — Carrinho vazio
Carrinhos vazios não poderão iniciar o checkout.
________________________________________
RN-CAR-005 — Persistência
O carrinho deverá permanecer salvo após logout.
________________________________________
RN-CAR-006 — Cálculo
O subtotal será calculado pela fórmula:
Quantidade × Preço Unitário
________________________________________
RN-CAR-007 — Cupom
Somente um cupom poderá ser aplicado por pedido.
________________________________________
RN-CAR-008 — Frete
O frete será calculado antes da confirmação do pedido.
________________________________________
MÓDULO CHECKOUT
________________________________________
RN-CHK-001 — Endereço
O usuário deverá possuir pelo menos um endereço cadastrado.
________________________________________
RN-CHK-002 — Pagamento
Pedidos somente serão confirmados após pagamento autorizado.
________________________________________
RN-CHK-003 — Estoque
O estoque será reduzido apenas após confirmação do pedido.
________________________________________
RN-CHK-004 — Atomicidade
A criação do pedido deverá ocorrer dentro de uma transação única.
________________________________________
RN-CHK-005 — Número do pedido
Cada pedido receberá um identificador único.
________________________________________
MÓDULO PEDIDOS
________________________________________
RN-ORD-001
Pedidos cancelados não poderão retornar ao status "Pago".
________________________________________
RN-ORD-002
Pedidos entregues não poderão ser cancelados.
________________________________________
RN-ORD-003
Pedidos pagos poderão ser cancelados apenas antes da expedição.
________________________________________
RN-ORD-004
Cada alteração de status deverá gerar registro de auditoria.
________________________________________
RN-ORD-005
Todo pedido deverá possuir pelo menos um item.
________________________________________
MÓDULO ADMINISTRAÇÃO
________________________________________
RN-ADM-001
Somente administradores poderão cadastrar produtos.
________________________________________
RN-ADM-002
Somente administradores poderão alterar estoque.
________________________________________
RN-ADM-003
Exclusões deverão ser registradas em auditoria.
________________________________________
RN-ADM-004
Alterações de preço deverão registrar usuário, data e valor anterior.
________________________________________
RN-ADM-005
Produtos inativos não deverão aparecer no catálogo.
________________________________________
MÓDULO SISTEMA
________________________________________
RN-SYS-001
Todas as exceções deverão ser registradas em log.
________________________________________
RN-SYS-002
Mensagens de erro não deverão expor detalhes técnicos ao usuário.
________________________________________
RN-SYS-003
Datas serão armazenadas em UTC.
________________________________________
RN-SYS-004
Todos os identificadores utilizarão UUID.
________________________________________
RN-SYS-005
Toda operação crítica deverá gerar evento de auditoria.
________________________________________
Matriz de Rastreabilidade
Um diferencial importante será relacionar cada regra aos requisitos funcionais e aos futuros testes.
Regra	Requisitos	Tipo de teste predominante
RN-AUT-001	RF-AUT-001, RF-AUT-002	Funcional, API e Integração
RN-AUT-003	RF-AUT-004	Funcional, Segurança e API
RN-PRO-001	RF-PRO-001, RF-CAR-001	Funcional, UI e Integração
RN-CAR-002	RF-CAR-001	Integração, API e UI
RN-CHK-004	RF-CHK-005	Integração e End-to-End
RN-ORD-002	RF-ORD-003	Funcional e Regressão
RN-ADM-002	RF-ADM-006	Segurança, API e Integração

