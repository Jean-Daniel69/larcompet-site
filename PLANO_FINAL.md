# Plano Final de Reconstrução: Site LarcomPet

## 1. Resumo do Problema

O site atual (`larcompet.com.br`), construído em WordPress/Divi, sofre com baixa performance (nota 67 no PageSpeed Mobile), resultando em uma taxa de conversão próxima de zero apesar do tráfego existente. A arquitetura baseada em iframes para funcionalidades críticas (preços, rede credenciada) é a principal causa dos problemas.

## 2. Objetivos do Projeto

*   **Performance:** Aumentar drasticamente as métricas de performance do site.
*   **Conversão:** Otimizar a jornada do usuário para transformar visitantes em clientes.
*   **Tecnologia:** Modernizar a stack para facilitar a manutenção e a evolução.
*   **Whitelabel:** Suportar a criação de versões personalizadas do site para parceiros comerciais.

## 3. Stack Tecnológica e Arquitetura

*   **Framework Frontend:** **Astro**, utilizando o modo de **Renderização no Servidor (SSR)**. Esta escolha visa máxima performance e flexibilidade para atender ao requisito de whitelabel.
*   **Versionamento de Código:** O projeto será controlado com **Git** e hospedado em um repositório no **GitHub**.
*   **Hospedagem:**
    *   **Frontend (Site Astro):** **Netlify**, começando com o plano gratuito (Starter) que permite uso comercial.
    *   **Backend (APIs existentes):** A infraestrutura atual na **Turbo Cloud** será mantida para rodar a API de preços (PHP/Aurora) e a aplicação da rede credenciada (PHPRunner).
*   **Arquitetura Geral:** Abordagem **Headless**, onde o frontend (Astro na Netlify) é desacoplado e consome os dados do backend (Turbo Cloud) via chamadas de API.

## 4. Estratégia de Migração e Go-Live

1.  O novo site será desenvolvido e testado em um ambiente de staging seguro na Netlify, sem qualquer interferência no site atual.
2.  As aplicações de backend permanecerão na Turbo Cloud.
3.  O "Go-live" (lançamento) será realizado através de uma simples alteração no **apontamento de DNS** do domínio `larcompet.com.br`, direcionando o tráfego para a nova aplicação na Netlify. Este método garante um downtime mínimo ou nulo.

## 5. Próximos Passos Imediatos

1.  Criação do repositório do projeto no GitHub.
2.  Mudança para o modo de implementação (Code Mode).
3.  Configuração inicial do projeto Astro no ambiente de desenvolvimento local.
4.  Início do desenvolvimento do frontend e das integrações.