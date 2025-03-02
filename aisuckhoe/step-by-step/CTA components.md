# CTA components - Phát triển website aisuckhoe

![CTA components](./CTA%20components.png)

### Prompts:
code CTA components theo thiết kế, bằng react + next + tailwind + có thể dùng thêm thư viện khác
- tuân thủ hình thiết kế
- sử dụng style theo global css
- hiện đại, rõ ràng, nỗi bật
- 1 section Web App CTA: chat trực tiếp trên web, nhanh chóng, tiện lợi, không cần cài đặt
- 1 section Telegram CTA: tích hợp với Telegram, nhanh chóng, tiện lợi

### AI Responses:
```tsx
import Link from 'next/link';
import clsx from 'clsx';

const CTAButton = ({ text, href, isPrimary = false }) => {
  return (
    <Link
      href={href}
      className={clsx(
        'px-6 py-3 rounded-full text-lg font-semibold border transition-all',
        isPrimary
          ? 'bg-primary text-primary-foreground hover:bg-opacity-80'
          : 'border-primary text-primary hover:bg-primary hover:text-primary-foreground'
      )}
    >
      {text}
    </Link>
  );
};

export function WebAppCTA() {
  return (
    <section className="flex flex-col items-center justify-center gap-6 p-10 bg-card rounded-2xl shadow-lg max-w-3xl mx-auto">
      <h2 className="text-3xl font-bold text-center text-foreground">Chat Trực Tiếp Trên Web</h2>
      <p className="text-center text-muted-foreground max-w-xl">
        Trải nghiệm trò chuyện nhanh chóng, tiện lợi, không cần cài đặt.
      </p>
      <CTAButton text="Chat Trên Web" href="/chat" isPrimary />
    </section>
  );
}

export function TelegramCTA() {
  return (
    <section className="flex flex-col items-center justify-center gap-6 p-10 bg-card rounded-2xl shadow-lg max-w-3xl mx-auto mt-8">
      <h2 className="text-3xl font-bold text-center text-foreground">Chat Trên Telegram</h2>
      <p className="text-center text-muted-foreground max-w-xl">
        Kết nối ngay với AI trên Telegram, nhanh chóng và dễ dàng.
      </p>
      <CTAButton text="Mở Telegram" href="https://t.me/yourbot" />
    </section>
  );
}
```