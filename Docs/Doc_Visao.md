Documento de Visão do Produto

Projeto: EasyShop Web Platform

Versão: 1.0

Status: Em Planejamento

Data: Agosto/2026


#1. Visão Geral
1.1 Propósito do Documento

Este documento apresenta a visão geral da EasyShop Web Platform, uma plataforma completa de comércio eletrônico desenvolvida para servir como base prática da disciplina Software Testing & Quality Assurance.

O documento define os objetivos do produto, seu escopo, os principais usuários, funcionalidades, restrições e características arquiteturais. Sua finalidade é alinhar o entendimento entre todos os envolvidos no projeto e estabelecer a referência para as fases de especificação, implementação e testes.

Embora o sistema seja desenvolvido para fins educacionais, sua arquitetura, organização e funcionalidades seguirão padrões utilizados em projetos reais de desenvolvimento de software, permitindo que os estudantes trabalhem em um ambiente próximo ao encontrado na indústria.


#2. Visão do Produto
2.1 Descrição

A EasyShop Web Platform é uma aplicação web de comércio eletrônico que permite a comercialização de produtos por meio de uma interface intuitiva, integrada a um backend baseado em APIs REST.

O sistema contempla funcionalidades voltadas tanto aos clientes quanto aos administradores da plataforma, incluindo autenticação, gerenciamento de catálogo, carrinho de compras, processamento de pedidos, acompanhamento de entregas e administração de produtos.

Além das funcionalidades de negócio, a plataforma foi concebida para servir como ambiente de experimentação de práticas de Garantia da Qualidade (QA), possibilitando a execução de testes funcionais, automatizados, de desempenho, integração, regressão e qualidade contínua.


#3. Problema que o Produto Resolve

Em projetos reais de software, equipes de QA frequentemente enfrentam dificuldades para aprender e praticar testes em aplicações completas. Grande parte dos cursos utiliza exemplos simplificados ou pequenos trechos de código que não representam a complexidade de um ambiente corporativo.

A EasyShop busca eliminar essa limitação ao oferecer um sistema integrado, contendo múltiplos módulos de negócio, banco de dados relacional, APIs REST e interface web, permitindo que diferentes estratégias de testes sejam aplicadas em um mesmo contexto durante toda a disciplina.


#4. Objetivos do Produto

O sistema possui os seguintes objetivos principais:

disponibilizar uma plataforma web funcional de comércio eletrônico;
servir como ambiente permanente para atividades práticas de QA;
permitir a aplicação de diferentes técnicas de testes de software;
possibilitar a automação de testes utilizando ferramentas amplamente empregadas pelo mercado;
reproduzir cenários encontrados em projetos profissionais de desenvolvimento.


#5. Público-Alvo

A plataforma contempla diferentes perfis de usuários.

Cliente

Usuário responsável pela navegação na loja virtual, pesquisa de produtos, realização de compras e acompanhamento de pedidos.

Administrador

Responsável pelo gerenciamento do catálogo de produtos, categorias, estoque e acompanhamento dos pedidos realizados.

Analista de Qualidade (QA)

Responsável pela elaboração e execução de testes manuais e automatizados, registro de defeitos, validação de requisitos e monitoramento da qualidade do sistema.

Este será o perfil utilizado pelos estudantes durante toda a disciplina.


#6. Escopo do Produto

A primeira versão do sistema contemplará os seguintes módulos.

Módulo de Autenticação
Cadastro de usuários
Login
Logout
Recuperação de senha
Alteração de senha
Perfil do usuário
Módulo de Catálogo
Listagem de produtos
Pesquisa
Filtros
Categorias
Ordenação
Paginação
Módulo de Produtos
Detalhes do produto
Imagens
Estoque
Avaliações
Produtos relacionados
Módulo de Carrinho
Inclusão de produtos
Alteração de quantidade
Remoção de itens
Aplicação de cupons
Cálculo automático dos valores
Módulo de Checkout
Endereços
Frete
Forma de pagamento
Confirmação da compra
Módulo de Pedidos
Histórico
Consulta
Cancelamento
Status
Detalhamento
Módulo Administrativo
Cadastro de produtos
Cadastro de categorias
Controle de estoque
Atualização de preços
Gerenciamento de pedidos


#7. Objetivos Educacionais

Além dos objetivos de negócio, a plataforma foi planejada para permitir o ensino das seguintes competências:

elaboração de planos de teste;
construção de casos de teste;
rastreabilidade entre requisitos e testes;
testes exploratórios;
testes funcionais;
testes de API;
testes automatizados;
testes de integração;
testes end-to-end;
testes de desempenho;
testes de regressão;
integração dos testes em pipelines CI/CD;
geração de relatórios de cobertura e qualidade.


#8. Funcionalidades Estratégicas para QA

Diferentemente de um e-commerce convencional, a EasyShop foi projetada para facilitar o aprendizado de Engenharia de Qualidade.

Entre suas características estão:

APIs REST documentadas;
autenticação baseada em tokens;
banco de dados relacional;
regras de negócio variadas;
validações de formulários;
diferentes perfis de usuários;
geração de logs;
tratamento de exceções;
respostas HTTP padronizadas;
estrutura preparada para automação de testes.


#9. Arquitetura Geral

A solução será baseada em arquitetura multicamadas.

<img width="389" height="511" alt="image" src="https://github.com/user-attachments/assets/8a217f93-cf68-4372-90eb-c7ae050ccb22" />



Toda a aplicação será executada em containers Docker, permitindo implantação padronizada em GitHub Codespaces e ambientes locais.


#10. Tecnologias Previstas
Camada	Tecnologia
Linguagem	Python 3
Backend	FastAPI
ORM	SQLAlchemy
Banco de Dados	PostgreSQL
Migrações	Alembic
Frontend	HTML + CSS + Bootstrap + Jinja2
Ambiente	GitHub Codespaces
Containers	Docker e Docker Compose
Testes Unitários	Pytest
Testes Web	Selenium
Testes de API	Postman e Pytest
Testes de Performance	Apache JMeter
CI/CD	GitHub Actions
Qualidade	Coverage.py e SonarQube


#11. Princípios Arquiteturais

O desenvolvimento seguirá alguns princípios fundamentais:

separação entre apresentação, regras de negócio e persistência;
organização modular por domínio;
APIs REST padronizadas;
baixo acoplamento entre componentes;
alta coesão entre módulos;
código preparado para testes automatizados;
documentação contínua da API;
facilidade de implantação em ambientes conteinerizados.


#12. Restrições do Projeto

Para garantir uniformidade durante toda a disciplina, serão adotadas as seguintes restrições:

toda a implementação será realizada em Python;
o banco de dados será exclusivamente PostgreSQL;
o ambiente oficial de desenvolvimento será o GitHub Codespaces;
todas as funcionalidades deverão possuir APIs REST correspondentes;
o sistema deverá permanecer suficientemente simples para fins didáticos, sem comprometer boas práticas de arquitetura.


#13. Critérios de Sucesso

Ao término do desenvolvimento, a plataforma deverá:

oferecer uma experiência completa de comércio eletrônico;
permitir a execução de testes manuais e automatizados em todos os módulos;
fornecer cobertura para testes funcionais e não funcionais;
possibilitar integração com pipelines de CI/CD;
servir como base única para todos os laboratórios da disciplina;
produzir artefatos profissionais de QA, como planos de teste, casos de teste, scripts automatizados, relatórios de defeitos e indicadores de qualidade.
