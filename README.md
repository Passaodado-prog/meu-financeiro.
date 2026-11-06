# Meu Financeiro - PWA para GitHub Pages

Este pacote ja esta preparado para publicacao no GitHub Pages e instalacao como aplicativo (PWA).

## Arquivos

- `index.html`: aplicacao Meu Financeiro.
- `manifest.webmanifest`: nome, icones e configuracao de instalacao.
- `service-worker.js`: cache do aplicativo para abertura offline e atualizacao do shell.
- `icons/`: icones Android, iOS e navegadores.

## Publicar no GitHub Pages

1. Entre em https://github.com e crie um repositorio, por exemplo `meu-financeiro`.
2. Extraia este ZIP no computador.
3. Envie **o conteudo** da pasta `meu-financeiro-pwa` para a raiz do repositorio. O `index.html` precisa ficar na raiz, ao lado de `manifest.webmanifest` e `service-worker.js`.
4. No repositorio, abra `Settings` > `Pages`.
5. Em `Build and deployment`, escolha `Deploy from a branch`.
6. Selecione a branch `main` e a pasta `/ (root)`, depois clique em `Save`.
7. Aguarde a publicacao e abra o endereco indicado pelo GitHub, normalmente `https://SEU-USUARIO.github.io/meu-financeiro/`.

Nao envie apenas o arquivo ZIP para a raiz: primeiro extraia o ZIP e envie os arquivos e a pasta `icons`.

## Instalar no celular

### Android

1. Abra o endereco publicado no Google Chrome.
2. Toque em `Instalar app` dentro do Meu Financeiro ou abra o menu de tres pontos do Chrome.
3. Escolha `Instalar app` / `Adicionar a tela inicial` e confirme.

### iPhone / iPad

1. Abra o endereco publicado no Safari.
2. Toque em `Compartilhar`.
3. Escolha `Adicionar a Tela de Inicio` e confirme.

## Atualizar o aplicativo depois de alterar o codigo

1. Substitua os arquivos no repositorio e faca commit.
2. Quando alterar o `service-worker.js` ou os arquivos do shell, incremente o identificador `CACHE_NAME` (por exemplo, de `v1` para `v2`).
3. Abra o site com internet. O navegador baixara a nova versao do shell; feche e reabra o PWA se a versao antiga ainda estiver aberta.

## Dados e privacidade

- O GitHub Pages hospeda apenas os arquivos do aplicativo. Os lancamentos, investimentos e comprovantes continuam armazenados localmente no navegador/dispositivo, em `localStorage` e `IndexedDB`.
- Nao existe sincronizacao automatica entre celular e computador. Para transferir dados entre dispositivos, use `Backup` e importe o JSON no outro dispositivo.
- A instalacao a partir do GitHub Pages usa uma origem diferente do arquivo HTML aberto localmente. Dados salvos anteriormente em `file://` nao aparecem automaticamente no site publicado; use o backup para migrar dados, se houver.
- O service worker armazena os arquivos do aplicativo para permitir abrir a interface sem internet. O primeiro acesso e a primeira instalacao exigem internet.
- A senha da aba Investimentos e as respostas de recuperacao continuam vinculadas ao armazenamento local daquele dispositivo; nao sao sincronizadas pelo GitHub.
- O codigo publicado em um repositorio publico pode ser visto por qualquer pessoa. Nao coloque senhas, tokens ou dados bancarios no codigo.

## Observacoes tecnicas

- O PWA precisa ser acessado por HTTPS. O GitHub Pages fornece HTTPS.
- O escopo do manifest e do service worker e relativo (`./`), portanto funciona tanto em dominio raiz quanto em URL de projeto do GitHub Pages.
- Os dados financeiros nao sao enviados ao GitHub Pages pelo aplicativo.
