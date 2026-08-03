Especificação de Requisitos Funcionais
Projeto: EasyShop Web Platform
Versão: 1.0
Objetivo: Definir todas as funcionalidades do sistema de forma clara, completa e verificável.
________________________________________
Organização dos Requisitos
Os requisitos serão agrupados por módulos:
Módulo	Prefixo
Autenticação	AUT
Usuários	USR
Catálogo	CAT
Produtos	PRO
Carrinho	CAR
Checkout	CHK
Pedidos	ORD
Administração	ADM
API	API
Auditoria	AUD
Sistema	SYS
Ao todo, teremos 100 requisitos funcionais, distribuídos entre os módulos.
________________________________________
MÓDULO 1 — AUTENTICAÇÃO (AUT)
RF-AUT-001 — Cadastro de usuário
O sistema deve permitir que novos usuários realizem cadastro informando:
•	Nome completo 
•	E-mail 
•	Senha 
•	Confirmação da senha 
________________________________________
RF-AUT-002 — Validação de e-mail único
Não deve ser permitido cadastrar dois usuários utilizando o mesmo endereço de e-mail.
________________________________________
RF-AUT-003 — Validação de senha
A senha deverá possuir:
•	mínimo de 8 caracteres; 
•	pelo menos uma letra maiúscula; 
•	pelo menos uma letra minúscula; 
•	pelo menos um número. 
________________________________________
RF-AUT-004 — Login
O usuário poderá autenticar-se utilizando:
•	e-mail; 
•	senha. 
________________________________________
RF-AUT-005 — Logout
O sistema deverá invalidar a sessão do usuário.
________________________________________
RF-AUT-006 — Recuperação de senha
Permitir solicitação de redefinição.
________________________________________
RF-AUT-007 — Alteração de senha
Usuários autenticados poderão alterar sua senha.
________________________________________
RF-AUT-008 — Perfil
Visualizar informações pessoais.
________________________________________
RF-AUT-009 — Atualização de perfil
Editar nome e telefone.
________________________________________
RF-AUT-010 — Exclusão de conta
Permitir encerramento da conta mediante confirmação.
________________________________________
MÓDULO 2 — CATÁLOGO (CAT)
RF-CAT-001
Listar produtos disponíveis.
________________________________________
RF-CAT-002
Pesquisar produtos por nome.
________________________________________
RF-CAT-003
Pesquisar por categoria.
________________________________________
RF-CAT-004
Pesquisar por faixa de preço.
________________________________________
RF-CAT-005
Pesquisar por disponibilidade.
________________________________________
RF-CAT-006
Ordenar produtos por:
•	nome 
•	preço 
•	popularidade 
________________________________________
RF-CAT-007
Paginar resultados.
________________________________________
RF-CAT-008
Exibir produtos relacionados.
________________________________________
RF-CAT-009
Exibir produtos em destaque.
________________________________________
RF-CAT-010
Permitir pesquisa parcial.
________________________________________
MÓDULO 3 — PRODUTOS (PRO)
RF-PRO-001
Visualizar detalhes do produto.
________________________________________
RF-PRO-002
Exibir descrição completa.
________________________________________
RF-PRO-003
Exibir imagens.
________________________________________
RF-PRO-004
Exibir estoque disponível.
________________________________________
RF-PRO-005
Exibir avaliações.
________________________________________
RF-PRO-006
Cadastrar avaliações.
________________________________________
RF-PRO-007
Editar avaliação.
________________________________________
RF-PRO-008
Excluir avaliação.
________________________________________
RF-PRO-009
Calcular média das avaliações.
________________________________________
RF-PRO-010
Exibir produtos similares.
________________________________________
MÓDULO 4 — CARRINHO (CAR)
RF-CAR-001
Adicionar produtos.
________________________________________
RF-CAR-002
Alterar quantidade.
________________________________________
RF-CAR-003
Remover produtos.
________________________________________
RF-CAR-004
Limpar carrinho.
________________________________________
RF-CAR-005
Calcular subtotal.
________________________________________
RF-CAR-006
Aplicar cupom.
________________________________________
RF-CAR-007
Remover cupom.
________________________________________
RF-CAR-008
Calcular frete.
________________________________________
RF-CAR-009
Atualizar total automaticamente.
________________________________________
RF-CAR-010
Persistir carrinho do usuário.
________________________________________
MÓDULO 5 — CHECKOUT (CHK)
RF-CHK-001
Selecionar endereço.
________________________________________
RF-CHK-002
Cadastrar endereço.
________________________________________
RF-CHK-003
Selecionar transportadora.
________________________________________
RF-CHK-004
Selecionar forma de pagamento.
________________________________________
RF-CHK-005
Confirmar pedido.
________________________________________
RF-CHK-006
Gerar número do pedido.
________________________________________
RF-CHK-007
Registrar pagamento.
________________________________________
RF-CHK-008
Atualizar estoque.
________________________________________
RF-CHK-009
Enviar confirmação.
________________________________________
RF-CHK-010
Gerar histórico.
________________________________________
MÓDULO 6 — PEDIDOS (ORD)
RF-ORD-001
Listar pedidos.
________________________________________
RF-ORD-002
Consultar pedido.
________________________________________
RF-ORD-003
Cancelar pedido.
________________________________________
RF-ORD-004
Atualizar status.
________________________________________
RF-ORD-005
Consultar rastreamento.
________________________________________
RF-ORD-006
Visualizar nota fiscal simulada.
________________________________________
RF-ORD-007
Permitir recompra.
________________________________________
RF-ORD-008
Emitir comprovante.
________________________________________
RF-ORD-009
Filtrar pedidos.
________________________________________
RF-ORD-010
Pesquisar pedidos.
________________________________________
MÓDULO 7 — ADMINISTRAÇÃO (ADM)
RF-ADM-001
Cadastrar produtos.
________________________________________
RF-ADM-002
Editar produtos.
________________________________________
RF-ADM-003
Excluir produtos.
________________________________________
RF-ADM-004
Cadastrar categorias.
________________________________________
RF-ADM-005
Editar categorias.
________________________________________
RF-ADM-006
Controlar estoque.
________________________________________
RF-ADM-007
Atualizar preços.
________________________________________
RF-ADM-008
Visualizar pedidos.
________________________________________
RF-ADM-009
Atualizar status dos pedidos.
________________________________________
RF-ADM-010
Consultar dashboard administrativo.
________________________________________
MÓDULO 8 — API REST (API)
RF-API-001
Disponibilizar autenticação via API.
________________________________________
RF-API-002
Disponibilizar consulta de produtos.
________________________________________
RF-API-003
Disponibilizar operações do carrinho.
________________________________________
RF-API-004
Disponibilizar operações de pedidos.
________________________________________
RF-API-005
Disponibilizar operações administrativas autenticadas.
________________________________________
RF-API-006
Retornar respostas JSON padronizadas.
________________________________________
RF-API-007
Documentar APIs via OpenAPI.
________________________________________
RF-API-008
Validar autenticação JWT.
________________________________________
RF-API-009
Retornar códigos HTTP compatíveis.
________________________________________
RF-API-010
Registrar logs das chamadas.
________________________________________
MÓDULO 9 — AUDITORIA (AUD)
RF-AUD-001
Registrar login.
________________________________________
RF-AUD-002
Registrar logout.
________________________________________
RF-AUD-003
Registrar alterações cadastrais.
________________________________________
RF-AUD-004
Registrar alterações de produtos.
________________________________________
RF-AUD-005
Registrar pedidos.
________________________________________
RF-AUD-006
Registrar cancelamentos.
________________________________________
RF-AUD-007
Registrar erros críticos.
________________________________________
RF-AUD-008
Registrar chamadas administrativas.
________________________________________
RF-AUD-009
Consultar histórico de auditoria.
________________________________________
RF-AUD-010
Exportar auditoria.
________________________________________
MÓDULO 10 — SISTEMA (SYS)
RF-SYS-001
Página inicial responsiva.
________________________________________
RF-SYS-002
Página de erro personalizada.
________________________________________
RF-SYS-003
Menu adaptado ao perfil do usuário.
________________________________________
RF-SYS-004
Exibir mensagens de sucesso.
________________________________________
RF-SYS-005
Exibir mensagens de erro.
________________________________________
RF-SYS-006
Exibir carregamento durante operações.
________________________________________
RF-SYS-007
Permitir paginação em tabelas.
________________________________________
RF-SYS-008
Registrar logs internos.
________________________________________
RF-SYS-009
Permitir configuração por variáveis de ambiente.
________________________________________
RF-SYS-010
Disponibilizar documentação técnica da API.
________________________________________
Resumo Geral
Módulo	Quantidade
Autenticação	10
Catálogo	10
Produtos	10
Carrinho	10
Checkout	10
Pedidos	10
Administração	10
API REST	10
Auditoria	10
Sistema	10
Total	100


________________________________________
Documento de Critérios de Aceitação e Cenários BDD
Projeto: EasyShop Web Platform
Versão: 1.0
________________________________________
Estrutura do Documento
Cada requisito possuirá exatamente a mesma estrutura.
RF-XXX

Objetivo

Regras de negócio relacionadas

Pré-condições

Fluxo principal

Fluxos alternativos

Critérios de Aceitação (BDD)

Observações
Essa padronização facilitará enormemente a construção das aulas.
________________________________________
Módulo AUTENTICAÇÃO
________________________________________
RF-AUT-001 — Cadastro de Usuário
Objetivo
Permitir que novos usuários criem uma conta na plataforma.
________________________________________
Regras relacionadas
•	RN-001 
•	RN-002 
•	RN-005 
________________________________________
Pré-condições
O e-mail informado ainda não está cadastrado.
________________________________________
Fluxo Principal
1.	Usuário acessa Cadastro. 
2.	Preenche os campos obrigatórios. 
3.	Confirma senha. 
4.	Clica em "Cadastrar". 
5.	Conta criada. 
________________________________________
Fluxos Alternativos
FA-01
E-mail já utilizado.
________________________________________
FA-02
Senha inválida.
________________________________________
FA-03
Campos obrigatórios vazios.
________________________________________
Critérios de Aceitação (BDD)
Cenário 1
Dado que o usuário não possui cadastro
Quando preencher todos os campos corretamente
Então o sistema deverá criar sua conta e redirecioná-lo para a página de login.
________________________________________
Cenário 2
Dado que o e-mail informado já existe
Quando tentar cadastrar novamente
Então o sistema deverá impedir o cadastro e exibir mensagem apropriada.
________________________________________
Cenário 3
Dado que a senha não atende às regras definidas
Quando enviar o formulário
Então o cadastro deverá ser rejeitado.
________________________________________
Cenário 4
Dado que existem campos obrigatórios vazios
Quando confirmar o cadastro
Então o sistema deverá indicar todos os campos pendentes.

Casos que deverão ser testados futuramente
•	Nome vazio 
•	Nome muito grande 
•	E-mail inválido 
•	E-mail duplicado 
•	Senha fraca 
•	Senha diferente da confirmação 
•	SQL Injection 
•	XSS 
•	Espaços em branco 
•	Caracteres especiais 
Observe que essa última seção não faz parte do BDD. Ela foi adicionada pensando na disciplina, para que os alunos consigam visualizar rapidamente quais cenários poderão gerar casos de teste.
________________________________________
RF-AUT-004 — Login
Objetivo
Permitir autenticação de usuários.
________________________________________
Fluxo Principal
1.	Informar e-mail. 
2.	Informar senha. 
3.	Validar credenciais. 
4.	Criar sessão. 
5.	Redirecionar para Home. 
________________________________________
Fluxos Alternativos
Senha incorreta.
Conta inexistente.
Conta bloqueada.
Sessão expirada.
________________________________________
Critérios de Aceitação
Cenário 1
Dado que o usuário possui cadastro
Quando informar credenciais válidas
Então deverá acessar sua conta.
________________________________________
Cenário 2
Dado que a senha está incorreta
Quando realizar login
Então o acesso deverá ser negado.
________________________________________
Cenário 3
Dado que o e-mail não existe
Quando tentar autenticar
Então o sistema deverá informar credenciais inválidas.
________________________________________
Cenário 4
Dado que a conta esteja bloqueada
Quando tentar acessar
Então o login deverá ser recusado.
________________________________________
Casos futuros
•	senha vazia; 
•	e-mail vazio; 
•	senha muito longa; 
•	SQL Injection; 
•	brute force; 
•	caracteres Unicode; 
•	espaços antes/depois do e-mail; 
•	sessão expirada. 
________________________________________
RF-CAR-006 — Aplicação de Cupom
Objetivo
Permitir utilização de cupons de desconto.
________________________________________
Critérios BDD
Cenário 1
Dado que existe um cupom válido
Quando o cliente aplicá-lo
Então o desconto deverá ser calculado.
________________________________________
Cenário 2
Dado que o cupom expirou
Quando for utilizado
Então o sistema deverá recusá-lo.
________________________________________
Cenário 3
Dado que o cupom exige valor mínimo
Quando o carrinho possuir valor inferior
Então o desconto não deverá ser aplicado.
________________________________________
Cenário 4
Dado que o cupom já foi utilizado
Quando o cliente tentar reutilizá-lo
Então o sistema deverá impedir a operação.
________________________________________
Casos para QA
•	cupom vazio; 
•	cupom inexistente; 
•	cupom expirado; 
•	letras minúsculas; 
•	letras maiúsculas; 
•	espaços extras; 
•	caracteres especiais; 
•	desconto superior ao permitido. 
________________________________________
RF-CHK-005 — Confirmação do Pedido
Critérios BDD
Cenário 1
Dado que todos os dados estão corretos
Quando confirmar o pedido
Então o pedido deverá ser criado.
________________________________________
Cenário 2
Dado que o estoque acabou
Quando confirmar a compra
Então a operação deverá ser cancelada.
________________________________________
Cenário 3
Dado que o pagamento falhou
Quando concluir o checkout
Então nenhum pedido deverá ser registrado.
________________________________________
Casos futuros
•	estoque simultâneo; 
•	timeout; 
•	pagamento duplicado; 
•	dupla confirmação; 
•	refresh da página; 
•	perda de conexão; 
•	cancelamento durante pagamento. 
________________________________________
Estrutura que seguiremos para os 100 requisitos
Cada requisito possuirá um conjunto padronizado de artefatos:
Item	Finalidade
Objetivo	Explicar a funcionalidade
Pré-condições	Estado necessário antes da execução
Fluxo Principal	Caminho esperado da funcionalidade
Fluxos Alternativos	Exceções e variações
Critérios BDD	Base para validação funcional
Casos para QA	Ideias de cenários positivos, negativos e de borda
Regras de Negócio	Referência cruzada com o documento de regras
Prioridade	Essencial, Alta, Média ou Baixa
Complexidade	Baixa, Média ou Alta
Tipo de Teste	Unitário, Integração, API, UI, E2E, Performance, Segurança etc.
A melhoria que considero o maior diferencial da disciplina
Gostaria de acrescentar mais uma coluna, que raramente aparece em documentação acadêmica, mas é extremamente útil em projetos reais: a Estratégia de Teste Recomendada.
Para cada requisito, definiremos explicitamente como ele deverá ser validado. Por exemplo:
Requisito	Estratégia principal
RF-AUT-004 (Login)	API + UI + Segurança
RF-CAR-006 (Cupom)	Integração + Regras de Negócio
RF-CHK-005 (Checkout)	End-to-End + Performance
RF-API-009 (Códigos HTTP)	API
RF-AUD-003 (Auditoria)	Integração + Banco de Dados
Quando chegarmos às aulas práticas, bastará consultar esse catálogo para saber quais requisitos serão exercitados, quais técnicas de teste serão aplicadas e quais artefatos deverão ser produzidos.

