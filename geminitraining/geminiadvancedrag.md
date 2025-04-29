# 🧠 Gemini Advanced RAG com Langflow
Este modelo implementa um fluxo de RAG Avançado (Geração Aumentada por Recuperação) usando Langflow, projetado para o Gemini responder perguntas com base exclusivamente em um documento institucional da UFRN. O sistema garante respostas precisas, controladas e verificáveis.

# ⚙️ Etapas do Processo
## 📥 1. Input do Usuário
O usuário insere uma pergunta no componente ChatInput.

A pergunta é enviada para pré-processamento e conversão em consulta vetorial.

## 🧹 2. Pré-processamento da Pergunta
Um Agent realiza ajustes na pergunta original para torná-la mais adequada à busca semântica.

Objetivo: evitar ambiguidade e garantir uma boa correspondência com os documentos vetorizados.

## 🔎 3. Conversão para Vetor de Consulta
Utiliza o Google Generative AI Embeddings para transformar a pergunta processada em um vetor semântico.

A conversão alimenta o mecanismo de busca no banco vetorial (Vector Store).

## 🗂️ 4. Busca no Banco de Dados Vetorial
O componente Chroma DB é usado para recuperar trechos do regulamento mais relevantes com base na similaridade vetorial.

Retorna os top-N resultados da pesquisa como context.

## 🧽 5. Filtragem dos Resultados
Um Prompt personalizado e um Agent refinam o conteúdo dos trechos retornados:

Seleciona apenas os trechos mais diretamente relacionados à pergunta.

Remove conteúdos genéricos, duplicados ou que não ajudam a responder.

## 🤖 6. Resposta da LLM Principal
A LLM recebe:

A pergunta original.

O contexto filtrado.

Gera uma resposta exclusivamente com base no documento, respeitando instruções específicas como citar artigos e evitar suposições.

## 💬 7. Entrega da Resposta ao Usuário
A resposta final é enviada ao componente ChatOutput, onde o usuário vê o resultado processado.

## 🧠 Características Avançadas
- 🔍 Busca semântica vetorial: mais eficaz que busca por palavras-chave.

- 📑 Filtragem contextual: evita que a LLM tenha acesso a informações irrelevantes.

- 📘 Conformidade do Documento: respostas são sempre baseadas no documento.

- 🔄 Reutilização e validação em camadas: possível integração com revisores de resposta, validação binária, entre outros.

## 🛠️ Tecnologias e Componentes
Langflow

Google Generative AI Embeddings

Chroma Vector Store

Prompt customizado para filtragem e geração

Gemini como LLM principal

Fluxo modular e expandível

## 📌 Observações
- O sistema pode receber outros documentos.
- Necessita-se de uma bateria de testes para validar esta modelo do Advnc RAG, assim como a engenharia de prompt (nos nodes de prompt, ou agent instructions e templates nos agentes de llm) deste modelo
- Se necessário, corrigir aspectos do modelo com base em ajustes com orientação docente a fim de chegar aos resultados ou formatações esperados.