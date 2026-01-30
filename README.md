# Netflix Data Transformation: Estratégias de Big Data com PySpark

Sobre o Projeto

Este projeto analisa o ecossistema de conteúdo da Netflix, uma gigante do streaming com mais de 200 milhões de assinantes e um catálogo superior a 8.000 títulos. O objetivo central foi transformar dados brutos em uma estrutura relacional para análises detalhadas de elenco e métricas de diretores.

Desafios Técnicos e Soluções de Engenharia

# Normalização de Dados Complexos (Desafio 2)
**Cenário:** O catálogo apresentava atores agrupados em strings únicas na coluna `cast`.
**Solução:** * Implementei uma lógica de **Explosão de Dados** utilizando as funções `split` e `explode`.
* Isso permitiu desestruturar a coluna para identificar individualmente os 51 profissionais vinculados ao diretor **Adam Shankman**.
* Apliquei `trim` e `distinct` para garantir a integridade e limpeza dos nomes.

# Engenharia de Atributos com UDF (Desafio 3)
**Cenário:** Necessidade de criar métricas personalizadas (contagem de vogais) sobre os nomes dos diretores, exigindo alta resiliência a dados nulos.
**Solução:**
* Desenvolvi e registrei uma **UDF (User Defined Function)** em Python para processamento de texto customizado.
* Inseri uma camada de tratamento de exceções para converter valores `NULL` em `0`, prevenindo interrupções no pipeline de dados.
 
# Ferramentas
* **Cloud & Big Data:** Databricks Community Edition.
* **Engine:** PySpark (Spark Core e SQL).
* **Linguagem:** Python para lógica de negócios personalizada.
