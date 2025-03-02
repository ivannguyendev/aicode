
# Pricing components - Phát triển website aisuckhoe

![Pricing components](./Pricing%20components.png)

### Prompts:
code Pricing components theo thiết kế, bằng react + next + tailwind + có thể dùng thêm thư viện khác
- tuân thủ hình thiết kế
- sử dụng style theo global css
- hiện đại, rõ ràng, nỗi bật

### AI Responses:
```tsx
'use client';

import { Button } from '@/components/ui/button';
import { Card, CardContent } from '@/components/ui/card';
import { Badge } from '@/components/ui/badge';
import { Check } from 'lucide-react';
import Image from 'next/image';

const plans = [
  {
    name: 'Free',
    price: 'USD $0/month',
    image: '/images/free-plan.jpg',
    features: [
      'Limited access to Multiple Personalities (3 personalities)',
      'Basic Dynamic Suggestions',
      'Multi-platform Integration (limited to 1 device)',
      'Multilingual Support (2 languages)',
    ],
    buttonLabel: 'Your Current Plan',
    isBestSelling: false,
  },
  {
    name: 'Plus',
    price: 'USD $20/month',
    image: '/images/plus-plan.jpg',
    features: [
      'Access to Multiple Personalities (10 personalities)',
      'Real-time Web References (unlimited queries)',
      'Multi-platform Integration (up to 5 devices)',
      'Multilingual Support (10 languages)',
    ],
    buttonLabel: 'Upgrade to Plus',
    isBestSelling: true,
  },
  {
    name: 'Team',
    price: 'USD $40/month (per user)',
    image: '/images/team-plan.jpg',
    features: [
      'Advanced Generated Images (limited to 100 images/month for the team)',
      'Multilingual Support (15 languages)',
      'Advanced Feedback Mechanism',
      'Collaborative conversation features for team projects',
    ],
    buttonLabel: 'Upgrade to Team',
    isBestSelling: false,
  },
];

export default function Pricing() {
  return (
    <section className="py-16 text-center">
      <h2 className="text-4xl font-extrabold mb-4">
        Choose the Plan That’s <span className="text-primary">Right For You</span>
      </h2>
      <p className="text-lg text-muted-foreground mb-10">
        Provide Descriptions, Get Instant AI Generated Content
      </p>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-6xl mx-auto">
        {plans.map((plan, index) => (
          <Card
            key={index}
            className="bg-card text-card-foreground p-6 rounded-2xl shadow-lg border border-border flex flex-col justify-between relative"
          >
            <div className="flex items-center justify-between">
              <h3 className="text-2xl font-semibold mb-1">{plan.name}</h3>
              {plan.isBestSelling && (
                <Badge className="bg-gradient-to-r from-purple-500 to-indigo-500 text-white px-3 py-1 text-xs rounded-full shadow-md">
                  Best Selling
                </Badge>
              )}
            </div>
            <p className="text-sm text-muted-foreground mb-4">{plan.price}</p>
            <Image src={plan.image} alt={plan.name} width={400} height={200} className="rounded-xl mb-4" />
            <ul className="space-y-3 text-left">
              {plan.features.map((feature, i) => (
                <li key={i} className="flex items-center gap-2 text-sm">
                  <Check className="w-4 h-4 text-primary" /> {feature}
                </li>
              ))}
            </ul>
            <Button
              className="w-full mt-6 py-3 text-lg bg-primary text-white hover:bg-opacity-90 rounded-lg shadow-md"
              disabled={plan.name === 'Free'}
            >
              {plan.buttonLabel}
            </Button>
          </Card>
        ))}
      </div>
    </section>
  );
}
```