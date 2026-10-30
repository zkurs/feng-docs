# Feng documentation

This repository contains Feng's public documentation source. The live documentation remains part of the main Feng Railway service so every page is available under `https://feng.up.railway.app/docs` without an iframe, a second paid host, or fragile reverse-proxy rewriting.

## Production architecture

- Source and navigation: this repository.
- Production renderer and route integration: [`zkurs/feng-by-zkur`](https://github.com/zkurs/feng-by-zkur).
- Live entry point: <https://feng.up.railway.app/docs>.
- Live article example: <https://feng.up.railway.app/docs/overview/introduction>.

The main service owns `/docs` and every nested documentation route. This preserves the existing domain, deep-link refreshes, anchors, search, Feng's animated starfield, and the site's other public routes.

## Writing rules

- Document only behavior verified in Feng's source.
- Use Feng's default prefix `,` in command examples.
- Keep headings short and sentence case.
- Explain Discord permissions and role hierarchy where they matter.
- Never publish tokens, client secrets, private transcript URLs, or internal owner-only commands.

## Updating production

1. Edit and review the MDX source here.
2. Apply the matching content change to the docs catalog in the main Feng repository.
3. Run the Python and browser tests in the main repository.
4. Merge the main repository pull request. Railway deploys that merge automatically.

This explicit reviewed sync is intentional until a cross-repository deployment credential is configured. Do not run `mint dev` or depend on a local machine for production.
