# Data Lake para Análise de Risco de Crédito

## Introdução
O Data Lake para Análise de Risco de Crédito foi desenvolvido para centralizar e organizar grandes volumes de dados de diferentes fontes, oferecendo uma base robusta e estruturada para análises confiáveis. Esta infraestrutura modular possui camadas que representam diferentes estágios de processamento e maturidade dos dados.

## Objetivos Principais
- Centralizar dados de diferentes fontes.
- Validar e transformar dados para garantir a qualidade.
- Suporte para análise e decisão estratégica.
- Preparação para futuros modelos preditivos e análise avançada.

## Arquitetura e Tecnologias Utilizadas
A arquitetura é construída sobre ferramentas da AWS para garantir escalabilidade, flexibilidade, segurança e desempenho.

### Ferramentas e Funcionalidades
- **AWS S3**: Armazena dados nas camadas Raw, Bronze, Silver e Gold.
- **AWS Lambda**: Orquestra o fluxo de dados e aciona transformações automáticas.
- **AWS Glue**: Realiza transformações e validações nas camadas Silver e Gold.
- **IAM**: Gerencia acessos e permissões.
- **CloudWatch**: Monitora o desempenho das ferramentas e processos.
- **Amazon SES**: Envia relatórios automatizados.
- **Flask e AWS API Gateway**: Recebem arquivos via HTTP e armazenam na camada Raw.
- **PySpark**: Processa grandes volumes de dados.
- **Amazon Athena**: Realiza consultas SQL rápidas na camada Gold.

## Estrutura de Armazenamento
- **Raw**: Dados brutos.
- **Bronze**: Dados validados e categorizados.
- **Silver**: Dados tratatados e alterados para parquet.
- **Gold**: Dados otimizados e enriquecidos para análises e modelos preditivos.

## Fluxo de Dados e Processamento

### Ingestão de Dados
- **Flask e AWS API Gateway**: Recebem arquivos via HTTP POST e os enviam para o S3.

### Camada Bronze
- **Objetivos**: Validar dados recebidos.
- **Fluxo**: AWS Lambda aciona validações e move arquivos para Bronze/Validated ou Bronze/Rejected.

### Camada Silver
- **Objetivos**: Tratar dados.
- **Fluxo**: AWS Lambda aciona limpeza e tratamento e salva em parquet.

### Camada Gold
- **Objetivos**: Consolidar dados para análises e modelos preditivos.
- **Fluxo**: Dados extraídos da camada Silver são enriquecidos, transformados e armazenados em tabelas analíticas.

## Qualidade dos Dados e Governança
- **Garantia de Qualidade**: Validações automatizadas e limpeza de dados.
- **Governança de Dados**: Logs detalhados e regras de acesso controladas.

## Processos Automatizados e Orquestração
- **AWS Lambda**: Automatiza a movimentação de dados.
- **AWS Glue**: Executa transformações complexas.
- **Amazon SES**: Garante a entrega automatizada de relatórios.

## Consultas e Análises
- **Amazon Athena**: Utilizado para consultas SQL diretas na camada Gold.

## Resultados Esperados e Impacto
- **Resultados Esperados**: Dados estruturados e otimizados para análises rápidas.
- **Impacto**: Melhoria da qualidade dos dados e suporte à tomada de decisão estratégica.
