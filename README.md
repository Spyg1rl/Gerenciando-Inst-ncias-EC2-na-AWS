# Gerenciando-Inst-ncias-EC2-na-AWS# Arquitetura AWS – Desafio Bootcamp Code Girls 2025 🚀

Este repositório apresenta um **diagrama de arquitetura AWS** desenvolvido como parte do **desafio prático do Bootcamp Code Girls 2025 – Santander em parceria com a DIO (Digital Innovation One)**.  

O objetivo do desafio foi **projetar e documentar uma solução simples de nuvem utilizando instâncias EC2**, além de integrar outros serviços fundamentais da AWS para compor um fluxo de sistema coerente e didático.  

---

## 🎯 Objetivo do Desafio
- Compreender o funcionamento de uma **instância EC2** e seu papel como núcleo de processamento.  
- Relacionar EC2 com serviços complementares da AWS:  
  - **EBS (Elastic Block Store)** – disco persistente da instância.  
  - **S3 (Simple Storage Service)** – repositório de arquivos.  
  - **Lambda** – processamento serverless e eventos.  
  - **RDS (Relational Database Service)** – banco de dados relacional.  
  - **CloudWatch** – monitoramento e métricas.  
- Documentar o fluxo em um diagrama no **draw.io (diagrams.net)**.  

---

## 🖼️ Arquitetura Proposta

### Fluxo principal
1. **Usuário** acessa a aplicação via navegador ou app.  
2. O acesso é direcionado por um **Load Balancer** para a **instância EC2**.  
3. A **EC2**:  
   - Utiliza **EBS** como disco local persistente.  
   - Lê e grava **dados estruturados** no **RDS**.  
   - Lê e envia **arquivos** para o **S3**.  
4. O **S3** dispara **funções Lambda** quando recebe arquivos novos.  
5. O **Lambda** processa arquivos e pode:  
   - Salvar resultados no **S3**.  
   - Atualizar registros no **RDS**.  
6. Todo o ambiente é monitorado pelo **CloudWatch**, que coleta métricas e logs da EC2, Lambda e RDS.  

---

## 🔑 Papéis dos Serviços AWS

| Serviço | Função no sistema |
|---------|-------------------|
| **EC2 (Elastic Compute Cloud)** | Executa a aplicação principal (servidor web/app). |
| **EBS (Elastic Block Store)** | Disco virtual anexado à EC2, garantindo armazenamento persistente local. |
| **S3 (Simple Storage Service)** | Armazena arquivos (uploads, relatórios, backups) e dispara eventos para Lambda. |
| **Lambda** | Executa código sob demanda (serverless), processando arquivos ou dados de forma assíncrona. |
| **RDS (Relational Database Service)** | Banco de dados relacional para dados estruturados da aplicação. |
| **CloudWatch** | Monitora métricas e gera logs do ambiente (EC2, Lambda, RDS). |
| **Elastic Load Balancer (ELB)** | Distribui requisições de usuários entre instâncias EC2. |

---

## 🔗 Fluxo de Comunicação

- **Usuário → Load Balancer:** Requisições HTTP/HTTPS.  
- **Load Balancer → EC2:** Distribuição de tráfego.  
- **EC2 ↔ EBS:** Armazenamento persistente local.  
- **EC2 ↔ RDS:** Leitura e escrita de dados estruturados.  
- **EC2 ↔ S3:** Upload e download de arquivos.  
- **S3 → Lambda:** Evento de upload dispara função.  
- **Lambda → S3:** Armazena resultados processados.  
- **Lambda → RDS:** Atualiza dados processados.  
- **EC2, Lambda e RDS → CloudWatch:** Envio de métricas e logs.  

---

## 📌 Conclusão
Este desafio foi uma oportunidade de consolidar conhecimentos em **serviços fundamentais da AWS**, entendendo como eles se conectam em um fluxo real de aplicação.  

O diagrama ilustra como construir um **ambiente simples, escalável e monitorado** na nuvem, utilizando os principais recursos da AWS.  

---

## ✨ Créditos
- **Bootcamp Santander Code Girls 2025 – DIO**  
- **Desafio: Gerindo instâncias EC2 e serviços complementares da AWS**  
- Desenvolvido por: Adriana Almeida
