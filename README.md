# AWS-FOUNDATIONS

Anotações importantes sobre o aprendizado em AWS.  
Este repositório contém resumos e imagens explicativas que complementam as informações sobre os principais serviços da AWS.

---

## Introdução

A AWS possui a infraestrutura de serviços de cloud mais segura e diversa do mercado.  
Com seus data centers espalhados globalmente, consegue disponibilizar em grande escala seus serviços.  
Atualmente, são **105 zonas de disponibilidade em 33 regiões** ao redor do planeta.

As **Regiões (Regions)** são áreas geográficas que contêm várias **Zonas de Disponibilidade (Availability Zones – AZs)**.  
Cada região é composta por **duas ou mais AZs**, que são data centers físicos interconectados, garantindo **alta disponibilidade e resiliência**.

Na AWS, o custo de utilização é baseado no **uso dos recursos**. É possível:
- Criar alertas para monitorar gastos.
- Desligar serviços que não estão em uso, evitando custos desnecessários.

### Ao escolher a região de hospedagem, é importante considerar:
- **Custo**
- **Compliance** (atendimento a requisitos regulatórios)
- **Disponibilidade de serviços** (nem todos estão disponíveis em todas as regiões)

---

## Modelos de Serviço na Nuvem AWS

- **SaaS (Software as a Service)** → utilização de software pronto.  
  _Exemplos:_ E-mail, CRM, ERP

- **PaaS (Platform as a Service)** → utilização de plataforma para desenvolvimento ou execução.  
  _Exemplos:_ Desenvolvimento de aplicações, Streaming, Web Apps

- **IaaS (Infrastructure as a Service)** → utilização de infraestrutura em nuvem.  
  _Exemplos:_ Servidores, Armazenamento, Segurança, Gerenciamento

---

## Principais Serviços da AWS

### **EC2 (Elastic Compute Cloud)**

O **Amazon EC2** oferece máquinas virtuais sob demanda (instâncias) com diferentes sistemas operacionais.  
É um serviço do tipo **IaaS**.

**Principais características:**
- Total controle sobre o ambiente (CPU, memória, rede, SO)
- Escalabilidade horizontal e vertical
- Pagamento por uso
- Integração com outros serviços AWS

---

### **S3 (Simple Storage Service)**

O **Amazon S3** é um serviço de armazenamento de objetos em nuvem.

**Principais características:**
- Armazenamento escalável, seguro e durável
- Várias classes de armazenamento (Standard, Infrequent Access, Glacier, etc.)
- Controle de versões, criptografia e políticas de ciclo de vida
- Acesso via interface web, CLI ou SDKs

---

### **EBS (Elastic Block Store)**

O **Amazon EBS** fornece volumes de armazenamento em blocos para instâncias EC2.

**Usos comuns:**
- Bancos de dados relacionais (MySQL, PostgreSQL, Oracle)
- Aplicativos que exigem alta performance de I/O
- Armazenamento persistente para sistemas operacionais

---

### **Amazon RDS (Relational Database Service)**

O **Amazon RDS** é um serviço gerenciado de banco de dados relacional.

**Principais recursos:**
- Suporte a vários mecanismos: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server e Aurora
- Backup automático e replicação entre AZs
- Escalabilidade vertical (instância) e horizontal (read replicas)
- Reduz a sobrecarga de administração de bancos de dados

---

### **AWS Lambda**

O **AWS Lambda** permite executar código sem necessidade de provisionar ou gerenciar servidores — um serviço **Serverless**.

**Características:**
- Execução sob demanda (paga apenas pelo tempo de execução)
- Suporte a várias linguagens (Python, Node.js, Java, Go, etc.)
- Escala automaticamente de acordo com o número de solicitações
- Ideal para automações, APIs e processamento de eventos

**Exemplo de uso:**  
Funções que são acionadas automaticamente quando um arquivo é enviado para o S3.

### **Elastic Load Balancer (ELB)**

O **Elastic Load Balancer** distribui automaticamente o tráfego de entrada entre várias instâncias EC2 ou containers.

**Tipos de ELB:**
1. **Application Load Balancer (ALB)** – Camada 7 (HTTP/HTTPS)
2. **Network Load Balancer (NLB)** – Camada 4 (TCP/UDP)
3. **Gateway Load Balancer (GLB)** – Gerencia tráfego de rede de appliances virtuais

**Benefícios:**
- Alta disponibilidade
- Escalabilidade automática
- Integração com Auto Scaling
- Balanceamento de carga inteligente

---

### **Amazon Glacier**

O **Amazon S3 Glacier** é uma classe de armazenamento voltada para **arquivamento de longo prazo e baixo custo**.

**Características:**
- Custos muito baixos por GB armazenado
- Tempo de recuperação maior (minutos a horas)
- Ideal para backups, logs antigos e dados raramente acessados

---

### **Amazon CloudFront**

O **CloudFront** é o **CDN (Content Delivery Network)** da AWS.

**Função:** Distribuir conteúdo (imagens, vídeos, arquivos, sites) globalmente com **baixa latência e alta velocidade**.

**Como funciona:**
- Utiliza uma rede de **edge locations** (pontos de presença)
- Cacheia conteúdo para reduzir o tempo de resposta
- Integra-se ao S3, EC2, API Gateway e outros serviços

---

### **Amazon SNS (Simple Notification Service)**

O **SNS** é um serviço de **mensageria e notificação**.

**Principais usos:**
- Envio de notificações (e-mail, SMS, push)
- Comunicação entre microserviços
- Acionamento de funções Lambda
- Publicar mensagens em “tópicos” e entregá-las a múltiplos assinantes

---

### **Amazon SQS (Simple Queue Service)**

O **SQS** é um serviço de **filas de mensagens** totalmente gerenciado.

**Características:**
- Garante a entrega de mensagens entre sistemas distribuídos
- Evita perda de dados em caso de falhas
- Suporta processamento assíncrono
- Tipos:
  - **Standard Queue** – alta taxa de transferência
  - **FIFO Queue** – garante ordem de processamento

**Exemplo de uso:**  
Um sistema web envia requisições para uma fila SQS, que são processadas por instâncias EC2 ou funções Lambda de forma assíncrona.
### **Amazon ECS (Elastic Container Service)**

O **ECS** é um serviço gerenciado de **orquestração de contêineres** da AWS.

**Características:**
- Permite executar e gerenciar aplicações em contêineres Docker
- Suporte a dois modos de execução:
  - **EC2 Launch Type:** os contêineres rodam em instâncias EC2
  - **Fargate Launch Type:** execução **serverless** sem gerenciar servidores
- Integração com **ELB**, **CloudWatch** e **IAM**

**Benefícios:**
- Totalmente integrado ao ecossistema AWS
- Alta escalabilidade e performance
- Ideal para microsserviços e workloads baseadas em containers

**Exemplo prático:**  
Aplicações web compostas por múltiplos contêineres (front-end, back-end e banco de dados) podem ser gerenciadas facilmente com ECS.

---

### **Amazon EKS (Elastic Kubernetes Service)**

O **EKS** é o serviço gerenciado de **Kubernetes** da AWS.

**Características:**
- Facilita a implantação, gerenciamento e escalabilidade de clusters Kubernetes
- Suporte nativo a workloads híbridos e multi-cloud
- Compatível com ferramentas e plug-ins padrão do Kubernetes
- Pode rodar workloads tanto em **EC2** quanto em **Fargate**

**Benefícios:**
- Gerenciamento automatizado do plano de controle do Kubernetes
- Alta disponibilidade e segurança
- Integração com IAM, VPC e CloudWatch

**Exemplo prático:**  
Empresas que já usam Kubernetes on-premises podem migrar seus clusters para a AWS utilizando EKS, reduzindo a carga operacional.

---










