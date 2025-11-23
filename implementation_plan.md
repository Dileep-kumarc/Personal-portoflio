# Portfolio Migration to Next.js 14+ & Premium UI

## Goal Description
Migrate the existing vanilla HTML/CSS/JS portfolio to a high-performance Next.js 14+ application. This upgrade will introduce a modern component-based architecture, premium UI libraries (Tailwind CSS, Framer Motion), and advanced animations to create a "wow" factor. The content (About, Skills, Projects, etc.) will be preserved and enhanced with a premium design.

## User Review Required
> [!IMPORTANT]
> **Directory Restructuring**: The current files (`index.html`, `styles.css`, `script.js`, etc.) will be moved to a `legacy_backup` folder to allow initializing a clean Next.js project in the root directory.

> [!NOTE]
> **Framework Choice**: We will use Next.js 14 (App Router) as requested, with Tailwind CSS for styling and Framer Motion for animations.

## Proposed Changes

### 1. Project Initialization & Setup
- [NEW] Move existing files to `legacy_backup/`
- [NEW] Initialize Next.js 14 app in root (`npx create-next-app@latest .`)
- [NEW] Configure Tailwind CSS v4 (or latest stable)
- [NEW] Install dependencies: `framer-motion`, `gsap`, `lucide-react`, `clsx`, `tailwind-merge`, `next-themes` (for dark mode), `@react-three/fiber` (optional for 3D).

### 2. Component Architecture
We will break down the monolithic `index.html` into reusable React components.

#### Structure
- `app/layout.tsx`: Root layout with ThemeProvider and global styles.
- `app/page.tsx`: Main landing page composing all sections.
- `components/ui/`: Reusable UI atoms (Buttons, Cards, Inputs) - inspired by shadcn/ui.
- `components/sections/`: Major page sections (Hero, About, Skills, Projects, Experience, Contact).
- `components/layout/`: Navbar, Footer.

### 3. Section Implementation Plan

#### Hero Section (`components/sections/Hero.tsx`)
- **Design**: High-impact typography, animated background (particles or 3D), "Typewriter" effect for roles.
- **Tech**: Framer Motion for entrance animations.

#### Skills Section (`components/sections/Skills.tsx`)
- **Design**: Interactive grid of skill cards with hover effects (glassmorphism).
- **Tech**: Tailwind CSS grid, Framer Motion hover states.

#### Projects Section (`components/sections/Projects.tsx`)
- **Design**: Featured project cards with image previews and "Live Demo"/"GitHub" links.
- **Tech**: Reusable `ProjectCard` component.

#### Experience & Education (`components/sections/Timeline.tsx`)
- **Design**: Vertical timeline with animated entry.
- **Tech**: Custom timeline component.

#### Contact Section (`components/sections/Contact.tsx`)
- **Design**: Clean form with validation and social links.
- **Tech**: React Hook Form (optional) or simple state-controlled form.

### 4. Premium Features
- **Dark/Light Mode**: Implemented using `next-themes`.
- **Smooth Scroll**: Global smooth scrolling behavior.
- **Custom Cursor**: React-based custom cursor component (optional, if requested).

## Verification Plan

### Automated Tests
- Run `npm run build` to ensure type safety and build success.
- Run `npm run lint` to check code quality.

### Manual Verification
- Verify all sections (Home, Skills, Projects, etc.) are present and content matches the original.
- Test responsiveness on Mobile, Tablet, and Desktop.
- Test Dark/Light mode toggle.
- Verify animations run smoothly without lag.
