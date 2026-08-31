# Rajat Sharma Portfolio

A production-ready personal portfolio for Rajat Sharma, a software developer and CMS specialist documenting his path toward AI engineering and AWS Solutions Architecture.

## Technology stack

- React
- TypeScript
- Vite
- Tailwind CSS
- Framer Motion
- Lucide React
- Local TypeScript data files

There is no database, authentication, paid service, or required backend in this first version.

## Run in Replit

Use the Replit Run button. It starts the managed `artifacts/rajat-sharma-portfolio: web` workflow:

```bash
pnpm --filter @workspace/rajat-sharma-portfolio run dev
```

The workflow injects `PORT` and `BASE_PATH`. The Vite server binds to `0.0.0.0` for the Replit preview.

For a manual local run:

```bash
PORT=22605 BASE_PATH=/ pnpm --filter @workspace/rajat-sharma-portfolio run dev
```

## Run locally

```bash
pnpm install
pnpm --filter @workspace/rajat-sharma-portfolio run dev
```

## Edit personal information

Most copy is in `src/App.tsx`. Update the name, title, introduction, about copy, experience, contact details, social URLs, and footer there. The current profile identifies Altudo as the employer for the current Software Developer experience and deliberately separates professional CMS experience from AI Engineering, AWS Solutions Architecture, data structures, and system design areas that are still developing.

The supplied contact details are currently configured as:

- Work email: `rajatsharma1401@outlook.com`
- GitHub: `https://github.com/Rajatsharma14/Rajatsharma14`
- LinkedIn: `https://linkedin.com/in/rajat-sharma-460872148/`

To change them later, edit `CONTACT_EMAIL`, `GITHUB_URL`, and `LINKEDIN_URL` near the top of `src/App.tsx`.

## Update skills

The grouped skill cards are in `src/App.tsx`. Edit the `items` arrays in the section with the `skills` anchor. Developing areas are marked with `Currently learning`.

## Update projects

Edit `src/data/projects.ts`. Each project supports:

- title and category
- Professional, CMS, or Personal category and label
- high-level description and contribution
- technology stack and highlights
- an abstract visual identifier
- optional live, GitHub, and case-study URLs

Confidential professional work should remain high-level. Link buttons only render when a URL is supplied.

The current personal project, `Money Lens`, is linked through its `liveUrl`. Replace that URL in `src/data/projects.ts` if the project moves.

## Update the learning roadmap

Edit `src/data/roadmap.ts`. Each roadmap item has a track, title, description, tags, and one of three honest states: `Completed`, `In progress`, or `Planned`.

## Add the résumé

Upload the real file as `public/resume/rajat-sharma-resume.pdf`, then restore the résumé links in `src/App.tsx`. See `public/resume/README.md`.

## Contact form

The form uses a transparent no-backend flow. Submitting prepares a prefilled `mailto:` message using `CONTACT_EMAIL`. The email link in the contact section uses the same value.

## Remaining optional details to provide before launch

- `[PROFILE PHOTO]` (optional; no photo slot is active until an approved image is supplied)
- `[RESUME PDF]`
- `[COLLEGE NAME]`
- `[CERTIFICATIONS]` (only if applicable)
- `[MEASURABLE ACHIEVEMENTS]` (only verified outcomes)

The résumé, college, certifications, and achievement fields remain intentionally unfilled rather than being invented. Add only verified, public, non-confidential information.

## Prepare and deploy with Replit

This is a frontend-only React SPA and is configured for a **Static** Replit deployment:

- Build command: `pnpm --filter @workspace/rajat-sharma-portfolio run build`
- Published files: `artifacts/rajat-sharma-portfolio/dist/public`
- SPA rewrite: all paths serve `index.html`
- Required secrets: none
- Runtime server: none after the static files are built

Validate the production build with the managed environment:

```bash
PORT=22605 BASE_PATH=/ pnpm --filter @workspace/rajat-sharma-portfolio run build
```

To publish, open Replit's Publish tool, confirm the Static target and the configuration above, then click Publish. Publishing is user-initiated; review the current Replit plan and usage estimate in that tool because charges may apply depending on the account and deployment usage.

There is no lint script or ESLint configuration in this workspace. TypeScript and the production build are the required automated checks currently available. Prettier can be run as a formatting audit:

```bash
pnpm exec prettier --check artifacts/rajat-sharma-portfolio/src/App.tsx artifacts/rajat-sharma-portfolio/src/data/projects.ts artifacts/rajat-sharma-portfolio/src/data/roadmap.ts artifacts/rajat-sharma-portfolio/src/index.css artifacts/rajat-sharma-portfolio/index.html
```

## Export to GitHub

Create a repository on GitHub, then from the project root:

```bash
git init
git add .
git commit -m "Build Rajat Sharma portfolio"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

## Deploy to Vercel

Import the GitHub repository into Vercel. Use:

- Framework preset: Vite
- Build command: `pnpm --filter @workspace/rajat-sharma-portfolio run build`
- Output directory: `artifacts/rajat-sharma-portfolio/dist/public`

For a standalone Vercel project, set `PORT` and `BASE_PATH` for the build if your build environment does not provide them. A typical value is `BASE_PATH=/`.