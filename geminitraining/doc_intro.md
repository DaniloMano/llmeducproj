# 💬 Chatbot RAG com Gemini 2.0 Flash (Langflow + ChromaDB)

Este repositório demonstra a criação de um **chatbot simples com RAG (Retrieval-Augmented Generation)** utilizando o modelo **Gemini 2.0 Flash**, através do **Langflow**, com base em um documento acadêmico da UFRN.

---

## 📚 Contexto

A base de conhecimento usada neste projeto foi o documento:

> **`regulamento_dos_cursos_de_graduacao`**  
> Documento oficial da Universidade Federal do Rio Grande do Norte (UFRN), que trata das normas dos cursos regulares de graduação.

---

## ▶️ Tutorial base

O projeto foi baseado no vídeo do canal *YAITEC Solutions*:
> [LANGFLOW – Monte Seus Próprios Agentes de IA (No-Code) – Versão Atualizada](https://www.youtube.com/watch?v=7jVO3j-qE4w)

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

- **Langflow**: interface visual para montar pipelines com LLMs e RAG.
- **LangChain**: biblioteca para orquestrar os componentes de IA.
- **Google Generative AI (Gemini 2.0 Flash)**: modelo usado para geração de respostas.
- **GoogleGenerativeAIEmbeddings**: embeddings gerados via LangChain (`langchain-google-genai`).
- **ChromaDB**: usado como vetor store para recuperação de contexto relevante.
- **PDF Loader**: utilizado dentro do Langflow para carregar o conteúdo do documento.

---

## 🧩 Estrutura Lógica do Projeto (via Langflow)

1. **Carregamento do Documento**  
   - O documento em PDF foi carregado com um nó de `PDFLoader`.

2. **Geração de Embeddings**  
   - Embeddings gerados com o `GoogleGenerativeAIEmbeddings`.

3. **Armazenamento Vetorial**  
   - Armazenamento e busca feitos com o `Chroma Vector Store`.

4. **Agente Gemini**  
   - Utilização do modelo `gemini-2.0-flash` através do componente `Google Generative AI`.

5. **Prompt customizado**  
   - O chatbot foi instruído a sempre consultar o documento `regulamento_dos_cursos_de_graduacao` para responder dúvidas com precisão.

---

## 🧪 Resultados dos Testes

Apesar de uma certa **latência nas respostas** (possivelmente relacionada ao Langflow ou à simplicidade da estrutura montada), os testes apresentaram **respostas bastante precisas e contextualizadas** com base no conteúdo do documento.

> ⚠️ *Nota: Caso a lentidão seja relacionada ao Langflow, uma arquitetura mais robusta ou otimização do pipeline pode melhorar o tempo de resposta.*

---

## ✅ Exemplos de Perguntas Testadas

- "Quantas vezes posso trancar uma disciplina?"
- "O que acontece se eu perder o prazo para matrícula?"
- "Qual o tempo máximo para concluir um curso de graduação?"

---
## Resultados Rasos

- Apesar do aumento da precisão, alucinação ainda é um problema.
- Engenharia de Prompt se mostrou eficaz para combater alucinação.
- É necessário realizar restes com uma bateria de testes melhor para provar a eficácia da engenharia de prompt (e melhorar ela) como sendo mais viável que optar pelo uso de uma llm alternativa.

---
## 📦 Requisitos

- Conta no [Google AI Studio](https://makersuite.google.com/app)
- Chave da API do Gemini ativada
- DataStax Langflow (nesse teste foi usado a versão web)
