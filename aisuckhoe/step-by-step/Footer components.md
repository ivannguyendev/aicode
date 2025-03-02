
# Footer components - Phát triển website aisuckhoe

![Footer components](./Footer%20components.png)

### Prompts:
code Footer components theo thiết kế, bằng react + next + tailwind + có thể dùng thêm thư viện khác
- tuân thủ hình thiết kế
- sử dụng style theo global css
- hiện đại, rõ ràng, nỗi bật

### AI Responses:
```tsx
// components/Footer.tsx
import Link from "next/link";

const Footer = () => {
  return (
    <footer className="bg-background text-foreground py-10">
      <div className="container mx-auto px-6 lg:px-20">
        <div className="flex flex-col lg:flex-row justify-between items-start lg:items-center">
          {/* Logo */}
          <div className="mb-6 lg:mb-0">
            <div className="flex items-center space-x-3">
              <div className="w-10 h-10 bg-primary flex items-center justify-center rounded-lg">
                <span className="text-white text-lg font-bold">🤖</span>
              </div>
              <span className="text-xl font-semibold">BotBuzz</span>
            </div>
          </div>

          {/* Links */}
          <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-8 text-sm">
            <div>
              <h3 className="font-semibold mb-2">Resources</h3>
              <ul className="space-y-1 text-muted-foreground">
                <li><Link href="#">Updates</Link></li>
                <li><Link href="#">Help Center</Link></li>
                <li><Link href="#">Pricing</Link></li>
                <li><Link href="#">Contact</Link></li>
              </ul>
            </div>
            <div>
              <h3 className="font-semibold mb-2">Pricing</h3>
              <ul className="space-y-1 text-muted-foreground">
                <li><Link href="#">Basic Pricing Plan</Link></li>
                <li><Link href="#">Plus Pricing Plan</Link></li>
                <li><Link href="#">Teams Pricing Plan</Link></li>
              </ul>
            </div>
            <div>
              <h3 className="font-semibold mb-2">Explore</h3>
              <ul className="space-y-1 text-muted-foreground">
                <li><Link href="#">AI Personalities</Link></li>
                <li><Link href="#">Bot Buzz AI</Link></li>
              </ul>
            </div>
            <div>
              <h3 className="font-semibold mb-2">Company</h3>
              <ul className="space-y-1 text-muted-foreground">
                <li><Link href="#">Privacy Policy</Link></li>
                <li><Link href="#">Terms and Conditions</Link></li>
              </ul>
            </div>
            <div>
              <h3 className="font-semibold mb-2">Others</h3>
              <ul className="space-y-1 text-muted-foreground">
                <li><Link href="#">FAQs</Link></li>
                <li><Link href="#">Support</Link></li>
              </ul>
            </div>
          </div>
        </div>

        {/* Footer Bottom */}
        <div className="mt-10 border-t border-border pt-6 flex flex-col lg:flex-row items-center justify-between">
          <p className="text-sm text-muted-foreground">Copyright © 2023. All rights reserved</p>
          <div className="flex space-x-4 mt-4 lg:mt-0">
            <button className="px-4 py-2 text-sm rounded-lg bg-muted text-foreground hover:bg-primary hover:text-primary-foreground transition">
              Socials
            </button>
            <button className="px-4 py-2 text-sm rounded-lg bg-muted text-foreground hover:bg-primary hover:text-primary-foreground transition">
              Botbuzz Community
            </button>
          </div>
        </div>
      </div>
    </footer>
  );
};

export default Footer;

```