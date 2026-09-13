# LifePet - VetBot

Disruptive Architectures: IoT, IoB & Generative IA — Challenge FIAP 2026
Empresa parceira: Clyvo VET

---

## Problema

A jornada de saúde do pet é fragmentada e reativa. O tutor só busca orientação veterinária quando o animal já apresenta sintomas visíveis. A falta de acompanhamento preventivo contínuo compromete a saúde animal e sobrecarrega as clínicas com casos que poderiam ter sido evitados.

## Solução

O VetBot é o assistente de inteligência artificial do LifePet. Ele permite que tutores conversem em linguagem natural para consultar o histórico clínico dos seus pets, receber orientações preventivas personalizadas e identificar sinais de alerta que exigem atenção veterinária.

O sistema combina três tecnologias de IA:

- Function Calling para consultar dados reais de vacinas, consultas e medicamentos de cada pet
- RAG (Retrieval Augmented Generation) para enriquecer as respostas com conhecimento veterinário técnico
- Interactions API do Gemini para manter histórico de conversa entre as mensagens

---

## Tecnologias

- Modelo de linguagem: Gemini 3.5 Flash (Google)
- Embeddings: gemini-embedding-001
- SDK: google-genai
- Ambiente: Google Colab
- Linguagem: Python 3

---

## Arquitetura

```
Tutor (usuário)
      ↓
  VetBot (Gemini 3.5 Flash)
      ↓              ↓
Function Calling     RAG
      ↓              ↓
 Dados dos pets   Base de conhecimento
 (vacinas,        veterinária
  consultas,      (8 documentos)
  medicamentos)
```

O tutor faz uma pergunta. O VetBot busca os documentos mais relevantes da base veterinária via RAG e, se necessário, consulta os dados reais do pet via Function Calling. A resposta é gerada com base nos dois contextos combinados.

---

## Funcionalidades

- Consulta de vacinas, consultas e medicamentos por pet
- Recomendações preventivas baseadas em idade, raça e histórico
- Identificação de sinais de alerta que exigem consulta imediata
- Histórico de conversa mantido entre as mensagens
- Base de conhecimento veterinária com 8 documentos especializados

---

## Como executar

**1. Abrir no Google Colab**

Acesse o notebook `lifepet_assistente.ipynb` e abra no Google Colab.

**2. Configurar a chave da API**

No menu lateral do Colab, clique no ícone de chave (Secrets) e adicione:
- Nome: `GEMINI_API_KEY`
- Valor: sua chave do Google AI Studio (aistudio.google.com/apikey)

**3. Executar**

Clique em Runtime > Run all para executar todas as células em ordem.

---

## Estrutura do projeto

```
LifePet-IA-3-sprint/
├── lifepet_assistente.ipynb   — notebook principal com o VetBot
└── README.md                  — documentação
```

---

## Como o VetBot se encaixa no LifePet

O LifePet já possui módulos de vacinas, consultas, medicamentos e histórico clínico. O VetBot é a camada de inteligência artificial que conecta esses dados ao tutor em linguagem natural, transformando o cuidado do pet de reativo para preventivo e contínuo — exatamente o que a Clyvo VET propõe.

---

## Resultados parciais

- Assistente conversacional funcionando com histórico de conversa
- Function Calling com 4 ferramentas integradas aos dados dos pets
- RAG com 8 documentos veterinários indexados por similaridade semântica
- Respostas personalizadas por espécie, raça, idade e histórico clínico

---

## Equipe da LifePet

Aguinel Junior - RM564857

Felipe Garcia - RM563485

Henrique Gonçalves - RM562086

Leonardo Saavedra - RM562229

Vitor Mendes - RM565376
