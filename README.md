# 🚀 SEND_MESSAGE_DISCORD

## SAP BTP Integration Suite (CPI) – Integração com Discord via Webhook

<br> 

🎯 Objetivo

Este iFlow tem como objetivo demonstrar uma integração simples, eficiente e reutilizável utilizando o SAP BTP CPI, permitindo o envio de mensagens automáticas para canais do Discord via Webhook.

A solução pode ser utilizada como base para:

- Monitoramento de integrações
- Notificações de erro/sucesso
- Alertas operacionais em tempo real
- Integração com sistemas externos

<br>

🧩 Visão Geral da Solução

A integração expõe um endpoint HTTP que recebe requisições externas e processa uma mensagem que será enviada diretamente para um canal do Discord.

Essa abordagem desacopla sistemas SAP de ferramentas de comunicação modernas, permitindo maior visibilidade operacional.

![Fluxo](imagens/capa-linkedin.png)

---

<br>

# 🏗️ 🔧 Arquitetura do iFlow

<br><br>

# 🔄 1. Fluxo da Integração

<br>

### 🧱 Criando o Package
![Fluxo](imagens/Screenshot_1.png)

<br><br>

### 🏷️ Nome do Package
```
ZPKG_SEND_MESSAGE_DISCORD
```
![Fluxo](imagens/Screenshot_2.png)

<br>

### ➕ Adicionando o Artefato
![Fluxo](imagens/Screenshot_3.png)

<br>

### 🏷️ Nome do iFlow
```
IF_SEND_MESSAGE_DISCORD
```
![Fluxo](imagens/Screenshot_4.png)

<br>

### ➕ Adicionando o Adapter
![Fluxo](imagens/Screenshot_5.png)


# 🔹 2. HTTPS Sender (Trigger)
```
Endpoint: /discord
```
![Fluxo](imagens/Screenshot_6.png)

# 🔹 3. Content Modifier

### ➕ Adicionando o Content Modifier
![Fluxo](imagens/Screenshot_7.png)

<br>

### 🏷️ Renomeando o Content Modifier
```
Nome: sendBody
```
![Fluxo](imagens/Screenshot_8.png)


<br>

### ⚙️ Configuração do Content Modifier
Message Header
```
| Campo        | Valor            |
| ------------ | ---------------- |
| Name          | Source Value    |
| Content Type  | application/json|

```
![Fluxo](imagens/Screenshot_9.png)

<br>

### ⚙️ Configuração do Content Modifier
Body
```
{
  "content": "\uD83D\uDE80 Mensagem enviada pelo SAP CPI com sucesso!"
}
```
![Fluxo](imagens/Screenshot_10.png)


# 🔹 4. Request Reply (Chamada API)

### ➕ Adicionando Request Reply
![Fluxo](imagens/Screenshot_11.png)

<br>

### 🏷️ Renomeando o Request Reply
```
Nome: API_jsonplaceholder
```
![Fluxo](imagens/Screenshot_11.png)

<br>

### ➕ Adicionando o Adapter
![Fluxo](imagens/Screenshot_12.png)

<br>

### ⚙️ Configuração do Request Reply
```
URL: https://jsonplaceholder.typicode.com/posts
Query: id=${property.id}
```
![Fluxo](imagens/Screenshot_13.png)

<br>

# 🔹 5. Discord

### ➕ Configurando o Canal
![Fluxo](imagens/Screenshot_14.png)

<br>

### ➡️ Integrações
![Fluxo](imagens/Screenshot_15.png)

<br>

### ⚙️ Configuração do Webhooks 
![Fluxo](imagens/Screenshot_16.png)

<br>

### ➕ Adicionando o Webhooks
![Fluxo](imagens/Screenshot_17.png)

<br>

### 🏷️ Renomeandoo o Webhooks

![Fluxo](imagens/Screenshot_18.png)

<br>

# 🔹 7. Postman

### ➕ Enviando o POST
![Fluxo](imagens/Screenshot_19.png)

<br>

### 🏷️ Resultado no DISCORD
![Fluxo](imagens/Screenshot_20.png)


<br>
<br>

---

## 📦 Exemplo prático – iFlow para baixar

📦 [Download do iFlow – CPI_ZPKG_SEND_MESSAGE_DISCORD](https://github.com/souzajean/ZPKG_SEND_MESSAGE_DISCORD/raw/main/Package/IFL_SEND_MESSAGE_DISCORD.zip)
