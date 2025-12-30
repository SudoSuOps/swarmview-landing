# SwarmView Landing Page

Medical AI, executed locally. Proven cryptographically.

## Tech Stack

- Vite (static build)
- Tailwind CSS v4
- No tracking, no cookies, no analytics

## Development

```bash
npm install
npm run dev
```

Open http://localhost:5173

## Build

```bash
npm run build
```

Output: `./dist/`

## Deploy to Cloudflare Pages

### Option 1: Git Integration (Recommended)

1. Push repo to GitHub/GitLab
2. Go to Cloudflare Dashboard → Pages → Create a project
3. Connect your repository
4. Configure build settings:
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
   - **Root directory:** `/` (or path to this folder if monorepo)
5. Deploy

### Option 2: Direct Upload

```bash
npm run build
npx wrangler pages deploy dist --project-name=swarmview
```

### Option 3: CLI from scratch

```bash
# Install Wrangler if needed
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Create project and deploy
wrangler pages project create swarmview
wrangler pages deploy dist --project-name=swarmview
```

## Custom Domain

After deployment:
1. Go to Cloudflare Pages → swarmview → Custom domains
2. Add `swarmview.io`
3. Update DNS records as prompted

## Structure

```
swarmview-landing/
├── index.html          # Main landing page
├── src/
│   └── style.css       # Tailwind + custom styles
├── public/
│   └── favicon.svg     # Logo
├── vite.config.js      # Vite config
├── tailwind.config.js  # Tailwind config
├── postcss.config.js   # PostCSS config
└── package.json
```

## Customization

- **Colors:** Edit `tailwind.config.js` → `theme.extend.colors`
- **Fonts:** Update Google Fonts import in `src/style.css`
- **Content:** Edit `index.html` directly
- **Links:** Replace placeholder `href="#"` with actual URLs

## No Tracking

This site:
- Sets no cookies
- Loads no external analytics
- Makes no tracking requests
- Uses only self-hosted fonts (via Google Fonts CDN)

Privacy statement is in the footer.

---

Built on SwarmVision Protocol.
