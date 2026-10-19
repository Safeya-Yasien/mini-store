This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

✨ This project was implemented by following this YouTube tutorial by PedroTech.
https://lnkd.in/e752WiFw

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Test a payment with Stripe

The checkout flow uses Stripe's hosted Checkout page. To test it locally:

1. In the [Stripe Dashboard](https://dashboard.stripe.com/), enable **Test mode** and copy your test secret key (`sk_test_...`).
2. Add the following variables to `.env.local` (keep your existing Clerk variables there if you use Clerk authentication):

   ```env
   STRIPE_SECRET_KEY=sk_test_your_test_secret_key
   NEXT_PUBLIC_BASE_URL=http://localhost:3000
   ```

3. Start the app with `npm run dev`, sign in, add a product to your cart, and select **Proceed to Payment**.
4. On the Stripe Checkout page, enter this test card:

   | Field | Value |
   | --- | --- |
   | Card number | `4242 4242 4242 4242` |
   | Expiration date | Any future date, such as `12/34` |
   | CVC | Any three digits, such as `123` |
   | Name, ZIP/postal code | Any values, if requested |

   Submit the payment to simulate a successful transaction. Stripe redirects back to the app's success page. To test other outcomes or payment methods, see [Stripe's testing documentation](https://docs.stripe.com/testing#cards).

Use only Stripe test keys and test card numbers for these steps. Do not use real card details or live keys for testing.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
