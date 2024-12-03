### Documentação do Projeto

#### Descrição do Projeto

Este projeto é uma aplicação web que oferece funcionalidades de registro, login de usuários, e gerenciamento de livros. Ele permite que usuários se registrem, façam login e acessem informações de livros disponíveis em um banco de dados, podendo também adicionar novos livros. O sistema foi desenvolvido utilizando a arquitetura de microsserviços, com uma API RESTful construída em **Node.js** e **Express**, conectada a um banco de dados PostgreSQL para persistência de dados.

#### Tecnologias Usadas

- **Node.js**: Ambiente de execução JavaScript no lado do servidor.
- **Express**: Framework para Node.js, utilizado para construção da API RESTful.
- **PostgreSQL**: Banco de dados relacional utilizado para armazenar informações de usuários e livros.
- **pg**: Biblioteca para conectar e interagir com o PostgreSQL a partir do Node.js.
- **Bcrypt/crypto**: Utilizados para criptografar senhas de usuários.
- **JWT (JSON Web Token)**: Para gerenciamento de autenticação e sessões.
- **SSL**: Configuração para uma conexão segura com o banco de dados.
- **Docker (opcional)**: Para containerização da aplicação.

#### Requisitos Funcionais

1. **Cadastro de Usuário**:
   - O sistema deve permitir que novos usuários se registrem com nome, email e senha.
   - O sistema deve validar se o nome, email e senha estão em um formato correto.
   - O sistema deve garantir que o email seja único.

2. **Login de Usuário**:
   - O sistema deve permitir que usuários já registrados façam login com email e senha.
   - O sistema deve autenticar a senha corretamente utilizando a criptografia.

3. **Gerenciamento de Livros**:
   - O sistema deve permitir que os administradores adicionem livros com título, autor e preço.
   - O sistema deve permitir a visualização de todos os livros cadastrados.
   - O sistema deve validar se o título e o preço do livro estão no formato correto antes de adicionar um novo livro.

4. **Gerenciamento de Sessões**:
   - O sistema deve criar e destruir sessões para os usuários logados.
   - O sistema deve manter a sessão ativa enquanto o usuário estiver autenticado.

#### Requisitos Não Funcionais

1. **Desempenho**:
   - A API deve ser capaz de responder a requisições em menos de 300ms sob carga normal.
   - O sistema deve suportar até 1000 requisições simultâneas de forma eficiente.

2. **Segurança**:
   - As senhas dos usuários devem ser sempre criptografadas antes de serem armazenadas no banco de dados.
   - O sistema deve garantir que os dados de conexão com o banco de dados sejam feitos de forma segura via SSL.
   - As informações sensíveis, como senhas, não devem ser logadas no sistema.

3. **Escalabilidade**:
   - A arquitetura deve ser escalável para suportar maior número de usuários e livros.
   - O sistema deve permitir fácil integração com novos módulos ou serviços.

4. **Disponibilidade**:
   - O sistema deve ser altamente disponível, garantindo 99.9% de tempo de funcionamento.
   - O banco de dados deve ter backups regulares para garantir a continuidade dos dados.

5. **Manutenibilidade**:
   - O código deve ser bem organizado e modular, facilitando manutenções futuras.
   - A documentação do código deve ser clara e completa.

#### Fluxo do Sistema

1. **Registro**: O usuário envia um POST para `/register` com nome, email e senha. O sistema cria um novo usuário no banco de dados.
2. **Login**: O usuário envia um POST para `/login` com email e senha. O sistema valida as credenciais e retorna um token de autenticação.
3. **Visualização de Livros**: O cliente envia um GET para `/livros`, e o sistema retorna uma lista de livros cadastrados.
4. **Adição de Livros**: Um administrador envia um POST para `/livros` com título, autor e preço. O sistema adiciona o livro ao banco de dados.

#### Possíveis Melhorias

- Implementação de um painel de administração para gestão de livros e usuários.
- Integração com serviços de envio de e-mails para confirmação de cadastro e redefinição de senha.
- Suporte a autenticação via JWT para sessões mais seguras.

#### Conclusão

Este projeto oferece uma base sólida para construir um sistema de gerenciamento de usuários e livros com funcionalidades de autenticação e controle de acesso. A modularidade do código permite fácil expansão e manutenção ao longo do tempo.
