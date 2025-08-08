# Progresso do Projeto: Reconstrução LarcomPet

## Status Atual: Fase 1 - Análise e Planejamento

## O que Funciona (no Conceito)

*   **Modelo de Negócio:** A proposta de valor de oferecer um plano de assistência pet é validada pelo mercado e pela demanda existente (alto volume de cliques).
*   **Fontes de Dados:** Existem fontes de dados definidas para as funcionalidades dinâmicas:
    *   Um banco de dados Aurora MySQL para preços.
    *   Uma aplicação PHPRunner para a rede credenciada.
    *   A API do Google Maps para geolocalização.

## O que Falta Construir (Visão de Futuro)

Tudo. O projeto visa uma reconstrução completa. A lista de trabalho inclui:

*   **Frontend:** Uma nova interface de usuário, construída com um framework moderno (ex: Next.js, SvelteKit, Astro).
*   **Backend/APIs:**
    *   Manter ou refatorar a API de preços.
    *   Criar uma nova API para a rede credenciada, substituindo a necessidade de carregar a aplicação PHPRunner via iframe.
*   **Infraestrutura:** Definir e configurar um novo ambiente de hospedagem otimizado para a nova stack.
*   **Design System:** Criar um sistema de design coeso para garantir consistência visual e de usabilidade.

## Problemas Conhecidos (Sistema Atual)

*   **Performance:**
    *   Pontuação geral de 67 no PageSpeed Insights (mobile).
    *   First Contentful Paint (FCP): 3.6s (lento).
    *   Largest Contentful Paint (LCP): 5.9s (muito lento).
    *   Total Blocking Time (TBT): 150ms (aceitável, mas pode ser melhorado).
*   **Erros de Console:**
    *   Erro de JS `et_pb_custom is not defined`.
    *   Pixel do Meta duplicado.
    *   Carregamento síncrono e API obsoleta do Google Maps.
    *   JQuery Migrate carregado múltiplas vezes.
    *   Erro na chamada da API de preços (`Erro ao buscar ou processar planos`).
*   **Arquitetura:** O uso de iframes é o principal gargalo de performance e usabilidade.
*   **Conversão:** A taxa de conversão é próxima de zero, indicando falhas graves na jornada do usuário e/ou na comunicação (copy).

## Evolução das Decisões

*   **Decisão Inicial (Cliente):** Construir o site com WordPress e Divi, provavelmente por familiaridade e agilidade percebida.
*   **Decisão Atual (Kilo Code):** A abordagem inicial se provou inadequada para os objetivos do negócio. A decisão pendente é sobre qual nova stack tecnológica adotar para a reconstrução, com forte inclinação para uma arquitetura baseada em componentes de frontend e APIs (Jamstack/Headless).