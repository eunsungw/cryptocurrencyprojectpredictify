# Vercel and optional Supabase deployment

## Deploy the simulated wallet UI to Vercel
1. On GitHub, review and merge the draft PR into the Predictify repository only after you are satisfied with the isolated folder. A standalone new repository works too.
2. Connect the repo in Vercel (**user action required**).
3. If using the Predictify monorepo, set **Root Directory** to `projects/wallet-qa-lab`.
4. Framework preset: **Other**; build command `npm run build`; output directory `dist`.
5. Deploy. The app is a static independent lab and requires no secrets.
6. For smartphone testing, open the Vercel preview or production URL in Android Chrome (test environment only).

## Supabase optional enhancement (not implemented in v1)
1. Create **a new sandbox project**. Do not point this lab at the existing Predictify production database.
2. Open the SQL editor and review `supabase/schema.sql` before applying it.
3. The script creates owner-scoped QA runs and defect tables with Row Level Security requiring authenticated access.
4. Add authentication and a server-side/data client in a follow-up development task. The current frontend saves locally and has **no Supabase connection**.
5. Never use a Supabase `service_role` key, database password or payment secrets in the browser, code repository or logs.

## Real Samsung Wallet caveat
Do not claim that the simulated payment flow is Samsung Wallet integration. Actual partner cards, Samsung Pay merchant testing, and NFC contactless flows require Samsung-approved partner credentials, payment-network test infrastructure, appropriate hardware/regions and official testing arrangements. See official Samsung Developer documentation for current eligibility and tooling.
