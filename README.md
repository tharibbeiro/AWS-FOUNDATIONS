# AWS-FOUNDATIONS
Anotações importantes sobre o aprendizado em AWS, nesse repositório possui imagens em anexo que completam as informações. 

---

A **AWS** possui a infraestrutura de serviços de cloud mais segura e diversa do mercado. Com seus data centers espalhados globalmente, consegue disponibilizar em grande escala seus serviços.  
Atualmente, são **105 zonas de disponibilidade em 33 regiões** no planeta.  

As **regiões (Regions)** são áreas geográficas que contêm várias **zonas de disponibilidade (Availability Zones – AZs)**.  
- Cada região é composta por 2 ou mais zonas de disponibilidade.  
- As zonas de disponibilidade são data centers físicos, conectados logicamente, garantindo **alta disponibilidade e resiliência**.  

Na AWS, o **custo de utilização é conforme o uso dos recursos**. É possível:  
- Criar **alertas** para monitorar gastos na plataforma.  
- **Desligar serviços** que não estão em uso, evitando custos desnecessários.  

Ao escolher a região de hospedagem, é importante considerar:  
- **Custo**  
- **Compliance** (se a região atende aos requisitos regulatórios da empresa/país)  
- **Disponibilidade de serviços** (nem todos os serviços estão em todas as regiões)  

---

## Modelos de Serviço na Nuvem AWS
- **SaaS (Software as a Service)** → utilização de software pronto.  
  *Exemplos: E-mail, CRM, ERP*  

- **PaaS (Platform as a Service)** → utilização de plataforma para desenvolvimento ou execução.  
  *Exemplos: Desenvolvimento de aplicações, Streaming, Web Apps*  

- **IaaS (Infrastructure as a Service)** → utilização de infraestrutura em nuvem.  
  *Exemplos: Sistemas legados, Servidores de arquivos, Segurança, Gerenciamento, Cache*  

---

## EC2 (Elastic Compute Cloud)
O **EC2** são as máquinas virtuais da AWS.  
- Oferece instâncias com diferentes sistemas operacionais.  
- É um serviço do tipo **IaaS**.  
- A escolha da instância deve ser feita com cuidado para balancear **necessidades técnicas x custo**.  

---

## S3 (Simple Storage Service)
O **Amazon S3** é o serviço de **armazenamento de objetos em nuvem** da AWS.  
- Ideal para armazenar, organizar e recuperar grandes volumes de dados de forma **segura** e **escalável**.  
- Possui diferentes **classes de storage** que permitem economia de custos.  
- É possível criar **regras de ciclo de vida (Lifecycle Policies)** para mover dados automaticamente entre classes de acordo com a frequência de acesso.  

---

## EBS (Elastic Block Store)
O **Amazon EBS** é um serviço de **armazenamento em blocos** que pode ser anexado a instâncias EC2.  
- Cada instância EC2 tem um volume de armazenamento, mas com o EBS é possível expandir rapidamente essa capacidade.  
- Exemplos de uso:  
  - Armazenamento para **bancos de dados** (MySQL, PostgreSQL, Oracle)  
  - Armazenamento de dados para **aplicativos web**  
  - **Logs de sistema**  











