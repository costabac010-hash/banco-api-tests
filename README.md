# Banco API Tests

Projeto de testes de integração e contrato automatizados para as APIs do **Banco API**, desenvolvidos utilizando **Mocha**, **Chai**, **SuperTest** e **Mochawesome**.

---

## Pré-requisitos

Antes de iniciar, certifique-se de ter instalado em sua máquina:
* [Node.js](https://nodejs.org/) (Versão 16 ou superior)
* [npm](https://www.npmjs.com/) (Gerenciador de pacotes do Node)
* A aplicação da API rodando localmente (por padrão na porta `3000`)

---

## Tecnologias Utilizadas

* **[Mocha](https://mochajs.org/)**: Framework de testes em JavaScript.
* **[Chai](https://www.chaijs.com/)**: Biblioteca de asserções (`expect`).
* **[SuperTest](https://github.com/ladjs/supertest)**: Biblioteca para testes de requisições HTTP.
* **[Dotenv](https://www.npmjs.com/package/dotenv)**: Gerenciamento de variáveis de ambiente.
* **[Mochawesome](https://www.npmjs.com/package/mochawesome)**: Gerador de relatórios executivos em HTML/JSON.

---

## Arquivos Não Versionados (.gitignore) 

Por razões de segurança e boas práticas de desenvolvimento, os seguintes arquivos/pastas não são enviados ao GitHub:

* **.env:** Armazena variáveis locais como a BASE_URL.Evita expor URLs internas ou credenciais de ambientes no repositório remoto.

* **.node_modules/:** Pasta gerada pelo npm install com as dependências.Arquivos pesados que podem ser instalados a qualquer momento pelo package.json.

* **mochawesome-report/:** Pasta com relatórios HTML/JSON gerados pós-execução.Artefato dinâmico gerado localmente após cada rodada de testes.

## Configuração do Ambiente: 
 
 * **Clone o repositório:** git clone [https://github.com/costabac010-hash/banco-api-tests.git](https://github.com/costabac010-hash/banco-api-tests.git)

Configure as variáveis de ambiente: Crie um arquivo .env na raiz do projeto contendo a URL base da API.

**BASE_URL=http://localhost:3000**

---

## Cobertura dos Testes

* **Documentação da API via Swagger:** http://localhost:3000/api-docs/#/Transferencias

* **Rota /login**

POST /login: Valida autenticação com credenciais válidas e retorno do token em formato string.

* **Rota /transferencias**

POST /transferencias:

201: Sucesso ao realizar transferência igual ou acima de R$ 10,00.

422: Falha ao tentar transferir valores abaixo de R$ 10,00.

GET /transferencias/{id}:

200: Sucesso ao buscar transferência por ID válido, validando estrutura dos dados, tipos de variáveis e valores de retorno.

GET /transferencias:

200: Validação de paginação e limitação de registros retornados na consulta.

* **Para rodar toda a suíte de testes e gerar o relatório do Mochawesome: npm test**

---

## Relatório de Execução:

 Após rodar o comando, acesse a pasta mochawesome-report/ e abra o arquivo mochawesome.html no seu navegador para visualizar o resultado dos testes.