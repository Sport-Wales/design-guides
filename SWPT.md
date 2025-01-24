# Sport Wales Project Template (SWPT)

A React-based website built with Vite, Tailwind CSS, and deployed on Netlify.

## Quick Start

### Prerequisites
- Node.js installed on your machine
- npm (comes with Node.js)
- Git for version control

### Setup Steps

1. Create a new Vite project:
```bash
npm create vite@latest crowdfunder_cal -- --template react
cd crowdfunder_cal
```

2. Install dependencies:
```bash
npm install react-router-dom @headlessui/react lucide-react @fortawesome/fontawesome-free
npm install -D tailwindcss postcss autoprefixer
```

3. Initialize Tailwind CSS:
```bash
npx tailwindcss init -p
```

## Project Structure
```
project_template/
├── public/              # Static assets that need to be served as-is
│   └── favicon.svg
├── src/
│   ├── components/     
│   │   ├── main/       # Main components (Header, Footer, etc.)
│   │   └── ui/         # Reusable UI components
│   ├── pages/          # Page components
│   ├── assets/         # Images, icons, etc.
│   ├── data/          # JSON data files
│   ├── styles/        # CSS files
│   │   └── index.css  # Global styles
│   ├── utils/         # Helper functions
│   ├── App.jsx        # Main App component
│   ├── main.jsx       # Entry point
│
├── index.html          # Entry HTML file
├── package.json        # Project dependencies and scripts
├── vite.config.js      # Vite configuration
├── postcss.config.js   # PostCSS configuration
├── tailwind.config.js  # Tailwind configuration
└── README.md          # Project documentation
```

## Configuration Files

### vite.config.js
```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  server: {
    port: 3000
  }
})
```

### tailwind.config.js
```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### package.json Scripts
```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  }
}
```

### Add to index.html
```html
<link 
  rel="stylesheet" 
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" 
/>
```

### Add to src/index.css
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Available Scripts

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build locally
npm run preview
```

## Deployment

### Deploy to Netlify:

1. Update netlify.toml for Vite:
```toml
[build]
  command = "npm run build"
  publish = "dist"    # Vite uses 'dist' instead of 'build'

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

2. Deploy options:
   - Connect your GitHub repository to Netlify for automatic deployments
   - Or use Netlify CLI:
```bash
npm install -g netlify-cli
netlify deploy
```

## Features
- Vite for faster development and builds
- React Router for navigation
- Tailwind CSS for styling
- Font Awesome icons
- HeadlessUI components
- Production-ready configuration
- Netlify deployment setup

## License
This project is licensed under the MIT License.

## Support
For support, email [your-email] or raise an issue in the repository.

## Important Notes
- Vite uses `dist` instead of `build` for production builds
- Use `npm run dev` for development (not `npm start`)
- Environment variables in Vite must be prefixed with `VITE_`
