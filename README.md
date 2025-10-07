# 🚀 Automação Simulada com AWS Lambda e S3  

Este projeto é uma *simulação* do desafio da DIO, cujo objetivo é demonstrar o fluxo de automação entre o *Amazon S3* e o *AWS Lambda*, sem necessidade de provisionar recursos reais.  

---

## 📌 Descrição  

A proposta é mostrar como funcionaria uma automação em que, ao enviar um arquivo para um bucket do *Amazon S3, uma **função Lambda* é acionada automaticamente para processar esse arquivo e registrar logs no *CloudWatch*.  

---

## 🎯 Objetivos  

- Entender a integração entre S3 e Lambda.  
- Representar o fluxo de eventos sem custos reais.  
- Documentar boas práticas de *Infraestrutura como Código (IaC)*.  

---

## ⚙️ Estrutura Simulada  

### 1️⃣ Bucket S3  
- Nome fictício: meu-bucket-dio-lambda  
- Pastas:
input/
processed/

### 2️⃣ Função Lambda (simulada)  
- Nome: processa-arquivo-s3  
- Runtime: Python 3.9  
- Permissões (simuladas): leitura em input/, escrita em processed/.  

### Código exemplo (não executado)

### 2️⃣ Função Lambda (simulada)  
- Nome: processa-arquivo-s3  
- Runtime: Python 3.9  
- Permissões (simuladas): leitura em input/, escrita em processed/.  

### Código exemplo (não executado)

```python
import json, os

def lambda_handler(event, context):
    print("Evento simulado:", json.dumps(event))
    key = "input/arquivo_teste.txt"
    dest_key = f"processed/arquivo_teste.txt"
    print(f"Simulação: {key} seria processado e copiado para {dest_key}")
    return {"statusCode": 200, "body": "Arquivo processado (simulação)"}
```




3️⃣ Evento (Trigger)
	•	Configuração simulada de trigger no S3:
	•	Tipo: PUT (upload em input/)
	•	Destino: Lambda processa-arquivo-s3

⸻

4️⃣ Teste Simulado
	•	Upload de arquivo fictício: input/arquivo_teste.txt
	•	Resultado esperado:
	•	Lambda dispara.
	•	Log no CloudWatch (simulado).
	•	Arquivo aparece em processed/arquivo_teste.txt.


graph TD;
    A[S3 - Upload em input/] -->|Evento PUT| B[Lambda - processa-arquivo-s3];
    B --> C[CloudWatch - Logs simulados];
    B --> D[S3 - processed/arquivo_teste.txt];


✅ Conclusão

Mesmo sem provisionar recursos reais na AWS, este exercício demonstra:
	1.	Como o S3 e o Lambda trabalham juntos.
	2.	O conceito de event-driven architecture.
	3.	A importância de registrar logs e processar arquivos automaticamente.

⸻

💡 Esse repositório é uma simulação didática para fins de estudo, sem custos reais na AWS.
