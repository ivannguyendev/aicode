
# FAQ components - Phát triển website aisuckhoe

![FAQ components](./FAQ%20components.png)

### Prompts:
code FAQ components theo thiết kế, bằng react + next + tailwind + có thể dùng thêm thư viện khác
- tuân thủ hình thiết kế
- sử dụng style theo global css
- hiện đại, rõ ràng, nỗi bật

### AI Responses:
```tsx
// components/FAQ.tsx
"use client";

import { useState } from "react";
import { motion } from "framer-motion";
import { ChevronDown, ChevronUp } from "lucide-react";

const faqs = [
  {
    id: 1,
    question: "Is my data safe with Ai-Con?",
    answer:
      "Ai-Con is a conversational AI app offering personalized interactions with customizable personalities. It uses natural language processing and machine learning to provide dynamic suggestions and real-time information.",
  },
  { id: 2, question: "What is Botbuzz and how does it work?" },
  { id: 3, question: "Can I customize the personality of my AI companion?" },
  { id: 4, question: "How does the real-time web reference feature work?" },
  { id: 5, question: "What are the benefits of the premium plans compared to the free plan?" },
];

export default function FAQ() {
  const [openId, setOpenId] = useState<number | null>(1);

  const toggleFAQ = (id: number) => {
    setOpenId(openId === id ? null : id);
  };

  return (
    <section className="py-12 px-6 md:px-12 bg-background text-foreground">
      <div className="max-w-2xl mx-auto text-center">
        <h2 className="text-3xl md:text-4xl font-bold">Everything You Need To Know</h2>
        <p className="text-muted-foreground mt-2">Here Are Some Frequently Asked Questions</p>
      </div>

      <div className="max-w-2xl mx-auto mt-8 space-y-4">
        {faqs.map((faq) => (
          <div
            key={faq.id}
            className="border-b border-border cursor-pointer"
            onClick={() => toggleFAQ(faq.id)}
          >
            <div className="flex justify-between items-center py-4">
              <span className={`text-lg font-semibold ${openId === faq.id ? "text-primary" : ""}`}>
                {faq.id < 10 ? `0${faq.id}` : faq.id} {faq.question}
              </span>
              {openId === faq.id ? <ChevronUp className="w-5 h-5 text-primary" /> : <ChevronDown className="w-5 h-5" />}
            </div>
            {openId === faq.id && faq.answer && (
              <motion.p
                initial={{ opacity: 0, height: 0 }}
                animate={{ opacity: 1, height: "auto" }}
                exit={{ opacity: 0, height: 0 }}
                className="text-muted-foreground pb-4"
              >
                {faq.answer}
              </motion.p>
            )}
          </div>
        ))}
      </div>
    </section>
  );
}

```