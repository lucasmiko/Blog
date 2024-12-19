# Sistema de Recomendação para Streaming de Filmes

## Visão Geral

Este documento descreve os passos envolvidos na implementação de um sistema de recomendação para um serviço de streaming de filmes usando **Microsoft.Extensions.VectorData**, **Qdrant** e **Azure AI Search**.

## Passos

1. **Coleta de Dados**
   - **Descrição**: Coletar dados sobre os filmes (títulos, descrições, gêneros, avaliações) e dados dos usuários (histórico de visualização, avaliações, preferências).
   - **Ferramentas**: Bancos de dados tradicionais para armazenar essas informações iniciais.

2. **Criação de Vetores**
   - **Descrição**: Converter os dados coletados em vetores numéricos que representam as características dos filmes e as preferências dos usuários.
   - **Ferramentas**: Usar **Microsoft.Extensions.VectorData** para facilitar a criação e manipulação desses vetores.

3. **Armazenamento de Vetores**
   - **Descrição**: Armazenar os vetores em um banco de dados vetorial para permitir buscas rápidas e eficientes.
   - **Ferramentas**: Utilizar **Qdrant** para armazenar os vetores de filmes e usuários.

4. **Busca Semântica**
   - **Descrição**: Implementar a busca semântica para encontrar filmes que correspondam às preferências dos usuários, mesmo que não contenham exatamente as mesmas palavras.
   - **Ferramentas**: Integrar **Azure AI Search** para realizar buscas semânticas e retornar resultados relevantes.

5. **Recomendações Personalizadas**
   - **Descrição**: Usar os resultados da busca semântica para gerar recomendações personalizadas para cada usuário.
   - **Ferramentas**: Combinar os vetores armazenados no **Qdrant** com os resultados da busca do **Azure AI Search** para criar uma lista de recomendações.

6. **Integração e Escalabilidade**
   - **Descrição**: Integrar todo o sistema na plataforma de streaming e garantir que ele possa escalar para atender a milhões de usuários.
   - **Ferramentas**: Usar **Azure AI Search** e **Semantic Kernel** para otimizar a performance e escalabilidade do sistema.

## Exemplo Prático

- **Usuário A** assiste a vários filmes de ficção científica e avalia positivamente.
- O sistema cria um vetor que representa as preferências do Usuário A.
- Quando o Usuário A acessa a plataforma, o sistema usa **Azure AI Search** para buscar filmes que correspondam ao vetor de preferências no **Qdrant**.
- O sistema retorna uma lista de filmes de ficção científica que o Usuário A provavelmente gostará, mesmo que os títulos ou descrições não contenham exatamente as palavras "ficção científica".

Esse processo permite que o serviço de streaming ofereça recomendações precisas e personalizadas, melhorando a experiência do usuário.

Documentações oficiais das tecnologias mencionadas:

- Introducing Microsoft.Extensions.VectorData Preview: https://devblogs.microsoft.com/dotnet/introducing-microsoft-extensions-vector-data/

- Microsoft.Extensions.VectorData.Abstractions: Now Available: https://devblogs.microsoft.com/semantic-kernel/microsoft-extensions-vectordata-abstractions-now-available/

- Exploring Microsoft.Extensions.VectorData with Qdrant and Azure AI Search: https://devblogs.microsoft.com/dotnet/vector-data-qdrant-ai-search-dotnet/

- Qdrant Documentation: https://qdrant.tech/documentation/

- Qdrant Configuration Guide: https://qdrant.tech/documentation/guides/configuration/

- Qdrant Local Quickstart: https://qdrant.tech/documentation/quickstart/

- Azure AI Search documentation: https://learn.microsoft.com/en-us/azure/search/

- Documentação da IA do Azure Search (em português): https://learn.microsoft.com/pt-br/azure/search/

- Introduction to Azure AI Search: https://learn.microsoft.com/en-us/azure/search/search-what-is-azure-search
