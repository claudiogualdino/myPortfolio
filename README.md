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
- Cada edição grava automaticamente o total do dia no histórico (um registo por dia).

## Atualizar a app

Substitui o `index.html` e incrementa `CACHE` em `sw.js` (ex. `acervo-v2`) para forçar a atualização.
