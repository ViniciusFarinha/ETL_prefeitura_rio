# CET_RIO_report
Reporte de ações de mitigação de ocorrências da CET-RIO na cidade - Vinícius Farinha

## Visão Geral

Projeto de processo seletivo com intuito de buscar dados sobre ocorrências abertas das CET-RIO a partir de API's e desenvolver um report destas ocorrências.
Cada na função deve gerar uma tabela csv dos dados e deve funcionar de 20 em 20 minutos.

## Pipeline

O projeto consiste em uma pipeline de dados que realiza a obtenção de informações de ocorrências abertas no Rio de Janeiro, filtragem de dados de acordo com critérios específicos e geração de um dataframe final atualizado.

A pipeline é composta pelas seguintes etapas:

1. **Obter dados de ocorrências abertas**: Realiza uma requisição a uma API para obter informações sobre as ocorrências abertas no Rio de Janeiro. Os dados são transformados em um dataframe.

2. **Obtenção de todos os Pop's**: Realiza uma requisição a uma API para obter informações sobre os Pop's (Procedimentos Operacionais Padrão) disponíveis. Os dados são armazenados em uma lista de identificadores.

3. **Utilizar Pop's para filtrar CET-RIO nas ocorrências abertas**: Utiliza a lista de identificadores de Pop's para filtrar as ocorrências abertas e manter apenas aquelas relacionadas ao órgão "CET-RIO".

4. **Dataframe final**: Realiza um merge dos dados das ocorrências abertas filtradas com os dados dos Pop's. Realiza ajustes no dataframe, como remoção de colunas desnecessárias e adição de informações adicionais.

5. **Criação do Loop**: Executa um loop contínuo que realiza a atualização periódica do dataframe final a cada 20 minutos. O loop é limitado a um tempo máximo de 1 hora.

6. **Entrega**: Exporta o dataframe final atualizado para um destino específico, como um arquivo ou um banco de dados.


                                  ┌─────────────────┐
                                  │ Obter Dados de  │
                                  │ Ocorrências     │
                                  │ Abertas         │
                                  └─────────────────┘
                                           │
                                           ▼
                                  ┌─────────────────┐
                                  │ Obtenção de     │
                                  │ todos os Pop's  │
                                  └─────────────────┘
                                           │
                                           ▼
                                  ┌─────────────────┐
                                  │ Utilizar Pop's  │
                                  │ para filtrar    │
                                  │ CET-RIO nas     │
                                  │ ocorrências     │
                                  │ abertas         │
                                  └─────────────────┘
                                           │
                                           ▼
                                  ┌─────────────────┐
                                  │ Dataframe Final │
                                  └─────────────────┘
                                           │
                                           ▼
                                  ┌─────────────────┐
                                  │   Criação do    │
                                  │      Loop       │
                                  └─────────────────┘
                                           │
                                           ▼
                                  ┌─────────────────┐
                                  │     Entrega     │
                                  └─────────────────┘

   

## Pré-requisitos

Antes de executar o projeto, certifique-se de ter as seguintes dependências instaladas:

- Python 
- Pandas
- time
- datetime
- json
- Requests 

## Configuração

Clone este repositório em sua máquina local:
   
git clone https://github.com/seu-usuario/seu-repositorio.git

## Autores

- Vinícius Farinha (@ViniciusFarinha) - [vinifarinha11rj55@gmail.com](mailto:vinifarinha11rj55@gmail.com)

## Recursos Adicionais

Link para o site das APIs: https://api.dados.rio/docs/
