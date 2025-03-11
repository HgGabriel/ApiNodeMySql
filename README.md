# API de Usuário com Node.js e MySQL

Este repositório contém um projeto de API REST para gerenciamento de usuários, desenvolvido com Node.js e MySQL. A API permite a criação e listagem de usuários armazenados em um banco de dados.

## Requisitos
Certifique-se de ter instalado em sua máquina:
- [Node.js](https://nodejs.org/)
- [MySQL](https://www.mysql.com/)

## Configuração do Ambiente
1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd seu-repositorio
   ```
2. Instale as dependências:
   ```bash
   npm install
   ```
3. Configure as variáveis de ambiente:
   Crie um arquivo `.env` na raiz do projeto e adicione as seguintes configurações:
   ```env
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=sua_senha
   DB_NAME=usersdb
   PORT=3000
   ```
   Substitua `sua_senha` pela senha do seu MySQL.

## Inicialização do Banco de Dados
O projeto automaticamente criará o banco de dados e a tabela necessária na primeira execução.

## Executando a API
Para iniciar o servidor, execute:
```bash
node index.js
```

O servidor rodará na porta definida no `.env` (padrão: 3000).

## Rotas da API
- **Criar usuário**
  - **POST** `/users`
  - Corpo da requisição (JSON):
    ```json
    {
      "name": "Nome do Usuário",
      "email": "email@example.com"
    }
    ```

- **Listar usuários**
  - **GET** `/users`

## Uso com Docker
Se desejar rodar o MySQL em um contêiner Docker, utilize o seguinte comando:
```bash
docker run -d -p 3306:3306 --name meu-mysql -e MYSQL_ROOT_PASSWORD=sua_senha mysql:latest
```
Para acessar o MySQL dentro do contêiner:
```bash
docker exec -it meu-mysql mysql -u root -p
```

## Testando a API
Você pode testar a API utilizando ferramentas como [Postman](https://www.postman.com/) ou [Insomnia](https://insomnia.rest/).

## Licença
Este projeto é distribuído sob a MIT License. Veja o arquivo `LICENSE` para mais detalhes.

