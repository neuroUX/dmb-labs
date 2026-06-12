# DMB Labs Static Site

Minimal static structure for a product studio landing page with room to grow.

## Project structure

```
.
├── index.html
├── README.md
├── assets
│   ├── css
│   │   └── main.css
│   └── images
│       └── .gitkeep
├── docs
│   └── production-release.md
├── data
│   └── site.json
```

## Notes

- Keep `index.html` as the studio landing page.
- Keep copy and product metadata in `data/site.json`.
- Put logos and images in `assets/images/`.

## Deploy

Works directly with static hosting:
- Vercel
- Netlify
- GitHub Pages

## Release workflow

For the first production release, use two branches:

- `develop` for active work and preview deploys
- `main` for production-only releases

Recommended flow:

1. Work on feature branches from `develop`.
2. Merge finished work into `develop` and verify in preview.
3. Merge `develop` into `main` when ready to ship.
4. Deploy `main` to production.

See [docs/production-release.md](docs/production-release.md) for the full checklist.
