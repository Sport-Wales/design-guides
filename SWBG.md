
# Sport Wales Brand Guidelines - Core Elements

## Brand Colors

### Primary Colors

1. **Sport Wales Red**
   - RGB: 227, 36, 52
   - HEX: `#E32434`
   - CMYK: 22/95/77/0

2. **Sport Wales Yellow**
   - RGB: 77, 17, 78
   - HEX: `#F6B207`
   - CMYK: 2/34/95/0

3. **Sport Wales Blue**
   - RGB: 22, 75, 100
   - HEX: `#164B64`
   - CMYK: 77/31/13/61

4. **Sport Wales Green**
   - RGB: 41, 157, 145
   - HEX: `#299D91`
   - CMYK: 78/17/49/1

## Typography

### Primary Font: Objektiv MK1
- XBold: Primary headlines
- Bold: Sub-heads and calls to action
- Regular: Body copy

### Fallback Font: Montserrat
- Extra Bold: Primary headlines
- Semi Bold: Sub-heads and calls to action
- Regular: Body copy

### System Fallback
- Arial Bold: Headlines
- Arial Regular: Body copy

### Font Styles
#### Headlines
- Sentence case with full stop
- Leading: 100-120%
- Tracking: -10pt to 10pt

#### Body Copy
- Leading: 110-140% of type size
- Line length: 45-90 characters
- Full line breaks between paragraphs

### Font Face Declarations
```css
@font-face {
  font-family: 'Objektiv MK1';
  src: url('/fonts/ObjektivMk1-Regular.woff2') format('woff2');
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}

@font-face {
  font-family: 'Objektiv MK1';
  src: url('/fonts/ObjektivMk1-Bold.woff2') format('woff2');
  font-weight: 700;
  font-style: normal;
  font-display: swap;
}

@font-face {
  font-family: 'Objektiv MK1';
  src: url('/fonts/ObjektivMk1-XBold.woff2') format('woff2');
  font-weight: 800;
  font-style: normal;
  font-display: swap;
}
```


## Layout & Spacing

### Margins
- Small: 5% (social media, web banners)
- Large: 10% (Out of Home advertising)

### Column System
- Divisible by 3 (3, 6, 9, or 12 columns)
- Gutters: Half the margin width
  - Example: 5% margin = 2.5% gutters

### Logo Spacing
- Minimum clear space: Equal to height of 'y' character in logo

## UI Elements

### Buttons
- Corner radius: 8px
- Height: 46px



## Core Setup

### Tailwind Directives
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## CSS Global/Root Variables Implementation

```css
:root {
  /* Primary Brand Colors */
  --color-sw-red: #E32434;
  --color-sw-yellow: #F6B207;
  --color-sw-blue: #164B64;
  --color-sw-green: #299D91;

  /* Neutral Colors */
  --color-black: #000000;
  --color-grey: #BFBEC5;
  --color-light-grey: #F4F5F7;
  --color-white: #FFFFFF;

  /* Primary Brand Colors Accent */
  --color-sw-red-light: #F7BDC2;
  --color-sw-yellow-light: #FFFFB7;
  --color-sw-blue-light: #6CD0FF;
  --color-sw-green-light: #97E9E1;
  --color-sw-red-dark: #8E0A0A;
  --color-sw-yellow-dark: #A77B00;
  --color-sw-blue-dark: #001830;
  --color-sw-green-dark: #005D53;

  /* Typography - Font Families */
  --font-primary: 'Objektiv MK1', sans-serif;
  --font-fallback: 'Montserrat', sans-serif;
  --font-system: 'Arial', sans-serif;

  /* Font Weights */
  --font-weight-regular: 400;
  --font-weight-bold: 700;
  --font-weight-xbold: 800;

  /* Font Sizes */
  --font-size-body: 16px;
  --font-size-label: 20px;
  --font-size-head: 24px;
  --font-size-subhead: 20px;
  --font-size-hero: 95px;

  /* Line Heights */
  --line-height-tight: 100%;
  --line-height-normal: 110%;
  --line-height-relaxed: 130%;

  /* Spacing & Layout */
  --margin-small: 5%;
  --margin-large: 10%;
  --gutter-width: calc(var(--margin-small) / 2);

  /* Border Radius */
  --border-radius-button: 8px;

  /* Component Specific */
  --button-height: 46px;
  --button-padding: 1rem 2rem;

  /* Layout */
  --logo-min-width: 160px;
  --clear-space-logo: 1em;

  /* Transitions */
  --transition-default: 0.3s ease-in-out;

  /* Opacity */
  --overlay-light: 75%;
  --overlay-dark: 90%;

}

```



### Base Styles

```css
@layer base {
  body {
    font-family: var(--font-primary);
    font-size: var(--font-size-body);
    line-height: var(--line-height-normal);
  }

  h1, h2, h3, h4, h5, h6 {
    font-weight: var(--font-weight-xbold);
    line-height: var(--line-height-tight);
  }
}
```

## Layout Components

### Container System
```css
.sw-container {
  @apply max-w-5xl mx-auto;
}
```

### Card System
```css
.sw-card {
  border-radius: var(--border-radius-button);
  background-color: var(--color-white);
  padding: 1.5rem;
}
```

### Grid System TW 
Standard grid layout tailwind:
```html
<div class="grid grid-cols-1 lg:grid-cols-3 gap-6 p-8">
  <!-- Main Content -->
  <div class="lg:col-span-2 space-y-8">
    <!-- Content here -->
  </div>
  
  <!-- Sidebar -->
  <div class="lg:col-span-1 space-y-6">
    <!-- Sidebar content -->
  </div>
</div>
```

## Component Library

### Header Component
```css
.sw-header {
  @apply sw-bg-red text-white p-6;
}
```

### Typography Components
```css
.sw-heading-primary {
  @apply text-3xl font-extrabold leading-tight;
  font-family: var(--font-fallback);
}

.sw-heading-secondary {
  @apply text-xl font-bold mb-3;
  font-family: var(--font-fallback);
}
```

### Form Components

#### Labels
```css
.sw-label {
  @apply text-lg font-semibold;
  color: var(--color-sw-blue);
}
```

#### Inputs
```css
.sw-input {
  height: var(--button-height);
  border-radius: var(--border-radius-button);
  padding: 0 1rem;
  border: 1px solid var(--color-grey);
}
```

#### Checkboxes
```css
.sw-checkbox {
  @apply w-5 h-5 rounded border-2 focus:ring-2;
  border-color: var(--color-sw-blue);
  color: var(--color-sw-red);
}
```

### Button System

#### Base Button
```css
.sw-button {
  height: var(--button-height);
  padding: var(--button-padding);
  border-radius: var(--border-radius-button);
  font-weight: var(--font-weight-bold);
  transition: all 0.3s ease-in-out;
}
```

#### Button Variants
```css
.sw-button-primary {
  @apply sw-bg-red text-white hover:opacity-90;
}

.sw-button-secondary {
  @apply sw-bg-blue text-white hover:opacity-90;
}

.mode-toggle-button {
  @apply sw-button flex-1 min-h-[56px] px-8 text-xs font-semibold tracking-wide transition-all;
  
  &.active {
    @apply sw-button-primary shadow-lg scale-105;
  }
  
  &.inactive {
    @apply bg-white border-2 border-[--color-sw-red] text-[--color-sw-red] hover:sw-bg-red hover:text-white hover:scale-102;
  }
}
```

### Content Display Components

#### Notice Box
```css
.sw-notice {
  @apply p-4 rounded-lg;
  background-color: rgba(246, 178, 7, 0.1);
  border-left: 4px solid var(--color-sw-yellow);
}
```

#### Results Display
```css
.sw-results {
  @apply p-6 rounded-lg space-y-4;
  background-color: var(--color-sw-blue);
  color: var(--color-white);
}
```

#### Highlight Box
```css
.sw-highlight {
  @apply p-4 rounded-lg;
  background-color: var(--color-sw-green);
  color: var(--color-white);
}
```

#### Sidebar Card
```css
.sw-sidebar-card {
  @apply p-6 rounded-lg;
  background-color: var(--color-light-grey);
}
```

## Utility Classes

### Brand Color Utilities
```css
@layer utilities {
  .sw-text-red {
    color: var(--color-sw-red);
  }
  .sw-bg-red {
    background-color: var(--color-sw-red);
  }
  .sw-text-blue {
    color: var(--color-sw-blue);
  }
  .sw-bg-blue {
    background-color: var(--color-sw-blue);
  }
  .sw-text-yellow {
    color: var(--color-sw-yellow);
  }
  .sw-bg-yellow {
    background-color: var(--color-sw-yellow);
  }
  .sw-text-green {
    color: var(--color-sw-green);
  }
  .sw-bg-green {
    background-color: var(--color-sw-green);
  }
}
```

## Responsive Design

### Breakpoints
- Default: Mobile-first approach
- Small (sm): 640px
- Large (lg): 1024px

### Common Responsive Patterns
```css
/* Mode Toggle */
.flex-col sm:flex-row

/* Grid Layout */
.grid-cols-1 lg:grid-cols-3

/* Content Spans */
.lg:col-span-2
```

## Implementation Examples

### Basic Page Structure
```jsx
<div className="sw-container sw-card">
  {/* Header */}
  <div className="sw-header">
    <h2 className="sw-heading-primary">Page Title</h2>
    <p className="mt-2 text-lg">Page description</p>
  </div>

  {/* Main Content */}
  <div className="grid grid-cols-1 lg:grid-cols-3 gap-6 p-8">
    <div className="lg:col-span-2 space-y-8">
      {/* Main content here */}
    </div>
    <div className="lg:col-span-1 space-y-6">
      {/* Sidebar content here */}
    </div>
  </div>
</div>
```

### Form Group Example
```jsx
<div className="space-y-4">
  <label className="sw-label">
    Field Label
  </label>
  <input 
    className="sw-input w-full" 
    placeholder="Enter value"
  />
  {error && (
    <div className="sw-notice text-[--color-sw-red]">
      <p className="font-semibold">{error}</p>
    </div>
  )}
</div>
```

### Results Display Example
```jsx
<div className="sw-results">
  <h3 className="sw-heading-secondary text-white">
    Results Section
  </h3>
  <div className="sw-highlight">
    <p className="text-lg">
      <span className="font-bold">Label:</span>
      <span className="text-2xl ml-2">Value</span>
    </p>
  </div>
</div>
```
