## Objetivo

Orientações rápidas para agentes AI trabalharem produtivamente neste repositório estático.

## Visão geral (big picture)

- Projeto: site estático da ONG Verde Ação (HTML + SCSS/CSS). Arquivos principais são `index.html`, `style.scss` e o CSS gerado `style.css`.
- Padrão: o código-fonte de estilos é `style.scss` (Sass com aninhamento). O arquivo `style.css` é o output compilado.
- Design: Paleta de cores verde (`rgb(124, 229, 124)`, `#66BB6A`) com texto branco (`#ffffff`)

## Arquivos-chave

- `index.html` — estrutura da página em pt-BR com:
  - Header contendo título e navegação
  - Conteúdo principal com imagem e texto descritivo
  - Links de navegação: "Atividades" e "Cadastre-se"
- `style.scss` — fonte principal de estilos com comentários em PT-BR e uso de aninhamento
- `style.css` — CSS compilado (não editar diretamente)

## Convenções e padrões do projeto

- Nunca editar o `style.css` manualmente para mudanças de estilo persistentes: altere `style.scss` e recompile (CSS é gerado)
- Comentários e explicações no `style.scss` estão em Português; mantenha esse idioma ao adicionar documentação inline
- Layout do header:
  - Usa flexbox (`display: flex`) no container
  - Elementos internos com `display: inline-block`
  - Larguras fixas: `h2 { width: 30% }`, `nav { width: 40% }` 
- Cores do projeto:
  - Verde claro (header): `rgb(124, 229, 124)`
  - Verde escuro (elementos): `#66BB6A`
  - Texto em branco: `#ffffff`

## Fluxos de desenvolvedor (comandos PowerShell)

- Compilar SCSS para CSS (recomendado usar Dart Sass):

  sass style.scss style.css --no-source-map

  (Se preferir usar npm local)

  npm i -D sass
  npx sass style.scss style.css --no-source-map

- Servir localmente: não há script de build. Use a extensão Live Server do VS Code ou um servidor estático simples.

  Exemplo (PowerShell com Python se disponível):

  python -m http.server 5500

  Depois abrir http://localhost:5500

## Pontos específicos a checar/atuar

- Corrigir a referência de CSS em `index.html`: trocar `styles.css` por `style.css` ou renomear o arquivo compilado para `styles.css` — preferível ajustar `index.html` para manter nome único e evitar divergências.
- Verificar se o `sourceMappingURL` é intencional. Se não usa mapas, remova `/*# sourceMappingURL=style.css.map */` do CSS compilado ou gere o mapa ao compilar.

## Boas práticas para commits/PRs aqui

- Mudar apenas o SCSS (não o arquivo compilado) em alterações de estilo, e incluir no PR a nota: "Recompilei SCSS para CSS" se você atualizar também o CSS gerado.
- Pequenas alterações de markup devem vir com screenshots ou descrição visual do impacto (site é estático, fácil verificar manualmente).

## Integrações externas / dependências

- Nenhuma integração ou build pipeline descoberta no repositório. Tudo é local/estático.

## Exemplo rápido (ao fazer uma alteração de cor no header)

1. Editar `style.scss` > `header { background-color: ... }`
2. Rodar `sass style.scss style.css --no-source-map`
3. Abrir `index.html` no Live Server / navegador e verificar mudança

## Se encontrar outros arquivos de orientação

Se já existir `.github/copilot-instructions.md` ou arquivos AGENT.md em subpastas, favor informar para mesclar; por ora este arquivo foi criado porque não foram encontrados arquivos de orientação no workspace.

---
Se quiser, ajusto o tom (mais técnico ou mais direto) e adiciono exemplos de PR template ou de comandos npm/CI.
