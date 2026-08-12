# ScoutPro Showcase Evolution Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Evoluir o showcase público do ScoutPro com uma abertura visual de cards de alto rating e uma demonstração da mudança de avaliação conforme o contexto competitivo.

**Architecture:** A apresentação continuará estática e baseada em README + SVG autorais. O primeiro SVG será uma galeria de cards premium com dados demonstrativos; o segundo será uma sequência comparativa do mesmo atleta em três ambientes competitivos. O README apresentará esses blocos antes da explicação metodológica.

**Tech Stack:** Markdown renderizado pelo GitHub, SVG autoral, Git, PowerShell para validações estruturais.

## Global Constraints

- Não usar logos, símbolos, layouts ou identidade visual proprietária de FIFA, PES, eFootball, Football Manager ou outras plataformas.
- Usar apenas a essência visual de cards esportivos: rating, raridade, moldura, brilho, atributos e estrelas.
- Não expor atletas pesquisados em ambientes privados, usuários, clubes em teste ou informações reais de contas.
- Usar dados demonstrativos e indicar visualizações ilustrativas quando necessário.
- Manter a leitura adequada em desktop e mobile.
- O showcase não deve conter código-fonte, dados operacionais ou segredos do ScoutPro.

---

### Task 1: Criar a abertura com cards premium

**Files:**
- Create: `assets/scoutpro-card-showcase.svg`
- Modify: `README.md`
- Test: validação estrutural do SVG e referências do README

**Interfaces:**
- Produces: `assets/scoutpro-card-showcase.svg`, uma composição com cards demonstrativos de rating elite, lendário e diamante.
- Consumes: `assets/scoutpro-logo-real.jpg` apenas no cabeçalho já existente; não inserir logos de jogos externos.

- [ ] **Step 1: Definir o conteúdo demonstrativo dos cards**

Usar nomes conhecidos apenas como referências visuais de demonstração, sem fotos oficiais, escudos reais ou afirmação de avaliação oficial. Cada card deve conter nome, posição, rating, categoria, estrelas e quatro ou seis atributos resumidos.

Usar as faixas:

- Elite: rating 88, acabamento prateado premium;
- Lendário: rating 94, acabamento dourado;
- Diamante: rating 99, acabamento cristalino.

- [ ] **Step 2: Criar o SVG autoral**

O SVG deve ter um fundo escuro, três cards verticais responsivos dentro de uma área panorâmica, molduras diferentes por raridade, brilho construído com gradientes e filtros SVG, e texto legível em largura reduzida. Não importar imagens externas.

- [ ] **Step 3: Inserir o bloco no README**

Adicionar a imagem logo após a introdução institucional, antes da explicação metodológica, com a legenda `Cards demonstrativos do ScoutPro, inspirados na linguagem visual dos games e sem dados oficiais de avaliação.`

- [ ] **Step 4: Validar a primeira entrega**

Run: `git diff --check`

Expected: nenhuma falha de whitespace.

Run: validação PowerShell que confirme que o SVG existe, começa com `<svg`, contém `Elite`, `Lendário` e `Diamante`, e que o README referencia o arquivo.

Expected: todas as condições verdadeiras.

- [ ] **Step 5: Commit**

```powershell
git add README.md assets/scoutpro-card-showcase.svg
git commit -m "Add premium ScoutPro card showcase"
```

### Task 2: Demonstrar rating contextual por nível competitivo

**Files:**
- Create: `assets/scoutpro-context-evolution.svg`
- Modify: `README.md`
- Test: validação estrutural do SVG e referências do README

**Interfaces:**
- Produces: `assets/scoutpro-context-evolution.svg`, comparação visual de um atleta fictício em três contextos.
- Consumes: a linguagem visual dos cards criada na Task 1, sem reutilizar dados reais.

- [ ] **Step 1: Definir o cenário de comparação**

Representar o mesmo atleta fictício em:

`Clube sem divisão → Série D → Série C`

Mostrar rating contextual, estrelas de adequação, categoria visual e uma justificativa curta. O rating global deve aparecer separado para explicar que o atleta não mudou necessariamente de qualidade.

- [ ] **Step 2: Criar o SVG comparativo**

Criar três cards ou painéis conectados por uma seta de evolução. Usar dados demonstrativos, por exemplo: rating global 78, rating contextual 78 no clube sem divisão, 72 na Série D e 58 na Série C. A composição deve indicar que a régua muda conforme o ambiente.

- [ ] **Step 3: Inserir a explicação no README**

Adicionar a imagem depois da seção de cards e antes da seção de metodologia, acompanhada de um parágrafo justificando rating global, rating contextual e estrelas de adequação.

- [ ] **Step 4: Validar a segunda entrega**

Run: `git diff --check`

Expected: nenhuma falha de whitespace.

Run: validação PowerShell que confirme que o SVG contém `Clube sem divisão`, `Série D`, `Série C`, `rating global` e `rating contextual`, e que o README referencia o arquivo.

Expected: todas as condições verdadeiras.

- [ ] **Step 5: Commit**

```powershell
git add README.md assets/scoutpro-context-evolution.svg
git commit -m "Explain contextual ScoutPro ratings"
```

### Task 3: Verificação visual e publicação

**Files:**
- Verify: `README.md`
- Verify: `assets/scoutpro-card-showcase.svg`
- Verify: `assets/scoutpro-context-evolution.svg`

**Interfaces:**
- Consumes: as duas artes e o texto final do README.
- Produces: branch pública sincronizada e showcase pronto para revisão.

- [ ] **Step 1: Verificar referências e arquivos**

Confirmar que todas as imagens referenciadas no README existem no diretório `assets` e que nenhum SVG textual antigo do cabeçalho foi reintroduzido.

- [ ] **Step 2: Inspecionar responsividade**

Abrir o README publicado em largura desktop e mobile. Conferir que os cards continuam legíveis, que nenhum texto fica cortado e que as cores mantêm contraste no tema claro e escuro.

- [ ] **Step 3: Revisar segurança de conteúdo**

Confirmar que não existem nomes de usuários, clubes em teste, URLs privadas, fotos reais de atletas ou dados de conta nas novas artes.

- [ ] **Step 4: Publicar**

```powershell
git push origin main
```

- [ ] **Step 5: Confirmar readback**

Buscar o README pela API do GitHub e confirmar as duas referências de imagem, a descrição dos dados demonstrativos e a ausência do SVG textual antigo.
