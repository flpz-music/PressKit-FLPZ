# FLPZ — Electronic Press Kit

Site estático (HTML/CSS/JS, **sem build**) com identidade azul, carrossel animado, sequência de vídeos e booking pelo WhatsApp **+55 86 99455-6828**.

## Fluxo de trabalho

1. Crie uma branch a partir da `main` e faça as alterações (pode ser direto pelo GitHub).
2. A Vercel gera automaticamente uma **URL de prévia** para cada branch / pull request.
3. Após aprovação, faça o merge na `main`: a Vercel publica em produção automaticamente.

## Estrutura

```
index.html            página completa (conteúdo, estilos e interações)
vercel.json           URLs limpas, cache e cabeçalhos de segurança
assets/
  fotos/              fotografias em WebP (DSC*.webp + versões -720 para celular)
  videos/             teasers MP4 sem áudio (8 s) + pôsteres WebP
  og/flpz-og.jpg      imagem de compartilhamento (WhatsApp / Instagram), 1200×630
```

## Onde editar

| O quê | Onde |
|---|---|
| WhatsApp / mensagem de booking | procure `wa.me/5586994556828` em `index.html` (3 botões: cabeçalho, Press Material e Booking) |
| Textos e legendas do carrossel | array `slides` no script no final de `index.html` |
| Fotos do carrossel / abertura | `assets/fotos/` (mantenha os nomes ou ajuste `slides` e o `<img>` da abertura) |
| Vídeos da seção Experiência | array `clips` no script; arquivos em `assets/videos/` |
| Paleta | bloco `FLPZ PREMIUM 2026` no CSS (`--bg`, `--blue-deep`, `--blue-2`, `--blue`, `--blue-soft`) |
| Imagem de compartilhamento | `assets/og/flpz-og.jpg` e as metas `og:image` / `twitter:image` |

## Comportamento dos vídeos

- Apenas o clipe ativo e o próximo são carregados; os demais só entram na vez.
- Reprodução silenciosa e automática, em loop de sequência, com transição suave.
- Pausam fora da tela e com a aba em segundo plano.
- Com `prefers-reduced-motion`, economia de dados ou conexão 2G, aparece só o pôster estático.
- Os arquivos são trechos de 8 s; não representam os vídeos integrais.

## Antes do lançamento

Confirme direitos de uso das imagens e vídeos. Os sets WAV não são incorporados (arquivos grandes demais para servir direto na web).
