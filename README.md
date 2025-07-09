# Laboratório: Organização e Pesquisa de Documentos com Azure AI Search

## Visão Geral do Projeto

Este laboratório prático tem como objetivo aplicar técnicas de organização e pesquisa de documentos utilizando o **Azure AI Search**. Através da ingestão de dados, criação de índices inteligentes e exploração das funcionalidades de busca, este projeto demonstra como ferramentas de Inteligência Artificial podem ser empregadas para minerar e extrair conhecimento de grandes volumes de informação.

O foco principal é desenvolver uma compreensão sólida sobre a aplicação prática do Azure AI Search para **otimização da recuperação de informações**.

---

## Desafio Proposto

O desafio consiste em documentar a experiência de configurar e utilizar o **Azure AI Search** para indexar e pesquisar um conjunto de **avaliações de clientes (reviews)**. Foram seguidos os três passos essenciais abordados nas aulas:

1. **Ingestão de Conteúdo para IA**  
   Carregamento dos dados das avaliações no **Azure Blob Storage**, servindo como fonte para o Azure AI Search.

2. **Criação de Índices Inteligentes**  
   Definição e configuração de um índice para processar e indexar os dados, incluindo **extração de entidades** e **análise de sentimento**.

3. **Exploração Prática dos Dados Organizados**  
   Realização de consultas para demonstrar a capacidade de busca e a extração de insights a partir das avaliações.

---

## Objetivos de Aprendizagem Alcançados

- ✅ Aplicar os conceitos aprendidos em um ambiente prático, configurando o Azure AI Search.
- ✅ Documentar processos técnicos de forma clara e estruturada.
- ✅ Utilizar o GitHub como ferramenta para compartilhamento de documentação técnica.

---

## Etapas Realizadas e Insights Obtidos

### 1. Ingestão de Dados

Os dados de reviews foram carregados no **Azure Blob Storage**. Estes arquivos (em `.txt` e `.pdf`) contêm avaliações de clientes sobre a cafeteria fictícia **Fourth Coffee**.

**Arquivos de Origem**:
- `sentimento negative.txt`
- `tudo.txt`
- `location chicago.txt`
- `prints.pdf`
- `reviews.pdf`

**Conteúdo dos Dados**:
- Exemplo 1: Review negativa de *Chicago* (23/10/2018) mencionando **pastéis estragados**.
- Exemplo 2: Review positiva de *Chicago* (21/10/2018) elogiando o ambiente, **Wi-Fi** e produtos.

---

### 2. Configuração do Azure AI Search

Foi configurado um serviço de Azure AI Search para indexar as avaliações.

**Skillset para Enriquecimento de Dados**:
- Criado o **coffee skillset** para extração de informações adicionais.
- Habilitado **OCR** e mesclagem de conteúdo no campo `merged_content`.

**Extração de Entidades**:
- Pessoas (`people`)
- Organizações (`organizations`)
- Localizações (`locations`)
- Frases-chave (`keyphrases`)
- Idioma (`language`)

**Análise de Sentimento**:
- Classificação automática das reviews como **positiva**, **negativa** ou **mista**.

---

### 3. Criação e Execução do Indexador

Foi criado o indexador `coffee-indexer` para processar os dados do Blob Storage e alimentar o índice.

**Status**:
- Executado com sucesso.
- **9 documentos processados** sem erros (Registro: 09/07/2025 às 15:56).

---

### 4. Exploração das Funcionalidades de Busca

Após a indexação, o **Search Explorer** foi utilizado para testar consultas e validar os resultados.

#### Exemplos de Consulta:

- **Busca por Sentimento Negativo**:
  ```text
  sentiment: negative
  ```
  - Resultado: Review com `search.score = 0.2875621`
  - Destaques: "Terrible experience", "Chicago, Illinois", menção a **espera longa** e **pastéis velhos**.

- **Busca por Localização e Keyphrases**:
  - Localização: `"Chicago"`, `"Illinois"`
  - Frases-chave: `"delicious baked goods"`, `"lavender honey latte"`, `"apple-chai latte"`

#### Insights:

- **3 reviews de Chicago** foram encontradas:
  - 2 positivas: elogiando **café**, **música local** e **ambiente de reunião com Wi-Fi**.
  - 1 negativa: destacando **atendimento demorado** e **produtos de má qualidade**.

---

## Recursos Úteis

- 🔗 [Explore an Azure AI Search index (UI) - Microsoft Learn](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html)

---

## Conclusão

Este laboratório proporcionou uma **experiência prática valiosa** na utilização do Azure AI Search para organizar e pesquisar documentos.

As principais lições incluem:
- Ingestão de dados estruturados e não estruturados.
- Enriquecimento com **habilidades de IA** como extração de entidades e análise de sentimento.
- Potente funcionalidade de busca e **recuperação de informação contextualizada**.

A documentação clara e a estruturação no GitHub reforçam o entendimento técnico e servem como **portfólio da experiência adquirida**.
