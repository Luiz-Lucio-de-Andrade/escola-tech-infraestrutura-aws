# 🏫 Escola Tech - Arquitetura AWS (Infraestrutura como Código)

Este repositório contém a infraestrutura em nuvem automatizada para o sistema de matrículas da Escola Tech, projetada para suportar alta disponibilidade e picos de tráfego com custos otimizados.

## 🏗️ Arquitetura (3 Camadas)
* **Camada de Acesso:** Elastic Load Balancing (ALB)
* **Camada de Processamento:** Amazon EC2 gerido por Auto Scaling (Instâncias Spot)
* **Camada de Dados:** Amazon RDS (MySQL) com replicação Multi-AZ

## ⚙️ Pré-requisitos
* Uma conta ativa na AWS.
* Permissões administrativas para criar recursos no AWS CloudFormation.
* Acesso à Consola da AWS.

## 🚀 Como Replicar o Projeto em Produção
A nossa infraestrutura está 100% automatizada utilizando o formato YAML nativo do AWS CloudFormation. Para recriar o ambiente:

1. Aceda ao painel do **AWS CloudFormation** na sua conta AWS.
2. Clique em **Create stack** (With new resources).
3. Selecione **Upload a template file** e envie o ficheiro `escola-tech-infra.yaml` deste repositório.
4. Clique em **Next**, defina um nome para a Stack (ex: `escola-tech-prod`).
5. Configure as variáveis de ambiente necessárias (como a password da base de dados). **Nunca exponha credenciais reais em texto aberto**.
6. Reveja os detalhes e clique em **Submit**. A AWS criará todos os recursos automaticamente em cerca de 5 a 10 minutos.

## 🔐 Segurança e Variáveis de Ambiente
As credenciais da base de dados (utilizador e password) são injetadas de forma dinâmica no momento da execução do CloudFormation. Nenhuma chave de acesso ou password hardcoded foi incluída neste código.
