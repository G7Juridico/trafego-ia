# Fluxo: criativos do Google Drive direto para o Meta

Validado em 2026-10-16 (AD029: imagem 1080x1350 entrou na biblioteca da conta pelo link lh3).

## Pré-requisitos
1. Conector Google Drive conectado no claude.ai (para listar pastas e pegar os IDs dos arquivos).
2. Arquivos compartilhados como **"Qualquer pessoa com o link — Leitor"**. O Meta baixa sem login; se a pasta virar privada, o upload falha.
3. Domínios `drive.google.com` e `drive.usercontent.google.com` liberados no ambiente — só para o copiloto baixar e conferir as peças. O Meta não depende disso.

## Passo a passo
1. Usuário manda o link da pasta.
2. Copiloto lista subpastas/arquivos pelo conector (IDs + nomes).
3. Copiloto baixa para pasta temporária (fora do git) e confere: abre, dimensões reais × nome, duplicatas, datas/prazos no texto da peça.
4. Upload no Meta: `ads_creative_upload_media` com `upload_source=URL`, `media_type=IMAGE`, `media_url=https://lh3.googleusercontent.com/d/<ID_DO_ARQUIVO>` → devolve `hash`; conferir width/height.
5. Criativo: `ads_create_creative` **com `image_hash`** (nunca `image_url` — gera ObjectStorySpecRedundant).
6. Anúncio: `ads_create_ad` com `{"creative_id": ...}` em rascunho; ler `active_errors` de cada um.
7. Releitura do rascunho + checklist → usuário decide publicar.

## O que NÃO funciona (testado)
- `https://drive.usercontent.google.com/download?id=...` como URL para o Meta → "Image Wasn't Downloaded … robots.txt".
- `image_url` direto no `ads_create_creative` → criativo com picture + image_hash → erro 1443051 no anúncio.
- 4:5 + 9:16 no mesmo anúncio (`placement_customizations`) → recurso não liberado no conector para esta conta.
- Upload local (`ads_creative_upload_local_image`) → em liberação gradual, indisponível para a conta.

## Não testado
- Vídeo: o link lh3 serve imagem. Vídeo do Drive precisa de outro caminho — testar quando houver.

## Padrão de pasta sugerido
`[MES] [VEN] [ADxxx] - Nome/` com `... - 1080x1350.png` e `... - 1080x1920.png`. Carrossel: `_01`, `_02` na ordem dos cartões.

## Vídeo (validado em 29/10/2026)
- Upload: `ads_creative_upload_media` com `media_type=VIDEO` e `media_url=https://drive.usercontent.google.com/download?id=<ID>&export=download&confirm=t` → video_id; aguardar status `ready` (`ads_get_ad_videos`).
- Capa: subir a imagem `picture` do vídeo como IMAGE (vem em 1080x1920) e usar **só `image_hash`** no criativo. `image_url` na capa gera erro 1443051 ObjectStorySpecRedundant no anúncio.
