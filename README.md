  O Data Lake para Análise de Risco de Crédito foi projetado para centralizar e organizar grandes volumes de dados de diferentes fontes. Ele oferece uma infraestrutura robusta para análises e modelagem preditiva.
Atualmente, o principal objetivo é receber e processar arquivos CSV contendo informações de clientes de produtos de crédito, com potencial para atender a outras demandas no futuro.
A arquitetura do Data Lake utiliza ferramentas da AWS para garantir escalabilidade e alto desempenho.

Ferramentas e Funcionalidades

AWS S3: Armazena os dados nas camadas Raw, Bronze, Silver e Gold, de forma hierárquica.
AWS Lambda: Orquestra o fluxo de dados e aciona processos automáticos no Glue.
AWS Glue: Realiza transformações e validações de dados nas camadas Silver e Gold.
Amazon SES: Envia relatórios de validação e erros automaticamente.
Flask e AWS API Gateway: Recebem arquivos via HTTP e os armazenam na camada Raw.
PySpark: Processa grandes volumes de dados e aplica transformações complexas.
Amazon Athena: Realiza consultas rápidas na camada Gold.
IAM e CloudWatch: Gerenciam permissões e registram logs de atividades.

Estrutura de Armazenamento

Raw: Dados brutos enviados pela aplicação Flask.
Bronze: Dados categorizados como "Validated" ou "Rejected" após validação.
Silver: Dados transformados e prontos para análises detalhadas.
Gold: Dados otimizados e consolidados para análises avançadas e modelagem.
