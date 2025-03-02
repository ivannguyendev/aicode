# Global CSS - Phát triển website aisuckhoe

### Prompts:
từ logo này hãy gợi ý bộ color để dùng trên website và tailwind. logo này có chủ đề Health và Chatbot và AI
chỉnh lại theo định dạng css này:

```css
/* global.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    font-size: unset;
    font-weight: unset;
  }

  :root {
    --background: 0 0% 100%;
    --foreground: 222.2 84% 4.9%;

    --card: 240 5% 96%;
    --card-foreground: 222.2 84% 4.9%;

    --popover: 0 0% 100%;
    --popover-foreground: 222.2 84% 4.9%;

    --primary: #1E90FF;
    --primary-foreground: 210 40% 98%;

    --secondary: 210 40% 96.1%;
    --secondary-foreground: 222.2 47.4% 11.2%;

    --muted: 210 40% 96.1%;
    --muted-foreground: 215.4 16.3% 46.9%;

    --accent: 210 40% 96.1%;
    --accent-foreground: 222.2 47.4% 11.2%;

    --destructive: 0 84.2% 60.2%;
    --destructive-foreground: 210 40% 98%;

    --border: 240 6% 80%;
    --input: 214.3 31.8% 91.4%;
    --ring: 222.2 84% 4.9%;

    --radius: 0.2rem;

    --success: 196 52% 74%;
    --warning: 34 89% 85%;
    --error: 10 100% 86%;
  }

  [data-theme='dark'] {
    
    background-color: var(--background-dark);
    color: var(--text-dark);

    --background: 0 0% 0%;
    --foreground: 210 40% 98%;

    --card: 0 0% 4%;
    --card-foreground: 210 40% 98%;

    --popover: 222.2 84% 4.9%;
    --popover-foreground: 210 40% 98%;

    --primary: 210 40% 98%;
    --primary-foreground: 222.2 47.4% 11.2%;

    --secondary: 217.2 32.6% 17.5%;
    --secondary-foreground: 210 40% 98%;

    --muted: 217.2 32.6% 17.5%;
    --muted-foreground: 215 20.2% 65.1%;

    --accent: 217.2 32.6% 17.5%;
    --accent-foreground: 210 40% 98%;

    --destructive: 0 62.8% 30.6%;
    --destructive-foreground: 210 40% 98%;

    --border: 0, 0%, 15%, 0.8;
    --input: 217.2 32.6% 17.5%;
    --ring: 212.7 26.8% 83.9%;

    --success: 196 100% 14%;
    --warning: 34 51% 25%;
    --error: 10 39% 43%;
  }
}

@layer base {
  * {
    @apply border-border;
    @apply font-sans;
    @apply transition-colors duration-300;
  }
  body {
    @apply bg-background text-foreground min-h-[100vh] flex flex-col;
    @apply font-bold;
  }
}

html {
  opacity: 0;
}

html[data-theme='dark'],
html[data-theme='light'] {
  opacity: initial;
}
```



### AI Responses:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    font-size: unset;
    font-weight: unset;
  }

  :root {
    --background: 210 40% 96.1%; /* Soft gray (#F5F7FA) */
    --foreground: 222.2 84% 4.9%; /* Dark gray (#333333) */

    --card: 210 40% 96.1%; /* Soft gray for cards */
    --card-foreground: 222.2 84% 4.9%; /* Dark gray for card text */

    --popover: 210 40% 96.1%; /* Soft gray for popovers */
    --popover-foreground: 222.2 84% 4.9%; /* Dark gray for popover text */

    --primary: 208 100% 50%; /* Primary blue (#1E90FF) */
    --primary-foreground: 210 40% 98%; /* White (#FFFFFF) for text on primary */

    --secondary: 180 60% 50%; /* Teal light (#00CED1) */
    --secondary-foreground: 210 40% 98%; /* White (#FFFFFF) for text on secondary */

    --muted: 210 40% 96.1%; /* Soft gray for muted areas */
    --muted-foreground: 215.4 16.3% 46.9%; /* Lighter gray for muted text */

    --accent: 180 60% 50%; /* Teal dark (#20B2AA) */
    --accent-foreground: 210 40% 98%; /* White for text on accent */

    --destructive: 0 84.2% 60.2%; /* Red for destructive actions */
    --destructive-foreground: 210 40% 98%; /* White for text on destructive */

    --border: 240 6% 80%; /* Light border gray */
    --input: 214.3 31.8% 91.4%; /* Light input background */
    --ring: 208 100% 50%; /* Ring color matching primary blue */

    --radius: 0.2rem;

    --success: 196 52% 74%; /* Green for success */
    --warning: 34 89% 85%; /* Yellow for warnings */
    --error: 10 100% 86%; /* Red for errors */
  }

  [data-theme='dark'] {
    --background: 217.2 32.6% 17.5%; /* Dark background (#2D3748) */
    --foreground: 210 40% 98%; /* Light gray (#E2E8F0) for text */

    --card: 0 0% 4%; /* Very dark gray for cards */
    --card-foreground: 210 40% 98%; /* Light gray for card text */

    --popover: 217.2 32.6% 17.5%; /* Dark background for popovers */
    --popover-foreground: 210 40% 98%; /* Light gray for popover text */

    --primary: 208 100% 60%; /* Lighter blue (#4DA6FF) for dark mode */
    --primary-foreground: 222.2 47.4% 11.2%; /* Dark gray for text on primary */

    --secondary: 180 40% 30%; /* Darker teal (#1A7F78) */
    --secondary-foreground: 210 40% 98%; /* White for text on secondary */

    --muted: 217.2 32.6% 17.5%; /* Dark muted background */
    --muted-foreground: 215 20.2% 65.1%; /* Lighter gray for muted text */

    --accent: 180 40% 30%; /* Darker teal (#1A7F78) */
    --accent-foreground: 210 40% 98%; /* White for text on accent */

    --destructive: 0 62.8% 30.6%; /* Dark red for destructive */
    --destructive-foreground: 210 40% 98%; /* White for text on destructive */

    --border: 0 0% 15%; /* Dark border */
    --input: 217.2 32.6% 17.5%; /* Dark input background */
    --ring: 212.7 26.8% 83.9%; /* Light ring for dark mode */

    --success: 196 100% 14%; /* Dark green for success */
    --warning: 34 51% 25%; /* Dark yellow for warnings */
    --error: 10 39% 43%; /* Dark red for errors */
  }
}

@layer base {
  * {
    @apply border-border;
    @apply font-sans;
    @apply transition-colors duration-300;
  }
  body {
    @apply bg-background text-foreground min-h-[100vh] flex flex-col;
    @apply font-bold;
  }
}

html {
  opacity: 0;
}

html[data-theme='dark'],
html[data-theme='light'] {
  opacity: initial;
}
```