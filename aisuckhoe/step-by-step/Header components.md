# Header components - Phát triển website aisuckhoe

![Header components](./Header%20components.png)

### Prompts:
code Header components theo thiết kế, bằng react + next + tailwind + có thể dùng thêm thư viện khác
- tuân thủ hình thiết kế
- sử dụng style theo global css
- hiện đại, rõ ràng, nỗi bật

### AI Responses:
```tsx
"use client";

import { useState } from "react";
import Link from "next/link";
import { cn } from "@/lib/utils";
import { Menu, X } from "lucide-react";

const Header = () => {
  const [menuOpen, setMenuOpen] = useState(false);

  return (
    <header className="flex justify-between items-center px-6 md:px-12 py-4 bg-background text-foreground">
      {/* Logo */}
      <div className="flex items-center space-x-2">
        <div className="w-8 h-8 bg-primary rounded-lg flex items-center justify-center">
          <span className="text-white text-xl font-bold">🤖</span>
        </div>
        <span className="text-xl font-semibold">BotBuzz</span>
      </div>

      {/* Desktop Nav */}
      <nav className="hidden md:flex items-center space-x-6">
        <Link href="/faq" className="hover:text-primary">
          FAQ
        </Link>
        <Link href="/pricing" className="hover:text-primary">
          Pricing
        </Link>
        <Link href="/signin" className="hover:text-primary">
          Sign in
        </Link>
      </nav>

      {/* Mobile Menu Button */}
      <button
        className="md:hidden p-2 rounded-lg bg-muted/10"
        onClick={() => setMenuOpen(!menuOpen)}
      >
        {menuOpen ? <X size={24} /> : <Menu size={24} />}
      </button>

      {/* Mobile Nav */}
      {menuOpen && (
        <div className="absolute top-16 left-0 w-full bg-background shadow-lg p-4 flex flex-col items-center space-y-4 md:hidden">
          <Link href="/faq" className="hover:text-primary" onClick={() => setMenuOpen(false)}>
            FAQ
          </Link>
          <Link href="/pricing" className="hover:text-primary" onClick={() => setMenuOpen(false)}>
            Pricing
          </Link>
          <Link href="/signin" className="hover:text-primary" onClick={() => setMenuOpen(false)}>
            Sign in
          </Link>
        </div>
      )}

      {/* Get Started Button */}
      <Link
        href="/get-started"
        className="hidden md:block px-4 py-2 rounded-full bg-primary text-primary-foreground font-medium hover:bg-primary/80 transition"
      >
        Get Started
      </Link>
    </header>
  );
};

export default Header;
```