# 🚀 SEND_MESSAGE_DISCORD

## SAP BTP CPI - SEND_MESSAGE_DISCORD

🎯 🧩 Objetivo do iFlow

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


# 🔹 3. HTTPS Sender (Trigger)
```
Endpoint: /discord
```
![Fluxo](imagens/Screenshot_6.png)

# 🔹 4. Content Modifier

### ➕ Adicionando o Content Modifier
![Fluxo](imagens/Screenshot_7.png)

<br>

### 🏷️ Renomeando o Content Modifier
![Fluxo](imagens/Screenshot_8.png)
```
Nome: sendBody
```

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


# 🔹 5. Request Reply (Chamada API)

### ➕ Adicionando Request Reply
![Fluxo](imagens/Screenshot_10.png)

<br>

### 🏷️ Renomeando o Request Reply
![Fluxo](imagens/Screenshot_11.png)
```
Nome: API_jsonplaceholder
```

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

# 🔹 6. Content Modifier (Get Payload)

### ➕ Adicionando o Content Modifier
![Fluxo](imagens/Screenshot_14.png)

<br>

### 🏷️ Renomeando o Content Modifier
![Fluxo](imagens/Screenshot_15.png)
```
Nome: cm_get_payload
```

<br>

### ⚙️ Configuração do Content Modifier 
![Fluxo](imagens/Screenshot_16.png)
Message Body
```
Type: Expression
Body: ${body}
```
# 🔹 7. Content Modifier (Prepare Payload)

### ➕ Adicionando o Content Modifier
![Fluxo](imagens/Screenshot_17.png)

<br>

### ⚙️ Configuração do Content Modifier

![Fluxo](imagens/Screenshot_18.png)

<br>

# 🔹 8. Groovy Script (ENCODER Base64)

### ➕ Adicionando o Adapter Groovy Script
![Fluxo](imagens/Screenshot_19.png)

<br>

### 🏷️ Renomeando o Groovy Script
![Fluxo](imagens/Screenshot_20.png)
```
Nome: groovy_encode
```


<br>
<br>

---

## 📦 Exemplo prático – iFlow para baixar

📦 [Download do iFlow – CPI_ZPKG_SEND_MESSAGE_DISCORD](https://github.com/souzajean/ZPKG_SEND_MESSAGE_DISCORD/raw/main/Package/IFL_SEND_MESSAGE_DISCORD.zip)
