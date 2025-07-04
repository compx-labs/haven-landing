Absolutely—here’s the **complete plan entirely in Markdown format**, including headings and code snippets:

---

# 🌟 Haven Landing Page – Remix App Build Plan

# What is Haven?
Haven is the easiest way to grow your savings with real yield.
With just a few taps, you can deposit your dollars, which are seamlessly converted into xUSD—our stable digital dollar—and start earning passive rewards instantly. Your savings are automatically put to work behind the scenes in secure, on-chain strategies, so your balance grows every day without any of the complexity of crypto trading. Designed for everyone, Haven makes saving secure, simple, and rewarding.

---

## 🛠️ Tech Stack

* **Framework:** Remix
* **Styling:** Tailwind CSS
* **Animations:** Framer Motion
* **Design Style:** Neumorphism – soft, elegant, tactile
* **Themes:** Support for multiple color schemes

---

## 🎨 Color Themes

```typescript
export const colorThemes = {
  lightPink: {
    background: '#F5D7E3',
    backgroundDarker: '#E8C2D1',
    backgroundLighter: '#FBE8F0',
    headerText: '#4A2F35',
    bodyText: '#6E4A50',
    error: '#E53935',
    loading: '#FFCDD2',
    success: '#66BB6A',
  },
  terracotta: {
    background: '#E2725B',
    backgroundDarker: '#C05C4A',
    backgroundLighter: '#F1A087',
    headerText: '#3E231E',
    bodyText: '#5E3D36',
    error: '#B71C1C',
    loading: '#F8B4A8',
    success: '#81C784',
  },
  grey: {
    background: '#E0E0E0',
    backgroundDarker: '#BDBDBD',
    backgroundLighter: '#F5F5F5',
    headerText: '#212121',
    bodyText: '#424242',
    error: '#D32F2F',
    loading: '#EEEEEE',
    success: '#388E3C',
  },
  obsidian: {
    background: '#1A1A1A',
    backgroundDarker: '#0F0F0F',
    backgroundLighter: '#2E2E2E',
    headerText: '#FFFFFF',
    bodyText: '#CCCCCC',
    error: '#EF5350',
    loading: '#424242',
    success: '#66BB6A',
  },
};

// Current active theme (can be changed to switch themes)
export type ThemeName = keyof typeof colorThemes;
export const currentTheme: ThemeName = 'lightPink';

// Create the theme using the selected color theme
const selectedColors = colorThemes[currentTheme];

const theme = createTheme({
  colors: {
    mainBackground: selectedColors.background,
    backgroundDarker: selectedColors.backgroundDarker,
    backgroundLighter: selectedColors.backgroundLighter,
    headerText: selectedColors.headerText,
    bodyText: selectedColors.bodyText,
    error: selectedColors.error,
    loading: selectedColors.loading,
    success: selectedColors.success,

    // Legacy color mappings
    primary: selectedColors.headerText,
    secondary: selectedColors.success,
    text: selectedColors.headerText,
    textSecondary: selectedColors.bodyText,
    border: selectedColors.backgroundDarker,
    danger: selectedColors.error,
    warning: '#FFA500',
  },
});
```

---

## ✨ Page Sections Outline

### 1. Hero Section

* **Headline:** *Save simply. Earn effortlessly.*
* **Subline:** *A modern way to grow your dollars with real yield—safe, simple, and automatic.*
* **Visual:** Mobile mockup
* **CTA:** *Join the Waitlist*

---

### 2. How It Works

* **3 Steps:**

  1. Deposit Dollars
  2. Convert to xUSD
  3. Earn Rewards
* **Icons:** Illustrate each step
* **Animation:** Fade/slide-in on scroll

---

### 3. Why Haven

* Benefits grid (real yield, security, ease, access)

---

### 4. The Difference

* Table comparing Haven to traditional savings

---

### 5. Trust & Security

* Audits, partners, simple reassurance copy

---

### 6. Early Access

* Signup form
* Optional perks for early users

---

### 7. FAQs

* Accordion questions styled with neumorphism

---

### 8. Footer

* Links, socials, disclaimers

---

## 🛠️ Build Steps

### 1️⃣ Project Setup

**Create Remix project:**

```bash
npx create-remix@latest
```

**Install dependencies:**

```bash
npm install tailwindcss framer-motion @headlessui/react
```

**Configure Tailwind:**

```bash
npx tailwindcss init -p
```

**Update `tailwind.config.js`:**

```javascript
module.exports = {
  content: ["./app/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

**Import Tailwind in `app/styles/tailwind.css`:**

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

**Link CSS in `root.tsx`:**

```tsx
import styles from "~/styles/tailwind.css";

export function links() {
  return [{ rel: "stylesheet", href: styles }];
}
```

---

### 2️⃣ Layout and Theming

* Create `ThemeContext` to manage the current theme.
* Store active theme in `localStorage`.
* Use Tailwind utility classes + dynamic inline styles.

**Example:**

```tsx
<div
  style={{ backgroundColor: selectedColors.background }}
  className="min-h-screen"
>
```

---

### 3️⃣ Neumorphism Styling

* Use **large rounded corners:**

```html
class="rounded-3xl"
```

* **Soft inset shadows:**

```css
shadow-[inset_4px_4px_10px_rgba(0,0,0,0.05),inset_-4px_-4px_10px_rgba(255,255,255,0.8)]
```

* **Dark theme shadows:**

```css
shadow-[inset_4px_4px_8px_rgba(0,0,0,0.3),inset_-4px_-4px_8px_rgba(255,255,255,0.1)]
```

---

### 4️⃣ Framer Motion Animations

* Animate sections on scroll (fade/slide).
* Animate buttons on hover (`scale`).

**Example:**

```tsx
<motion.div
  initial={{ opacity: 0, y: 30 }}
  whileInView={{ opacity: 1, y: 0 }}
  transition={{ duration: 0.6 }}
>
  <h1>Save simply. Earn effortlessly.</h1>
</motion.div>
```

---

### 5️⃣ Email Capture

* Use **Formspree, Supabase, or Airtable** for submissions.
* Validate email input.

---

### 6️⃣ Responsive Design

* Use Tailwind breakpoints (`sm`, `md`, `lg`).
* Test layouts on mobile and tablet.

---

## ✅ Final Notes

* Keep tone approachable, modern, and trustworthy.
* Emphasize simplicity and security.
* Use neumorphic design consistently.
* Make theme switching prominent to showcase all color schemes.

---

If you’d like, I can help write actual starter components or theme toggler logic. Just let me know!
