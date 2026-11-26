
# GeoPoint API

## Sobre o projeto

O GeoPoint é uma API REST desenvolvida em Java, utilizando o framework Spring Boot, que permite cadastrar, consultar, editar e excluir pontos geográficos.
Cada ponto geográfico possui um identificador único, nome, descrição, latitude e longitude. As informações são armazenadas em um banco de dados PostgreSQL.
O projeto tem como objetivo aplicar conceitos de programação, desenvolvimento de APIs REST, integração com banco de dados, organização de código em camadas e operações CRUD (Create, Read, Update e Delete).

## Funcionalidades
- Cadastro de pontos geográficos;
- Listagem dos pontos cadastrados;
- Consulta de um ponto pelo seu identificador;
- Edição de pontos geográficos;
- Exclusão de pontos geográficos;
- Validação dos dados informados;
- Geração automática de identificadores únicos (UUID);
- Armazenamento das informações em banco de dados;
- Tratamento de erros nas requisições.

## Tecnologias utilizadas
- Java
- Spring Boot
- Spring Web
- JDBC / JdbcTemplate
- PostgreSQL
- Maven
- Docker
- Git e GitHub

## Estrutura do projeto
O projeto está organizado em camadas, separando as responsabilidades de cada parte da aplicação.

| Camada | Responsabilidade |
|---|---|
| Controllers | Recebe as requisições HTTP e retorna as respostas da API. |
| Services | Contém as regras de negócio e as validações dos dados. |
| Repositories | Realiza as operações SQL no banco de dados. |
| Entities | Representa os objetos e seus atributos. |
| DTOs | Define a estrutura dos dados recebidos pela API. |
| Configs | Configura as dependências da aplicação. |

Essa organização facilita a manutenção, a compreensão e a evolução do código.

## Modelo de dados
Cada ponto geográfico possui os seguintes atributos:

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID | Identificador único do ponto. |
| name | String | Nome do ponto geográfico. |
| description | String | Descrição do local. |
| latitude | BigDecimal | Latitude do ponto. |
| longitude | BigDecimal | Longitude do ponto. |

## Endpoints da API
A API disponibiliza os seguintes endpoints para realizar as operações CRUD:

| Método HTTP | Endpoint | Funcionalidade |
|---|---|---|
| POST | /api/points | Cadastrar um novo ponto. |
| GET | /api/points | Listar todos os pontos. |
| GET | /api/points/{id} | Consultar um ponto específico. |
| PUT | /api/points/{id} | Atualizar um ponto. |
| DELETE | /api/points/{id} | Excluir um ponto. |

## Exemplo de requisição
Para cadastrar um novo ponto geográfico, deve ser realizada uma requisição POST para o endpoint `/api/points`, enviando os dados no formato JSON.

```json
{
  "name": "Universidade Atitus",
  "description": "Instituição de ensino superior",
  "latitude": -28.26,
  "longitude": -52.40
}
```

As coordenadas acima são ilustrativas.
O identificador é gerado automaticamente pela aplicação no momento do cadastro.

## Regras de validação
Para garantir a consistência dos dados, a aplicação realiza as seguintes validações:

- O nome do ponto é obrigatório;
- A descrição é opcional;
- A latitude deve estar entre -90 e 90;
- A longitude deve estar entre -180 e 180;
- O identificador é gerado automaticamente;
- O ponto deve existir para ser consultado, editado ou excluído;
- Na edição, não é permitido utilizar o nome de outro ponto já cadastrado.

## Códigos de retorno HTTP

| Código | Descrição |
|---|---|
| 200 | Requisição realizada com sucesso. |
| 201 | Ponto cadastrado com sucesso. |
| 204 | Ponto excluído com sucesso. |
| 400 | Erro na requisição ou nos dados informados. |
| 404 | Ponto geográfico não encontrado. |
| 500 | Erro interno do servidor. |

## Testes da API
As requisições foram testadas utilizando a ferramenta Postman. Por meio dela, foi possível verificar o funcionamento das operações de cadastro, listagem, consulta, edição e exclusão dos pontos geográficos.




## Contexto acadêmico
Este projeto foi desenvolvido na disciplina de ORGANIZAÇÃO E ABSTRAÇÃO NA PROGRAMAÇÃO, do curso de Ciência da Computação da Universidade Atitus.

## Grupo
Allana Prestes
1139889
1139889@atitus.edu.br

Caroline Russo Zilio
1140047
caroline.zilio@atitus.edu.br

Eloise Pagnussat
1139521
1139521@atitus.edu.br

Kélen Camargo dos Santos
1102339 
kelen.santos@atitus.edu.br

Luísa Lima Migliorini 
1139749
1139749@atitus.edu.br

Vitória Drechsler Colega
1139410
1139410@atitus.edu.br
