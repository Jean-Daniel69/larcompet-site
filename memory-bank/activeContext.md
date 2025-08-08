# Contexto Ativo: Análise e Planejamento da Reconstrução

## 1. Foco Atual

O foco atual é a **Fase de Análise e Planejamento**. O objetivo é dissecar completamente o projeto existente, documentar suas falhas e qualidades, e propor uma estratégia sólida para a reconstrução do site da LarcomPet.

## 2. Decisões e Considerações Atuais

*   **Problema Central Identificado:** A arquitetura baseada em WordPress/Divi com múltiplos iframes é a causa raiz dos problemas de performance e usabilidade. A reconstrução é a abordagem mais provável para alcançar os objetivos do projeto.
*   **Necessidade de uma Nova Stack:** A stack tecnológica precisa ser redefinida. As opções devem priorizar a performance (especialmente no lado do cliente), a facilidade de manutenção e a capacidade de integração direta com APIs.
*   **Alternativas aos Iframes:** É mandatório encontrar substitutos para os iframes. As principais hipóteses são:
    *   **Tabela de Preços:** Componente de frontend (React, Vue, Svelte, etc.) que consome a API PHP/Aurora diretamente.
    *   **Rede Credenciada:**
        1.  Consumir dados da aplicação PHPRunner via API.
        2.  Migrar a lógica e os dados do PHPRunner para uma nova API e banco de dados.
    *   **Mapa:** Integração direta com a API do Google Maps (ou uma alternativa como Leaflet) usando a biblioteca mais recente e performática.

## 3. Próximos Passos Imediatos

1.  **Finalizar a Criação do Banco de Memória:** Criar o arquivo `progress.md`.
2.  **Desenvolver um Plano de Reconstrução:** Detalhar a proposta de nova arquitetura, a stack tecnológica recomendada e um cronograma macro.
3.  **Apresentar o Plano ao Cliente:** Obter validação e feedback sobre a estratégia proposta.
4.  **Transição para a Fase de Implementação:** Uma vez que o plano seja aprovado, mudar para o modo de desenvolvimento para começar a execução.

## 4. Aprendizados e Padrões do Projeto

*   **Padrão de Falha:** A tentativa de "remendar" uma plataforma inadequada (WordPress para uma aplicação web-like) com iframes levou a um sistema lento e frágil.
*   **Insight Chave:** A solução não está em otimizar o site atual, mas em repensar a arquitetura desde o início, tratando o site como uma aplicação web e não como um blog ou site institucional simples. A interatividade (preços, mapas) é central para o negócio.