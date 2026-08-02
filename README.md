# ac-webpages

Repositório de deploy das landing pages de Ana Clara Bastos.

Vercel detecta pushes na branch `main` e deploya automaticamente em `lp.anaclarabastos.com.br`.

---

## Mapeamento de páginas

| Diretório no repo (`public/`) | Working copy local (`AC | Webpages/`) | URL ao vivo |
|---|---|---|
| `v11/` | *(template base)* | `/v11/` |
| `v11-2608/` | `L2608 \| Página de Captura v11 (Clone v1)` | `/v11-2608/` |
| `cadastro-realizado-2608/` | `L2608 \| Página de Obrigado` | `/cadastro-realizado-2608/` |

---

## Fluxo de deploy

1. Editar o arquivo na **working copy** local (`AC | Webpages/...`)
2. Copiar para o diretório correspondente em `public/`
3. Commitar e fazer push na `main`

```bash
# Exemplo — atualizar a página de captura L2608
cp "AC | Webpages/L2608 | Página de Captura v11 (Clone v1)/index.html" \
   public/v11-2608/index.html

git add public/v11-2608/index.html
git commit -m "feat: descrição da mudança [L2608]"
git push origin main
```

Deploy leva ~1-2 minutos após o push.

---

## Convenções

- Nomenclatura de diretórios: `v{versao}-{data}` (ex: `v11-2608`)
- Mensagens de commit: conventional commits com tag do evento no final (ex: `[L2608]`)
- **Não usar** `vercel link` ou `vercel --prod` — deploy exclusivamente via GitHub push
