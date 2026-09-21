# Site: Dr. Flávio Toledo

Site institucional estático (HTML, CSS e JavaScript puros, sem build), servido por **nginx** via Docker.

## Estrutura
```
index.html          página única do site
assets/             favicon, ícone e imagens
Dockerfile          imagem nginx:alpine que serve o site na porta 80
nginx.conf          gzip, cache dos assets e cabeçalhos básicos
robots.txt
```

## Subir no GitHub
```bash
git init
git add .
git commit -m "Site Dr. Flávio Toledo"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/drflaviotoledo-site.git
git push -u origin main
```

## Publicar no Easypanel
1. No projeto: **+ Service → App**.
2. Em **Source**, escolha **GitHub** e selecione o repositório e a branch `main`.
3. Em **Build**, escolha **Dockerfile** (caminho: `Dockerfile`).
4. Clique em **Deploy**.
5. Em **Domains**, adicione o domínio e deixe a porta de destino em **80**. O Easypanel emite o HTTPS automaticamente.

A cada `git push` na `main`, basta clicar em **Deploy** de novo, ou ativar o **Auto Deploy** no Easypanel.

## Testar localmente (opcional)
```bash
docker build -t drflaviotoledo-site .
docker run --rm -p 8080:80 drflaviotoledo-site
```
Depois, abra http://localhost:8080.

## Pendências antes de ir ao ar
- Preencher o **RQE** (aparece como "RQE —" no `index.html`).
- Trocar as fotos provisórias pelas do ensaio novo (mantendo os mesmos nomes em `assets/img/`).
