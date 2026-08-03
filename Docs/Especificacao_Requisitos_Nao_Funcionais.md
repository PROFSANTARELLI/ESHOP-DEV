Especificação dos Requisitos Não Funcionais (RNF)
Projeto: EasyShop Web Platform
Versão: 1.0
Objetivo: Definir os requisitos de qualidade que deverão ser atendidos pelo sistema, estabelecendo critérios mensuráveis para desempenho, segurança, confiabilidade, usabilidade, manutenção e operação.
________________________________________
Organização dos Requisitos
Os requisitos serão agrupados em categorias:
Categoria	Prefixo
Desempenho	RNF-PER
Segurança	RNF-SEG
Disponibilidade	RNF-DIS
Usabilidade	RNF-USA
Confiabilidade	RNF-CON
Escalabilidade	RNF-ESC
Compatibilidade	RNF-COM
Manutenibilidade	RNF-MAN
Observabilidade	RNF-OBS
Implantação	RNF-DEP
Teremos 50 requisitos não funcionais.
________________________________________
1. Desempenho (RNF-PER)
RNF-PER-001 — Tempo de resposta
O sistema deverá responder às requisições HTTP em até 2 segundos para 95% das operações em condições normais de uso.
Validação: Testes de performance com Apache JMeter.
________________________________________
RNF-PER-002 — Página inicial
A página inicial deverá carregar completamente em até 3 segundos utilizando conexão banda larga.
________________________________________
RNF-PER-003 — Pesquisa de produtos
A pesquisa deverá retornar resultados em até 1 segundo, considerando uma base de até 10.000 produtos.
________________________________________
RNF-PER-004 — Login
A autenticação deverá ser concluída em até 1 segundo.
________________________________________
RNF-PER-005 — Checkout
A confirmação do pedido deverá ser processada em até 5 segundos, desconsiderando integrações externas simuladas.
________________________________________
2. Segurança (RNF-SEG)
RNF-SEG-001 — Comunicação segura
Toda comunicação deverá ocorrer exclusivamente via HTTPS em ambientes de produção.
________________________________________
RNF-SEG-002 — Senhas
As senhas nunca deverão ser armazenadas em texto puro, devendo utilizar algoritmo de hash seguro.
________________________________________
RNF-SEG-003 — Autenticação
A autenticação deverá utilizar JWT com tempo de expiração configurável.
________________________________________
RNF-SEG-004 — Controle de acesso
Usuários só poderão acessar funcionalidades compatíveis com seu perfil.
________________________________________
RNF-SEG-005 — Proteção contra SQL Injection
Todas as consultas deverão utilizar mecanismos seguros de acesso ao banco de dados, evitando concatenação direta de comandos SQL.
________________________________________
3. Disponibilidade (RNF-DIS)
RNF-DIS-001
O sistema deverá estar disponível em 99% do tempo durante o período de utilização previsto.
________________________________________
RNF-DIS-002
Falhas em uma requisição não deverão comprometer o funcionamento das demais.
________________________________________
RNF-DIS-003
O sistema deverá apresentar mensagens amigáveis em situações de indisponibilidade.
________________________________________
RNF-DIS-004
Erros inesperados deverão ser registrados em log.
________________________________________
RNF-DIS-005
Serviços deverão ser reinicializáveis sem perda de dados persistentes.
________________________________________
4. Usabilidade (RNF-USA)
RNF-USA-001
Todas as telas deverão apresentar identidade visual consistente.
________________________________________
RNF-USA-002
Mensagens de erro deverão ser claras e compreensíveis.
________________________________________
RNF-USA-003
Campos obrigatórios deverão ser identificados visualmente.
________________________________________
RNF-USA-004
O sistema deverá ser responsivo para desktop, tablet e smartphone.
________________________________________
RNF-USA-005
O fluxo de compra deverá ser concluído em no máximo cinco etapas.
________________________________________
5. Confiabilidade (RNF-CON)
RNF-CON-001
Nenhuma operação deverá gerar inconsistências entre banco de dados e interface.
________________________________________
RNF-CON-002
Pedidos confirmados deverão permanecer registrados mesmo após reinicialização da aplicação.
________________________________________
RNF-CON-003
Alterações de estoque deverão ocorrer de forma transacional.
________________________________________
RNF-CON-004
Operações críticas deverão possuir tratamento de exceções.
________________________________________
RNF-CON-005
Falhas não deverão corromper dados persistidos.
________________________________________
6. Escalabilidade (RNF-ESC)
RNF-ESC-001
O sistema deverá suportar pelo menos 500 usuários simultâneos em ambiente de testes.
________________________________________
RNF-ESC-002
A arquitetura deverá permitir expansão horizontal dos serviços.
________________________________________
RNF-ESC-003
A camada de aplicação deverá permanecer desacoplada da persistência.
________________________________________
RNF-ESC-004
Consultas frequentes deverão ser passíveis de otimização.
________________________________________
RNF-ESC-005
A aplicação deverá operar corretamente com bases contendo até 100.000 pedidos.
________________________________________
7. Compatibilidade (RNF-COM)
RNF-COM-001
Compatível com as versões recentes de Chrome, Edge e Firefox.
________________________________________
RNF-COM-002
As APIs deverão seguir o padrão REST utilizando JSON.
________________________________________
RNF-COM-003
O sistema deverá executar em Docker sem alterações no código-fonte.
________________________________________
RNF-COM-004
O ambiente oficial será GitHub Codespaces.
________________________________________
RNF-COM-005
A aplicação deverá ser independente do sistema operacional do usuário.
________________________________________
8. Manutenibilidade (RNF-MAN)
RNF-MAN-001
O código deverá seguir o padrão PEP 8.
________________________________________
RNF-MAN-002
Toda API deverá possuir documentação OpenAPI/Swagger.
________________________________________
RNF-MAN-003
O projeto deverá utilizar migrações versionadas com Alembic.
________________________________________
RNF-MAN-004
Os módulos deverão possuir baixo acoplamento e alta coesão.
________________________________________
RNF-MAN-005
O código deverá ser organizado em camadas (Controller, Service, Repository e Model).
________________________________________
9. Observabilidade (RNF-OBS)
RNF-OBS-001
Todas as exceções deverão ser registradas em log.
________________________________________
RNF-OBS-002
Operações administrativas deverão gerar registros de auditoria.
________________________________________
RNF-OBS-003
Chamadas às APIs deverão possuir identificação temporal.
________________________________________
RNF-OBS-004
Logs deverão possuir níveis (INFO, WARNING, ERROR).
________________________________________
RNF-OBS-005
Os registros deverão permitir rastrear a execução das operações.
________________________________________
10. Implantação (RNF-DEP)
RNF-DEP-001
Toda a aplicação deverá ser executada por Docker Compose.
________________________________________
RNF-DEP-002
O ambiente deverá iniciar completamente com um único comando.
________________________________________
RNF-DEP-003
O banco deverá ser inicializado automaticamente com dados de demonstração.
________________________________________
RNF-DEP-004
A documentação deverá conter instruções completas de instalação.
________________________________________
RNF-DEP-005
A aplicação deverá estar preparada para execução automática em GitHub Codespaces.
________________________________________
Matriz de Validação dos RNFs
Uma melhoria importante em relação aos documentos tradicionais é adicionar uma matriz que relacione cada requisito ao tipo de teste que o validará.
Categoria	Técnica Principal	Ferramenta
Desempenho	Teste de carga	Apache JMeter
Segurança	Testes de segurança introdutórios	Pytest + Requests
Disponibilidade	Testes de recuperação	Docker
Usabilidade	Testes manuais e exploratórios	Navegador + Checklist
Confiabilidade	Testes de integração	Pytest
Escalabilidade	Testes de carga	Apache JMeter
Compatibilidade	Testes cruzados	Navegadores
Manutenibilidade	Análise estática	Ruff, Coverage.py e SonarQube
Observabilidade	Validação de logs	Pytest
Implantação	Testes de ambiente	Docker e GitHub Codespaces

