# Build Fix Walkthrough

## Issue
The Vercel build was failing with the error:
`Type error: Cannot find module '@/components/theme-toggle' or its corresponding type declarations.`

This was caused by `components/layout/navbar.tsx` importing a file that did not exist in the project.

## Fix
I created the missing `components/theme-toggle.tsx` file with a standard light/dark mode toggle button using `next-themes` and `lucide-react`.

### [NEW] [theme-toggle.tsx](file:///c:/Users/dilee/Downloads/Personal-portoflio/components/theme-toggle.tsx)
```tsx
"use client"

import * as React from "react"
import { Moon, Sun } from "lucide-react"
import { useTheme } from "next-themes"

import { Button } from "@/components/ui/button"

export function ThemeToggle() {
  const { theme, setTheme } = useTheme()

  return (
    <Button
      variant="ghost"
      size="icon"
      onClick={() => setTheme(theme === "light" ? "dark" : "light")}
    >
      <Sun className="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
      <Moon className="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
      <span className="sr-only">Toggle theme</span>
    </Button>
  )
}
```

## Verification
I ran `npm run build` locally and it completed successfully.

```
✓ Generating static pages using 11 workers (4/4) in 7.4s
Exit code: 0
```
