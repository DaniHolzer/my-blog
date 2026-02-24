---
title: "Implementing Content & Visuals"
date: 2026-02-24
series: "first-project"
prev: "/posts/profilePage-fourthPost/"
draft: false
tags: ["react", "content", "images", "tailwind", "typescript"]
description: "Bringing the Penpot designs to life with React components, text content, and optimized images."
---

# Implementing Content & Visuals

*Part 5 of my "First Complete Project" series. [← Part 4: Designing with Penpot](/posts/profilePage-fourthPost/)*

Designs ready, now time to **build**. I followed a structured approach:
layout first, components second, content last.

## Implementation Workflow

1. Navigation Pages (Home, Skills, Documents, Projects, Contact)
2. Page Layout (shared across routes)
    Header + Main + Footer structure
3. Create Reusable Components (container, heading, button, link, card)
4. Layout Components (header with logo + menu button)
5. Page Assembly -> Penpot layout matching
6. Real Content -> Replace lorem ipsum + placeholders
7. Final Colors -> Design system palette

## Step-by-Step Process

### 1. Navigation Pages
```tsx
createRoot(document.getElementById('root')!).render(
  <StrictMode>
    <BrowserRouter>
      <RootLayout>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/contact" element={<Contact />} />
          <Route path="/projects" element={<Projects />} />
          <Route path="/skills" element={<Skills />} />
          <Route path="/documents" element={<Documents />} />
          <Route path="/sitenotice" element={<SiteNotice />} />
        </Routes>
      </RootLayout>
    </BrowserRouter>
  </StrictMode>
);
```

### 2. Page Layout
```tsx
export function RootLayout({ children }:
    { children: React.ReactNode }) {

  return(
    <>
      <HeaderLayout/>
      <main className="pt-[5.6rem] max-w-[50rem] my-0 mx-auto">
            { children }</main>
      <FooterLayout/>
    </>
  );
}
```

### 3. Reusable Components
```tsx
// Tag Styles
export const tagStyles = tv({
  base: "py-[0.5rem] px-[1rem] text-[1.4rem] rounded-full
  text-bgPrimary",
})

// Tag Properties
export interface TagProps extends VariantProps<typeof tagStyles> {
  id?: string;
  className?: string;
  children: string;
}

// Tag - Component
export function Tag({ id, className, children }: TagProps) {
  const generatedId = useId();

  return(
    <div
      id={ id ?? generatedId }
      className={tagStyles({ className })}
    >
      { children }
    </div>
  );
}
```

### 4. Development with Bright Colors
Used random bright colors to distinguish components.
This made layout issues immediately visible.

### 5. Page Assembly
Combined components respecting Penpot layout:

```tsx
<HomePage>
  <Container>
    <Hero />
    <SocialLinks />
  </Container>
</HomePage>
```

### 6-7. Content Replacement
- Lorem ipsum -> Real "Software Engineer from South Tyrol" text
- Placeholder images → Profile photo
- Random colors → Final dark theme palette

## Key Decisions
| Phase	| Focus |
| --- | --- |
| Layoud | Shared Header/Main/Footer for all routes |
| Components | container, heading, button, link, card |
| Development | Bright colors for visual debugging |
| Final | Real content → Design system colors |

## What I Learned
- **Layout-first** approach scales — Shared structure across all pages
- Bright colors = **debugging** gold — Component boundaries crystal clear
- Content reveals design flaws — Real text/images fix spacing issues
- **Component library** pays off — Reused everywhere consistently

<br/>

> **→ Next:** [Retrospective & Lessons Learned](/posts/profilePage-sixthPost/)

Continue reading the "First Complete Project" series.
