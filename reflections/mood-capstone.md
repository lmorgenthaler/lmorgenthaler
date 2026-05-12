# MōōD — Senior Capstone Project

**Course:** CMPT 390 — Senior Capstone
**Live site:** https://moodla.vercel.app
**Poster:** [mood-poster.pdf](../mood-poster.pdf)

## Demo

<!--
  TO EMBED THE VIDEO:
  1. Open this file on github.com and click the pencil icon to edit.
  2. Drag MōōD Demo Video.mp4 from your Desktop directly into the editor.
  3. GitHub will upload it (~75 MB; 100 MB cap) and insert a link like:
       https://github.com/user-attachments/assets/<uuid>
  4. Replace the line below with the URL GitHub inserts. A bare URL on its own
     line auto-renders as a playable video on the rendered README page.
-->

<!-- PASTE GITHUB-ATTACHMENT VIDEO URL HERE -->

## Reflective Summary

MōōD is the senior capstone project I designed and built to address a real gap in the way people shop independent fashion boutiques: 65% of consumers say they wish they shopped local more, but cannot easily discover what nearby stores actually carry. MōōD is a hyperlocal discovery platform that ingests product-level inventory from independent boutiques and surfaces it through a geospatially-indexed, style-first browsing experience on web and mobile. The system is two-sided — a consumer-facing map and product browser, plus an analytics dashboard for the boutique owners themselves. The production deployment currently covers 29 onboarded Los Angeles boutiques and roughly 33,000 real products, refreshed daily through an automated ingestion pipeline. Technically it spans a Next.js 16 / React 19 / Tailwind v4 frontend on Vercel, a FastAPI + async SQLAlchemy backend on Railway, a PostgreSQL 17 database with the PostGIS extension on Supabase (with row-level security across nine tables), a Streamlit analytics dashboard, and a Sentry-monitored deployment pipeline with a documented rollback playbook. The most demanding engineering pieces were a five-tier category normalization pipeline that resolves 149 raw Shopify `product_type` values into a coherent style taxonomy that holds across stores, dual ingestion paths (public `/products.json` scraping for prospects plus OAuth Admin API access for partners), and an audit-driven verification methodology in which scripts like `audit_search_fidelity.py` run against the live database to catch the kind of data-quality bugs that unit tests cannot see.

I chose MōōD as the centerpiece of my portfolio because it is the project where I had to act as the full owner of a real, deployed system — product strategy, architecture, implementation, infrastructure, observability, and the operational realities of running something other people actually use. That ownership is what made it the most direct exercise of the Computer Science learning goals of system-level understanding (PostGIS indexing, async I/O, RLS policies, edge-cache invalidation), software design (separating ingestion, normalization, and serving so the taxonomy could be iterated without breaking the API), and effective problem solving (e.g., diagnosing the Sentry source-map upload failure under Turbopack, or reconciling Shopify's inconsistent `product_type` field into a usable taxonomy). It also pushed me on the Westminster goals of Critical Thinking — repeatedly making judgment calls about scope, data trust, and what was worth shipping versus deferring — Creativity, in the design of a style-first rather than search-first browsing model, and Communication, both in writing the capstone report and in explaining the system to cofounders and faculty who pushed back hard on assumptions about synthetic data.

## Learning Goals Addressed

- **Computer Science:** system-level understanding of the computer; software design; problem solving
- **Westminster:** Critical Thinking; Creativity; Communication
