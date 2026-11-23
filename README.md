# Ultimate Next.js - Level 3

A beginner-friendly Next.js App Router project used to practice routing,
navigation, layouts, fonts, images, and basic client-side interactivity.

## Tech Stack

- Next.js 15.5.4
- React 19.1.0
- Tailwind CSS 4
- ESLint 9
- JavaScript (JSX)
- Turbopack

## Features

- App Router page structure under `src/app`
- Shared root layout for every route
- Link-based navigation
- Programmatic navigation with `useRouter`
- Local image rendering with `next/image`
- Roboto font loading with `next/font/google`
- Home, About, and Contact routes
- Dark-mode-aware global CSS variables

## Application Routes

| Route | File | Description |
| --- | --- | --- |
| `/` | `src/app/page.jsx` | Main page with navigation links and a button that opens `/about` |
| `/about` | `src/app/about/page.jsx` | About page that displays a local React image |
| `/contact` | `src/app/contact/page.jsx` | Simple contact page |

## Project Structure

```text
Next.js  - Level 3/
|-- public/
|   |-- react.png
|   |-- file.svg
|   |-- globe.svg
|   |-- next.svg
|   |-- vercel.svg
|   `-- window.svg
|-- src/
|   `-- app/
|       |-- about/
|       |   `-- page.jsx
|       |-- contact/
|       |   `-- page.jsx
|       |-- globals.css
|       |-- layout.js
|       |-- page.jsx
|       `-- favicon.ico
|-- jsconfig.json
|-- next.config.mjs
|-- package.json
`-- package-lock.json
```

## Prerequisites

- Node.js 18.18 or newer
- npm

## Installation

Clone the repository, enter this project folder, and install dependencies:

```bash
cd "Next.js  - Level 3"
npm install
```

## Running the Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in a browser.

The development server supports hot reloading. Changes made to files under
`src/app` are reflected in the browser without restarting the server.

## Available Scripts

| Command | Purpose |
| --- | --- |
| `npm run dev` | Start the Next.js development server with Turbopack |
| `npm run build` | Create an optimized production build with Turbopack |
| `npm run start` | Start the production server after building |
| `npm run lint` | Run ESLint across the project |

## Production Build

```bash
npm run build
npm run start
```

The production server is available at
[http://localhost:3000](http://localhost:3000) by default.

## Code Examples

### Navigation with `Link`

The home page uses Next.js `Link` components for client-side navigation:

```jsx
import Link from "next/link";

<Link href="/about">About</Link>
```

### Programmatic Navigation

The home page also uses `useRouter` for navigation triggered by an event:

```jsx
"use client";

import { useRouter } from "next/navigation";

const router = useRouter();
router.push("/about");
```

### Local Images

The About page loads an image from the `public` directory with `next/image`:

```jsx
import Image from "next/image";

<Image src="/react.png" alt="React" width={200} height={200} />
```

## Root Layout and Font

`src/app/layout.js` contains the shared root layout. It:

- Imports `src/app/globals.css`
- Loads Roboto through `next/font/google`
- Applies the selected font to the `<body>`
- Defines basic application metadata

## Styling

Global styles are located in `src/app/globals.css`. The project imports Tailwind
CSS and defines background and foreground variables for light and dark
preferences.

## Image Configuration

`next.config.mjs` includes remote image patterns for:

- `www.google.com`
- `plus.unsplash.com`

Use the Next.js `Image` component when rendering external images to apply
Next.js image optimization and layout safety.

## Course Exercise Ideas

- Add navigation styles and active-route highlighting
- Create a reusable navigation component
- Add a layout for `/about` and `/contact`
- Add loading and error states
- Expand the Contact page with a validated form
- Introduce dynamic routes
- Add a custom 404 page
- Improve metadata for every route
- Convert the project to TypeScript

## Troubleshooting

### Port 3000 is already in use

```bash
npm run dev -- --port 3001
```

### Dependencies are missing or the installation is stale

```bash
npm install
npm run dev
```

### A remote image does not render

Make sure the image hostname is listed in `next.config.mjs` and restart the
development server after changing Next.js configuration.

## Learn More

- [Next.js Documentation](https://nextjs.org/docs)
- [Next.js App Router](https://nextjs.org/docs/app)
- [Next.js Image Optimization](https://nextjs.org/docs/app/building-your-application/optimizing/images)
- [Next.js Font Optimization](https://nextjs.org/docs/app/building-your-application/optimizing/fonts)
- [React Documentation](https://react.dev/)
