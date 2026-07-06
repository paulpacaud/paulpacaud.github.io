# Run the website locally

Requires Docker. Run from the project root.

## First time only — install gems

```bash
docker run --rm -u "$(id -u):$(id -g)" -v "$PWD":/srv/jekyll \
  -e BUNDLE_PATH=/srv/jekyll/vendor/bundle \
  --entrypoint bundle jekyll/jekyll:latest install
```

## Serve

```bash
docker run --rm --name jekyll-serve \
  -u "$(id -u):$(id -g)" \
  -p 4000:4000 \
  -v "$PWD":/srv/jekyll \
  -e BUNDLE_PATH=/srv/jekyll/vendor/bundle \
  --entrypoint bundle \
  jekyll/jekyll:latest \
  exec jekyll serve --host 0.0.0.0 --watch --incremental
```

Open http://localhost:4000/ — auto-rebuilds on edits, stop with `Ctrl-C`.
