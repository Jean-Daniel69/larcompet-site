# Contexto Técnico: LarcomPet (Sistema Atual)

## 1. Tecnologias Utilizadas

### Frontend & Plataforma
*   **CMS:** WordPress
*   **Construtor de Páginas:** Divi Builder
*   **JavaScript:**
    *   jQuery (incluído pelo WordPress e Divi)
    *   jQuery Migrate (carregado múltiplas vezes, indicando problemas de compatibilidade ou configuração)
    *   Scripts customizados para funcionalidades específicas (ex: chamada da API de preços).
*   **CSS:** CSS gerado pelo Divi, possivelmente com customizações manuais.

### Backend & Banco de Dados
*   **Linguagem:** PHP (padrão do WordPress e das aplicações nos iframes)
*   **Banco de Dados (Tabela de Preços):** AWS Aurora MySQL
*   **Plataforma Low-Code (Rede Credenciada):** PHPRunner

### Serviços de Terceiros & APIs
*   **Google Maps API:** Utilizada para exibir o mapa da rede credenciada.
    *   **Observação:** A implementação atual usa `google.maps.Marker` (obsoleto) e carrega a API de forma síncrona, prejudicando a performance.
*   **Meta Pixel:** Utilizado para tracking de marketing.
    *   **Observação:** Está sendo disparado duas vezes, o que pode levar a métricas incorretas e processamento desnecessário.
*   **API de Preços Customizada:** Uma API desenvolvida em PHP para buscar dados do banco Aurora MySQL e alimentar o iframe da tabela de preços.

## 2. Ambiente de Desenvolvimento e Hospedagem
*   **Hospedagem:** Não especificado, mas provavelmente um ambiente de hospedagem compartilhada ou VPS otimizado para WordPress.
*   **Servidor Web:** Apache ou Nginx.

## 3. Restrições Técnicas e Débitos

*   **Débito Técnico Principal:** A arquitetura baseada em iframes e no Divi é a maior fonte de débito técnico. Ela impede a otimização de performance, dificulta a manutenção e cria uma experiência de usuário fragmentada.
*   **Dependência de Plugins:** O ecossistema WordPress/Divi depende fortemente de plugins, que podem introduzir vulnerabilidades, conflitos e sobrecarga de performance.
*   **APIs Obsoletas:** O uso da `google.maps.Marker` API do Google Maps é um débito que precisa ser resolvido para garantir a longevidade e o suporte da funcionalidade.
*   **Falta de um "Build Step":** O desenvolvimento é feito diretamente no ambiente de produção ou staging. Não há um processo de build para otimizar (minificar, agrupar) assets como CSS e JavaScript, uma prática padrão em desenvolvimento web moderno.

## 4. Arquitetura e Stack de Reconstrução Proposta

*   **Framework Frontend:** Astro (com modo SSR - Server-Side Rendering).
*   **Versionamento de Código:** Git, com repositório no GitHub.
*   **Hospedagem Frontend:** Netlify (Plano Starter/Gratuito), integrado ao GitHub para CI/CD (Continuous Integration/Continuous Deployment).
*   **Hospedagem Backend:** Manter a estrutura atual na Turbo Cloud para a API de Preços (PHP/Aurora) e a aplicação de Rede Credenciada (PHPRunner).
*   **Estratégia de Migração:** O novo site será desenvolvido em um ambiente de staging na Netlify. O Go-live ocorrerá através da alteração do apontamento de DNS do domínio `larcompet.com.br` para o servidor da Netlify.