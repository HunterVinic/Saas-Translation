# Next.js Application

A modern web application built with Next.js 13+, featuring App Router, Tailwind CSS, and automatic dark mode support.

## Table of Contents
- [Overview](#overview)
- [Technologies](#technologies)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Core Components](#core-components)
- [Styling](#styling)
- [Development](#development)
- [Building for Production](#building-for-production)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)

## Overview

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app). It includes:

- Next.js 14 with App Router
- TypeScript support
- Tailwind CSS for styling
- Automatic dark mode detection
- Optimized fonts with next/font
- Responsive design

## Technologies

| Technology | Version | Purpose |
|------------|---------|---------|
| Next.js | 14.x | React framework |
| React | 18.x | UI library |
| TypeScript | 5.x | Type safety |
| Tailwind CSS | 3.x | Styling |
| Inter Font | - | Typography |

## Prerequisites

- Node.js 18.17 or later
- npm/yarn/pnpm package manager
- Git (optional)

## Installation

```bash
# Clone the repository
git clone <repository-url>
cd nextjs-app

# Install dependencies
npm install
# or
yarn install
# or
pnpm install

# Run development server
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Project Structure

```
nextjs-app/
├── app/
│   ├── globals.css          # Global styles & Tailwind imports
│   ├── layout.tsx           # Root layout component
│   └── page.tsx             # Home page component
├── public/                   # Static assets
│   ├── next.svg
│   ├── vercel.svg
│   └── ...
├── next.config.js           # Next.js configuration
├── tailwind.config.js       # Tailwind CSS configuration
├── postcss.config.js        # PostCSS configuration
├── package.json             # Dependencies and scripts
└── tsconfig.json            # TypeScript configuration
```

## Core Components

### Root Layout (`app/layout.tsx`)

The root layout component that wraps all pages:

```tsx
export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <body className={inter.className}>{children}</body>
    </html>
  )
}
```

Features:
- Sets HTML language to English
- Applies Inter font globally
- Metadata configuration for SEO

### Home Page (`app/page.tsx`)

The main landing page featuring:
- Responsive design with Tailwind CSS
- Next.js logo and branding
- Links to documentation, tutorials, templates, and deployment
- Gradient effects and animations
- Dark mode support

### Global Styles (`app/globals.css`)

Contains:
- Tailwind CSS directives
- CSS variables for theming
- Dark mode preferences
- Gradient backgrounds

```css
:root {
  --foreground-rgb: 0, 0, 0;
  --background-start-rgb: 214, 219, 220;
  --background-end-rgb: 255, 255, 255;
}

@media (prefers-color-scheme: dark) {
  :root {
    --foreground-rgb: 255, 255, 255;
    --background-start-rgb: 0, 0, 0;
    --background-end-rgb: 0, 0, 0;
  }
}
```

## Styling

### Tailwind CSS Configuration

The project uses Tailwind CSS for styling with:
- Utility-first approach
- Responsive design utilities
- Dark mode support via `prefers-color-scheme`
- Custom gradients and effects

### Dark Mode

Automatic dark mode detection using CSS media queries:
```css
@media (prefers-color-scheme: dark) {
  :root {
    /* Dark mode variables */
  }
}
```

### Custom Gradients

Multiple gradient effects are used:
- Radial gradients for background effects
- Conic gradients for decorative elements
- Linear gradients for smooth transitions

## Development

### Available Scripts

```bash
# Development server with hot reload
npm run dev

# Build for production
npm run build

# Start production server
npm run start

# Lint code
npm run lint
```

### Code Editing

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

### Font Optimization

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load the Inter font.

## Building for Production

```bash
# Create production build
npm run build

# Preview production build locally
npm run start
```

The build process:
1. Compiles TypeScript to JavaScript
2. Optimizes images and assets
3. Generates static HTML files
4. Applies code splitting
5. Minifies CSS and JavaScript

## Deployment

### Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme).

**Deployment Steps:**
1. Push code to GitHub/GitLab/Bitbucket
2. Import project to Vercel
3. Automatic deployments on push

### Other Hosting Options

- **Netlify**: Support for Next.js applications
- **AWS Amplify**: Full-stack deployment
- **Self-hosted**: Node.js server required

## Troubleshooting

### Common Issues

1. **Port already in use**
   ```bash
   # Kill process on port 3000 (Mac/Linux)
   kill -9 $(lsof -t -i:3000)
   
   # Or use different port
   npm run dev -- -p 3001
   ```

2. **Module not found errors**
   ```bash
   # Clear npm cache and reinstall
   rm -rf node_modules package-lock.json
   npm install
   ```

3. **Build failures**
   - Check TypeScript errors
   - Verify all dependencies are installed
   - Check for syntax errors in components

### Debug Mode

Enable debugging with:
```bash
# More verbose output
NODE_OPTIONS='--inspect' npm run dev

# Debug build process
NODE_OPTIONS='--inspect' npm run build
```

## Performance Optimization

### Built-in Optimizations

- **Automatic Image Optimization**: Using Next.js Image component
- **Font Optimization**: next/font for Inter font
- **Code Splitting**: Automatic page-based splitting
- **Static Generation**: Pre-rendering where possible

### Best Practices

1. **Use next/image for images**
   ```tsx
   <Image
     src="/vercel.svg"
     alt="Vercel Logo"
     width={100}
     height={24}
     priority
   />
   ```

2. **Leverage CSS variables for theming**
3. **Implement responsive design with Tailwind**
4. **Optimize fonts with next/font**

## Environment Variables

Create a `.env.local` file for environment variables:

```env
NEXT_PUBLIC_API_URL=your_api_url
DATABASE_URL=your_database_url
```

## Features to Add

- [ ] Custom 404 page
- [ ] API routes
- [ ] Dynamic routes
- [ ] Middleware for authentication
- [ ] Incremental Static Regeneration (ISR)
- [ ] Internationalization (i18n)

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.
- [Next.js GitHub Repository](https://github.com/vercel/next.js/) - feedback and contributions welcome.
- [Tailwind CSS Documentation](https://tailwindcss.com/docs) - styling guide.

## 📜 License

Copyright (c) 2026 Sheshehang Limbu

All rights reserved.

This project and its source code are proprietary and confidential. No part of this project may be:
- Copied or reproduced in any form
- Modified or adapted
- Distributed or transmitted
- Used for commercial purposes

without explicit written permission from the author.

## 👨‍💻 Author

**Sheshehang Limbu**
*Full Stack Developer*

### Connect with the Author

| Platform | Link |
|----------|------|
| **GitHub** | [@HunterVinic](https://github.com/HunterVinic) |
| **Email** | [sheshehangs2016@gmail.com](mailto:sheshehangs2016@gmail.com) |
| **LinkedIn** | [Sheshehang Limbu](www.linkedin.com/in/sheshehang-limbu) |

### About the Author

Sheshehang Limbu is a Full Stack developer with expertise in:

| Area | Technologies |
|------|-------------|
| **Frontend** | Next.js, React, TypeScript, Tailwind CSS |
| **Backend** | Node.js, Python, REST APIs |
| **Database** | PostgreSQL, MongoDB, SQLite |
| **DevOps** | Vercel, Netlify, AWS |

### Support and Inquiries

For:
- 🐛 Bug reports
- 💡 Feature suggestions
- 🤝 Collaboration opportunities
- 📧 Business inquiries

Please contact the author directly via email or LinkedIn.

---

**Last Updated**: March 3, 2026  
**Next.js Version**: 14.x  
**React Version**: 18.x  
**Node.js Requirement**: 18.17+

---

<div align="center">
  <a href="https://nextjs.org">
    <img src="https://assets.vercel.com/image/upload/v1662130559/nextjs/Icon_light_background.png" alt="Next.js Logo" width="50" height="50"/>
  </a>
  <br />
  Made with ❤️ by Sheshehang Limbu
</div>
