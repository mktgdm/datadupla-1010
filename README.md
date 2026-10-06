# Data Dupla 10/10 — Grupo DM

Landing page da campanha Esquenta 10/10 / Data Dupla da Dermomed.
Arquivo único: HTML, CSS, JavaScript, imagens e vídeo estão todos
dentro do `index.html`. Não precisa instalar nada nem rodar build.

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | A landing page inteira |
| `CNAME` | Domínio próprio: `datadupla.dermomed.com.br` |
| `.nojekyll` | Impede o GitHub de processar a pasta e quebrar arquivos |
| `404.html` | Página de erro que manda o visitante para a home |
| `robots.txt` | Libera a indexação e aponta o sitemap |
| `sitemap.xml` | Endereço da página para o Google |

## Publicar no GitHub Pages

1. Crie um repositório novo (pode ser público ou privado; com conta
   gratuita, o Pages só funciona em repositório público).
2. Envie todos estes arquivos para a raiz do repositório, na branch
   `main`. Pelo site: **Add file > Upload files**, arraste tudo e
   confirme com **Commit changes**.
   O arquivo `.nojekyll` começa com ponto; se o navegador não deixar
   arrastá-lo, crie pelo **Add file > Create new file**, com o nome
   `.nojekyll` e conteúdo vazio.
3. Vá em **Settings > Pages**.
4. Em **Source**, escolha **Deploy from a branch**; em **Branch**,
   escolha `main` e a pasta `/ (root)`. Salve.
5. Aguarde de 1 a 2 minutos. O endereço provisório aparece no topo
   dessa mesma tela, no formato `https://<usuario>.github.io/<repo>/`.

## Domínio próprio (datadupla.dermomed.com.br)

1. No painel de DNS do domínio dermomed.com.br, crie um registro:
   - Tipo: `CNAME`
   - Nome/host: `datadupla`
   - Valor/destino: `<usuario>.github.io.` (o seu usuário do GitHub)
   - TTL: o padrão
2. Em **Settings > Pages > Custom domain**, confirme que aparece
   `datadupla.dermomed.com.br` (o arquivo CNAME já faz isso).
3. Marque **Enforce HTTPS** assim que a opção ficar disponível. O
   certificado leva de alguns minutos até algumas horas para sair.

Se o domínio for apontado para outro usuário do GitHub, troque o
destino do CNAME. Se a landing for ficar em outro endereço, edite o
arquivo `CNAME`, o `robots.txt` e o `sitemap.xml`.

## Tags do Google

No topo do `index.html` existe esta linha:

```js
window.DD10_TAGS = { GTM:'', GA4:'', ADS:'', ADS_LABEL:'' };
```

Preencha o que for usar:

- `GTM` — container do Tag Manager (`GTM-XXXXXXX`)
- `GA4` — medida do Analytics (`G-XXXXXXXXXX`)
- `ADS` — conta do Google Ads (`AW-123456789`)
- `ADS_LABEL` — rótulo de conversão (`AW-123456789/AbC-D_efGh`)

Com tudo vazio, a página não chama nada do Google. O recomendado é
preencher só o `GTM` e configurar GA4 e Ads dentro do Tag Manager.

Eventos enviados ao dataLayer: `dd10_cta_hero`, `dd10_banner_click`,
`dd10_vitrine_produto`, `dd10_produto_eu_quero`, `dd10_quiz_resultado`,
`dd10_video_akmed`, `dd10_whatsapp`, entre outros.

## Outros ajustes no index.html

Todos no bloco `<script>`, no fim do arquivo:

- `CONFIG` — WhatsApp e mensagem padrão
- `BANNERS` — os 6 banners do carrossel (imagem, link, descrição)
- `BN_INTERVAL` — tempo de troca do carrossel (5000 = 5 segundos)
- `CD_START` / `CD_END` — início e fim da Data Dupla
- `P` — os 25 produtos, com preços e links
- `TOP10` — quais produtos entram nas 10 ofertas
- `HERO_ARTS` — as 6 artes da vitrine do topo
- `QUIZ` — as 4 perguntas da autoavaliação

A página vira sozinha para o modo 10/10 à meia-noite de 10 de outubro,
horário de Brasília: trocam os selos, o texto do topo e o cronômetro.

## Pendências

- Versões dos banners para celular (1080 x 1080 px)
- Links próprios de cada banner (hoje apontam para seções da página)
- Preços dos banners de gel e de membranas não batem com os cards
- Preços do dia 10/10
