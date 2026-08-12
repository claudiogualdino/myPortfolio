# Acervo — Património

App offline (PWA) para gerir o património mobiliário. Sem servidor, sem contas: os dados ficam
**cifrados no dispositivo** (AES-GCM, chave derivada do PIN por PBKDF2). Sem recuperação de PIN.

## Publicar em GitHub Pages

1. Faz upload do conteúdo desta pasta `dist/` para a raiz do repositório (`index.html`,
   `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`).
2. **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)` → Save.**
3. Ao fim de ~1 minuto a app fica em `https://claudiogualdino.github.io/myPortfolio/`.
4. No Android: abre o link no Chrome → menu ⋮ → **Adicionar ao ecrã principal**.

Funciona offline depois da primeira abertura (service worker).

## Dados

- Arranca com as 17 posições do Excel `Patrimonio mobiliário_12082026_beta_test.xlsx`.
- **Ajustes → Importar Excel** substitui tudo pelo ficheiro (colunas A–F: Tipologia, Broker, Valor, Owner, NIF, Observ).
- **Ajustes → Exportar cópia (CSV)** guarda posições + histórico.
- Cada edição grava automaticamente o total do dia no histórico (um registo por dia), incluindo o valor por tipologia.

## Evolução (v2)

- Gráfico de área interativo: toca num ponto para ver o valor e a variação desse registo.
- Períodos 1M / 6M / 1A / Máx.
- Média por mês, melhor mês e crescimento anual (CAGR, a partir de ~45 dias de histórico).
- Objetivo de património: define o valor no ecrã Evolução — barra de progresso, quanto falta e estimativa ao ritmo atual.
- Variação mês a mês em barras (usa variação por registo enquanto houver menos de 3 meses).
- Evolução por tipologia desde o registo mais antigo do período (só para registos criados a partir da v2).

## Atualizar a app

Substitui o `index.html` e incrementa `CACHE` em `sw.js` (esta versão já está em `acervo-v2`) para forçar a atualização. Sobe também o `manifest.webmanifest` — sem ele o Chrome não oferece "Adicionar ao ecrã principal".
