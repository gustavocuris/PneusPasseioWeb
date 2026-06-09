# Persistencia online do painel

O painel de funcionario salva as alteracoes pela rota `/api/site-content`.
Os dados ficam no Cloudflare KV e sao carregados por todos os visitantes.

## Configuracao

1. Execute `npm run cloudflare:login`.
2. Execute `npm run deploy`.

O Wrangler cria automaticamente um KV exclusivo para o binding `SITE_CONTENT`
e registra o ID no `wrangler.jsonc`.

Depois, teste:

```txt
https://pneuspasseioweb.intercappneus.workers.dev/api/site-content
```

Antes do primeiro salvamento pode retornar `No saved content yet.`. Depois que o
funcionario salvar, a mesma configuracao sera carregada para todos os usuarios.
