# Production Release Plan

## Branch model

- `main` is production-only.
- `develop` is the integration branch for ongoing work.
- Feature work should live in short-lived branches created from `develop`.

Suggested flow:

1. `feature/*` branches merge into `develop`.
2. `develop` is deployed to a preview environment.
3. When ready, `develop` is merged into `main`.
4. `main` triggers production deploy.

## Simple GitHub / Vercel flow

Use this lightweight setup for the first release:

1. Create `feature/*` branches from `develop`.
2. Merge finished work into `develop` and let Vercel preview that branch.
3. When the release is ready, merge `develop` into `main`.
4. Let Vercel deploy `main` to production.
5. Tag the release on `main` if you want a simple rollback point.

Recommended branch mapping:

- GitHub: `main` for production, `develop` for integration, `feature/*` for tasks.
- Vercel: connect the repo once, then set `main` as Production and `develop` as Preview.

## Release rules

- Only polished, reviewed changes reach `main`.
- Keep production deploys small and reversible.
- Use one release commit or merge per deploy if possible.
- Prefer content and layout changes in separate PRs when practical.

## First production release checklist

- [ ] Finalize hero copy and section labels.
- [ ] Verify all external links open correctly.
- [ ] Check mobile spacing and ticker behavior.
- [ ] Confirm the latest updates section is current.
- [ ] Review footer, contact email, and navigation anchors.
- [ ] Test the site in at least one desktop and one mobile viewport.
- [ ] Make sure refresh always lands on the hero.
- [ ] Remove any temporary debug code before release.

## Deployment mapping

Use branch-based deploys if the platform supports them:

- Vercel: `main` -> Production, `develop` -> Preview
- Netlify: `main` -> Production, `develop` -> Deploy Preview or branch deploy
- GitHub Pages: publish from `main`

## Rollback

If production needs to be reverted:

1. Revert the release commit on `main`.
2. Redeploy `main`.
3. Verify the homepage and all anchors.

## Definition of done

The first production release is done when:

- the homepage loads cleanly on refresh,
- the branch model is in place,
- the production deploy path is documented,
- the content and layout are stable enough for public traffic.
