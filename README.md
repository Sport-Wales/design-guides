# Sport Wales Design Guides

## Overview
This repository contains the official design and development documentation for Sport Wales digital products. These guides provide a comprehensive set of tools, components, and guidelines to ensure consistency across all Sport Wales digital platforms.

## Repository Structure
```
sport-wales-design-guides/
├── docs/
│   └── SWBG.md           # Sport Wales Brand Guidelines
│   └── SWCF.md           # Sport Wales Component Functionality
│   └── SWGS.md           # Sport Wales Global Style Sheet
│   └── SWPT.md           # Sport Wales Project Template
├── examples/             # Example implementations
├── assets/              # Design assets and resources
└── README.md            # This file
```

## Simple Explanation 

### SWBG - Brand Guidelines
The Sport Wales Brand Guidelines define our visual identity including:
- Color palette and usage
- Typography system
- Layout principles
- Component design specifications
- UI Elements

[View Brand Guidelines →](./docs/SWBG.md)

### SWCF - Component Functionality
Technical documentation for implementing components:
- Form interaction patterns
- State management patterns
- Responsive layout patterns
- User experience patterns
- Accessibility implementation
- Best practices

[View Component Functionality →](./docs/SWCF.md)

### SWGS - Global Style Sheet
CSS implementation of our design system:
- Global CSS variables
- Font face declarations
- Base styles
- Custom utility classes
- Component styles
- Responsive design utilities

[View Global Style Sheet →](./docs/SWGS.md)

### SWPT - Project Template
Starter template for new Sport Wales projects:
- Project setup with Vite
- Folder structure
- Configuration files
- Deployment guidelines
- Dependencies and scripts

[View Project Template →](./docs/SWPT.md)


## Detailed Explaination 


1. **SWBG (Sport Wales Brand Guidelines)**
This is the core brand documentation that defines Sport Wales' visual identity:
- Primary brand colors with specific RGB, HEX, and CMYK values (Red, Yellow, Blue, Green)
- Typography system using Objektiv MK1 as primary font, with Montserrat and Arial as fallbacks
- Layout and spacing guidelines (margins, column system)
- Button specifications (corner radius: 8px, height: 46px)
- CSS implementation details for colors, fonts, and components
- Detailed component library with styling for headers, forms, cards, and other UI elements

2. **SWCF (Sport Wales Component Functionality)**
This is a technical guide focusing on how components should behave:
- Form interaction patterns for inputs, checkboxes, and toggles
- State management patterns for form validation and calculations
- Responsive layout patterns for different screen sizes
- User experience patterns (loading states, error handling)
- Accessibility implementations for keyboard navigation and screen readers
- Best practices for performance and user experience

3. **SWGS (Sport Wales Global Style Sheet)**
This is the main CSS stylesheet that implements the brand guidelines:
- Global CSS variables for colors, typography, spacing
- Font face declarations for Objektiv MK1
- Base styles for typography and layout
- Custom utility classes for brand colors
- Component styles for buttons, forms, headers
- Responsive design utilities
- Layout component styles

4. **SWPT (Sport Wales Project Template)**
This is a starter template for new Sport Wales projects:
- Project setup instructions using Vite and React
- Defined project structure and folder organisation
- Configuration files (Vite, Tailwind, PostCSS)
- Deployment instructions for Netlify
- Package dependencies and scripts
- Project features including React Router, HeadlessUI, and Font Awesome integration

Together, these files form a comprehensive design system and development framework for Sport Wales digital products, ensuring consistency in both visual design and functionality across different projects.


## Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn
- Git

### Starting a New Project
1. Implement the design system:
- Copy the global styles from SWGS
- Follow component guidelines from SWCF
- Ensure adherence to brand guidelines (SWBG)


### Best Practices
- Always reference the brand guidelines when creating new components
- Follow the component functionality guide for consistent behavior
- Implement styles using the global style sheet
- Use the project template for new projects
- Test across multiple devices and browsers


## License
This project is proprietary and confidential. All rights reserved by Sport Wales.
