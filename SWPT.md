# Sport Wales Project Template (SWPT)

Welcome to the Sport Wales Project Template - a comprehensive foundation for building React applications that align with Sport Wales' design system and development standards. This template combines Vite, React, Tailwind CSS, and our custom component library to help you build consistent, high-quality applications.

## Getting Started

### Prerequisites
Before you begin, ensure you have the following installed:
- Node.js (version 18 or higher)
- npm (comes with Node.js)
- Git for version control
- A code editor (we recommend VS Code)

### Creating Your Project

1. Clone the template:
```bash
git clone https://github.com/sportwales/SWPT.git your-project-name
cd your-project-name
```

2. Update project configuration:
   - Open `package.json` and update:
     ```json
     {
       "name": "your-project-name",
       "version": "0.0.1",
       // Keep other configurations as is
     }
     ```
   - Update the title in `index.html`
   - Remove the Git history and initialise a new repository:
     ```bash
     rm -rf .git
     git init
     ```

3. Install dependencies:
```bash
npm install
```

4. Start development:
```bash
npm run dev
```

## Project Architecture

### Directory Structure
```
your-project/
├── public/                    # Static assets
│   ├── sport_wales_logo_white.png
│   ├── sw_favicon.ico
│   └── vite.svg
├── src/
│   ├── components/           # React components
│   │   ├── component_library/  # Reusable UI components
│   │   ├── main/              # Core components
│   │   └── ui/                # Basic UI elements
│   ├── pages/                # Page components
│   ├── assets/               # Project assets
│   ├── data/                 # Data files
│   ├── styles/               # CSS styles
│   │   ├── index.css          # Main styles
│   │   └── custom/            # Custom styles
│   ├── utils/                # Utility functions
│   ├── App.jsx              # Main application
│   └── main.jsx             # Entry point
└── [Configuration Files]     # Various config files
```

### Key Features

#### 1. Styling System
The template uses a combination of Tailwind CSS and custom Sport Wales styles:
- Sport Wales brand colors (configured in `tailwind.config.js`)
- Custom components with consistent styling
- Responsive design utilities
- CSS variables for brand consistency

#### 2. Component Library
Located in `src/components/component_library/`:
- Pre-built components following Sport Wales design guidelines
- Form components with validation
- Layout components
- Interactive elements

#### 3. Bilingual Support
Built-in support for English and Welsh:
- Route-based language switching
- Language toggle component
- Structured content organisation

#### 4. Development Tools
- Hot Module Replacement with Vite
- ESLint configuration for code quality
- PostCSS for advanced CSS features
- Tailwind CSS for utility-first styling

## Customisation Guide

### Adding New Features

1. Page Components:
```jsx
// src/pages/YourNewPage.jsx
import React from 'react';
import { Layout } from '../components/Layout';

export function YourNewPage() {
  return (
    <Layout>
      <div className="sw-container">
        {/* Your content here */}
      </div>
    </Layout>
  );
}
```

2. Add the route in `App.jsx`:
```jsx
<Route path="/your-path" element={<YourNewPage />} />
```

### Styling Guidelines

1. Using Sport Wales classes:
```jsx
// Preferred approach using our utility classes
<button className="sw-button sw-button-primary">
  Click Me
</button>

// Custom styling when needed
<div className="sw-card custom-class">
  Content
</div>
```

2. Adding custom styles:
```css
/* src/styles/custom/styles.css */
.custom-class {
  /* Your styles here */
}
```

## Deployment Options

### Netlify Deployment

1. Configure `netlify.toml`:
```toml
[build]
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

2. Deploy:
   - Connect your GitHub repository to Netlify, or
   - Use Netlify CLI:
     ```bash
     npm install -g netlify-cli
     netlify deploy
     ```

### Railway Deployment

1. Configure `railway.toml`:
```toml
[build]
builder = "nixpacks"
buildCommand = "npm run build"

[deploy]
startCommand = "npm start"
healthcheckPath = "/"
```

2. Use Railway's GitHub integration or CLI for deployment.

### Docker Deployment

The template includes a production-ready Dockerfile:
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
COPY . .
RUN npm ci
RUN npm run build
EXPOSE $PORT
CMD ["npm", "start"]
```

Build and run:
```bash
docker build -t your-project-name .
docker run -p 3000:3000 your-project-name
```

## Development Workflow

1. Start development:
```bash
npm run dev
```

2. Build for production:
```bash
npm run build
```

3. Preview production build:
```bash
npm run preview
```

## Environment Variables

Create a `.env` file for environment variables:
```env
VITE_API_URL=your-api-url
VITE_OTHER_VAR=other-value
```

Remember: All variables must be prefixed with `VITE_`

## Best Practices

1. Component Organisation:
   - Place reusable components in `component_library`
   - Keep page-specific components in `pages`
   - Use the Layout component for consistent page structure

2. State Management:
   - Use React hooks for local state
   - Consider context for shared state
   - Keep state as close to where it's used as possible

3. Styling:
   - Use Sport Wales utility classes when available
   - Follow the component styling guidelines
   - Maintain responsive design principles

4. Performance:
   - Lazy load routes and heavy components
   - Optimise images and assets
   - Use appropriate caching strategies

## Support and Resources

- **Documentation**: Full Sport Wales design system documentation is available in the main repository
- **Support**: Contact the Sport Wales development team at [team-email]
- **Issues**: Raise issues in the GitHub repository
- **Updates**: Check the changelog for template updates

## License and Attribution

This project template is proprietary to Sport Wales. All rights reserved.

## Important Notes

- Always prefix environment variables with `VITE_`
- Use `npm run dev` for development
- The production build is in the `dist` directory
- Keep the Sport Wales design system documentation handy
- Follow the established coding standards and patterns

Need help? Contact the development team or raise an issue in the repository.
