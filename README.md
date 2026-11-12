# Awesome-SaaS-MRR-ARR-Analytics-Dashboard

# Awesome SaaS MRR / ARR Analytics Dashboard

> A curated list of top SaaS MRR / ARR Analytics Dashboard platforms — both SaaS/Hosted commercial solutions and open-source alternatives for tracking recurring revenue, churn, and subscription health.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [ChartMogul](#chartmogul)
  - [Baremetrics](#baremetrics)
  - [ProfitWell Metrics](#profitwell-metrics)
  - [Stripe Sigma](#stripe-sigma)
  - [Chargebee SaaS Metrics Dashboard](#chargebee-saas-metrics-dashboard)
  - [FirstOfficer](#firstofficer)
  - [Databox](#databox)
  - [Geckoboard](#geckoboard)
- [Open-Source Software](#-open-source-software)
  - [stripe-pulse](#stripe-pulse)
  - [saas-metrics](#saas-metrics)
  - [ChurnLens](#churnlens)
  - [SaaSDashboard (bhattsaurya16)](#saasdashboard-bhattsaurya16)
  - [cashier-saas-metrics (Laravel)](#cashier-saas-metrics-laravel)
  - [profitable (Ruby)](#profitable-ruby)
  - [Basalt Dashboard](#basalt-dashboard)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted SaaS MRR / ARR Analytics Dashboard platforms. These are not open-source but are included as reference points for feature comparison.

### ChartMogul
**Type:** Subscription analytics and CRM with standardized SaaS metrics
ChartMogul connects to billing systems and consolidates subscription revenue, product usage, and marketing data into one platform, standardizing how metrics are calculated so every team works from the same numbers. Built-in reports cover MRR movements, churn, customer lifetime value, cohort retention, and more, with custom dashboards and the ability to send metrics to Slack, HubSpot, or data warehouses like Snowflake and BigQuery. It also functions as a CRM, giving sales and success teams a revenue-aware view of customers. Pricing scales with tracked revenue rather than seats.

### Baremetrics
**Type:** Subscription analytics with payment recovery add-ons
Baremetrics tracks over 28 subscription metrics including MRR, ARR, churn, upgrades, and downgrades, priced on tracked revenue rather than per seat. The free tier covers up to $180K ARR, with paid plans scaling to $409/month for larger businesses. Optional add-ons include **Payment Recovery** ($129/month or 10% of recovered revenue) and **Cancellation Insights** ($129/month) for churn feedback collection. The platform is known for its clean dashboards and accessible pricing for early-stage SaaS [citation:2].

### ProfitWell Metrics
**Type:** Free subscription analytics with benchmarking
ProfitWell Metrics is **free forever, regardless of business size**, offering growth, revenue, retention, and churn trends, unit economics, cohorts, and benchmarks from 15,000+ subscription companies. Setup is quick (5 minutes), with native integrations and APIs, enrichment via Clearbit and FullContact, and a mobile app with intelligent alerting. Paid add-ons include Retain (churn recovery), Recognized (revenue recognition), and Price Intelligently (pricing strategy). The free tier makes it uniquely accessible for SaaS businesses at any stage.

### Stripe Sigma
**Type:** SQL-based analytics layer within Stripe
Stripe Sigma is a SQL-powered analytics layer built into the Stripe Dashboard, enabling custom queries against live payment and billing data. It includes pre-built templates for common SaaS questions (MRR trends, active subscriptions, churned customers, failed payments) and an **AI Assistant** that generates SQL from plain English. Sigma allows unlimited customization without fixed dashboards, with a 30-day free trial before paid subscription. **Trade-off:** Requires SQL knowledge for non-template queries, and it is limited to Stripe data only.

### Chargebee SaaS Metrics Dashboard
**Type:** Billing-native subscription analytics and reporting
Chargebee's Analytics module provides 360° visibility into subscription health, with reports covering MRR movements, churn, trial conversion, deferred revenue, and custom cohort analysis. The **Reports Explorer** provides instant access to predefined reports from acquisition to churn, while custom reports can be built without code using Chargebee's data sources. Churn alerts notify teams when rates exceed thresholds, and trial analytics track conversion from free to paid.

### FirstOfficer
**Type:** Stripe-centric SaaS metrics with FinOps dashboard
FirstOfficer is the original reporting tool for startups, now offering free subscription metrics (MRR, churn, LTV) alongside a paid FinOps dashboard [citation:3]. It is Stripe-centric, with integrations for Recurly, PayPal, ProfitWell, Plaid, Sage, QuickBooks, and Xero. The platform has processed 1B+ data points over 10 years with 10K+ connections [citation:3]. **Note:** Under new ownership since 2020, it is now a free metrics tool with a small FinOps dashboard run by a very small team, and it lacks recovery, cancellation, or serious forecasting tooling [citation:6]. Pricing for the paid tier starts at $29/month for 250 customers [citation:12].

### Databox
**Type:** Business dashboard and reporting platform
Databox connects to hundreds of data sources (including Stripe, HubSpot, and Google Analytics) to build customizable dashboards and reports. It is a general-purpose business analytics platform rather than a dedicated SaaS metrics tool, but it is commonly used by SaaS teams to visualize MRR and churn alongside other KPIs.

### Geckoboard
**Type:** Real-time KPI dashboard for teams
Geckoboard provides real-time dashboards that pull from various data sources, designed to be displayed on office TVs for team visibility. It supports Stripe and other SaaS tools, making it useful for keeping MRR and churn visible to the whole team.

---

## 🟩 Open-Source Software

Self-hosted, community-driven SaaS MRR / ARR Analytics tools. The open-source ecosystem spans **CLI-driven metric calculators**, **library-based metric engines**, and **full dashboard applications**.

### stripe-pulse
**Stack:** Node.js / TypeScript | **License:** Open Source (npm)
stripe-pulse is a **CLI tool that calculates MRR, ARR, churn, LTV, NRR, Quick Ratio, and MRR movements directly from your Stripe subscriptions** — no dashboard, no monthly fee, no data exports [citation:2]. It addresses the gap that Stripe has no MRR endpoint, while Baremetrics costs $129/mo and ChartMogul starts at $199/mo [citation:2]. Install via `npx stripe-pulse` (no installation) or globally. Commands include `mrr`, `arr`, `churn`, `nrr`, `quick-ratio`, `movements`, and a full `dashboard` that combines all metrics. **Output modes** include human-readable terminal output, JSON (automatic when piped), CSV, Markdown tables, and `--chart` for MRR trend lines and waterfall charts [citation:2]. Supports multi-account profiles for managing multiple Stripe accounts.  
**Best for:** Developers and founders wanting instant Stripe metrics from the command line without paying for a SaaS dashboard, particularly those comfortable with CLI workflows.

### saas-metrics
**Stack:** Python / Excel | **License:** Open Source (PyPI)
saas-metrics is an open reference implementation for computing SaaS revenue metrics from a raw billing export, with **written, tested definitions** for every metric [citation:13]. Key features include a **revenue waterfall exact to the cent** (New, Reactivation, Expansion, Contraction, Churn), NRR/GRR/logo retention, quick ratio, ARR, cohort triangles, and an **Excel workbook where every metric is a live formula you can audit**, with a Checks tab proving it matches the engine [citation:13]. It handles **service-period spreading** for annual/multi-month invoices, correcting the common error of counting invoices in the month billed (on a sample export, this reduced churn events from 214 to 106) [citation:13]. Reads Stripe, Chargebee, ERP, or spreadsheet exports with column mapping. Pre-flight checks block errors and warn on issues like periods with no billing [citation:13].  
**Best for:** Finance teams and developers wanting auditable, transparent SaaS metrics from their own billing data, with Excel output for stakeholder review and rigorous metric definitions.

### ChurnLens
**Stack:** Python / Docker | **License:** Source-available (COCL v1.0)
ChurnLens is a self-hosted tool that calculates MRR, customer churn rate, and LTV from a CSV file listing subscription sign-ups, upgrades, cancellations, and plan changes . It produces month-by-month breakdowns of revenue growth or shrinkage, running entirely on your own computer or server with no account, third-party service, or monthly fee . Single-purpose and scriptable, it outputs in table, JSON, or SARIF formats and can gate CI on findings . Ports are available in Python, JavaScript, Go, and Rust . **Important licensing note:** It is source-available under the Cognis Open Collaboration License (COCL) v1.0 — free for personal, internal-evaluation, research, and educational use, but **commercial/production use requires a license** .  
**Best for:** Founders and finance teams wanting a simple, self-hosted CSV-based metric calculator without a SaaS subscription, accepting source-available licensing with commercial restrictions.

### SaaSDashboard (bhattsaurya16)
**Stack:** Python / Streamlit / Gemini AI | **License:** Open Source (per GitHub)
SaaSDashboard is an AI-powered analytics dashboard for SaaS customer data, offering churn, MRR, cohort retention, revenue loss, and quant forecasts [citation:7]. It supports flexible data input (default CSV, file upload of CSV/Excel, or SQL database query) and includes a generic dataset explorer for non-SaaS schemas [citation:7]. **Gemini AI insights** generate executive summaries, risks, opportunities, and action plans [citation:7]. Deploys via Streamlit Community Cloud, Render, or Docker.  
**Best for:** Teams wanting a ready-to-run Streamlit dashboard with AI-generated insights from their CSV or database data, particularly those comfortable with Python and Google Gemini.

### cashier-saas-metrics (Laravel)
**Stack:** PHP / Laravel | **License:** Open Source (Packagist)
cashier-saas-metrics is a comprehensive SaaS metrics analyzer for Laravel that tracks MRR, churn rate, LTV, ARPU, and cohort analysis with support for Stripe, Paddle, and custom billing providers [citation:11]. Features include pre-built metric calculators, multi-provider support (Stripe, Paddle, LemonSqueezy), a **cache-first architecture** with intelligent caching and automatic invalidation, ready-to-use Blade components for Laravel dashboards, first-class cohort tracking with retention curves, and **auto-recalculation** via background jobs [citation:11]. Usage includes `Metrics::mrr()->calculate()`, `Metrics::churnRate()->calculate()`, and `Metrics::dashboard('this_month')` for all metrics at once [citation:11].  
**Best for:** Laravel developers wanting a drop-in metrics package with a Filament dashboard, accepting the Laravel/Cashier ecosystem requirement.

### profitable (Ruby)
**Stack:** Ruby / Rails | **License:** Open Source (RubyGems)
profitable is a Ruby gem that calculates SaaS metrics like MRR, ARR, churn, LTV, ARPU, total revenue, estimated valuation, and other business metrics for `pay`-powered Rails apps, displaying them in a simple dashboard [citation:1]. It is specifically built for the `pay` payment engine in Rails, making it a natural fit for Rails applications already using that gem. Versions are actively released (v0.6.0 in June 2026) [citation:1].  
**Best for:** Rails developers using the `pay` gem wanting built-in SaaS metrics with a simple dashboard, accepting the specific ecosystem dependency.

### Basalt Dashboard
**Stack:** TypeScript / Zod | **License:** Open Source (npm)
Basalt Dashboard is a TypeScript library that provides `computeBillingMetrics` and `churnRate` functions for calculating MRR, ARR, active/trialing/pastDue counts, and churn from subscription records [citation:4]. It is designed as a **building block** for admin dashboards, with `metricsSection`, `resourceSection`, `auditSection`, and `queueSection` composable components [citation:4]. MRR counts only active subscriptions with numeric prices, dividing annual prices by 12; trials and unknown plans contribute 0 to MRR but count in totals [citation:4].  
**Best for:** TypeScript developers building custom admin dashboards who want a lightweight, testable metrics calculation library rather than a full application.

---

## 📊 Comparison at a Glance

| Software | License | Stack | MRR/ARR | Churn | Dashboard | Self-Hosted | Best For |
|----------|---------|-------|---------|-------|-----------|-------------|----------|
| **ChartMogul** | Proprietary | Cloud | ✅ | ✅ | ✅ | ❌ | Cross-system metric consistency |
| **Baremetrics** | Proprietary | Cloud | ✅ | ✅ | ✅ | ❌ | Accessible core analytics |
| **ProfitWell** | Proprietary | Cloud | ✅ | ✅ | ✅ | ❌ | Free + benchmarks |
| **Stripe Sigma** | Proprietary | Cloud | ✅ SQL | ✅ | ✅ | ❌ | Stripe-native SQL flexibility |
| **FirstOfficer** | Proprietary | Cloud | ✅ | ✅ | ✅ (FinOps) | ❌ | Stripe-centric + FinOps |
| **stripe-pulse** | Open Source | Node.js/CLI | ✅ | ✅ | ✅ (CLI) | ✅ | CLI Stripe metrics |
| **saas-metrics** | Open Source | Python/Excel | ✅ | ✅ | ✅ (Excel) | ✅ | Auditable definitions |
| **ChurnLens** | Source-available | Python | ✅ | ✅ | ✅ | ✅ | CSV-based self-hosted |
| **SaaSDashboard** | Open Source | Streamlit | ✅ | ✅ | ✅ (AI) | ✅ | AI insights from CSV/DB |
| **cashier-saas-metrics** | Open Source | Laravel/PHP | ✅ | ✅ | ✅ (Filament) | ✅ | Laravel developers |
| **profitable** | Open Source | Ruby/Rails | ✅ | ✅ | ✅ | ✅ | `pay` gem Rails apps |
| **Basalt Dashboard** | Open Source | TypeScript | ✅ | ✅ | (Library) | ✅ | Custom TS admin dashboards |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source SaaS MRR / ARR Analytics Dashboard tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source (or clearly note if it is source-available but not OSI-approved, as with ChurnLens). Note that the open-source ecosystem **splits** between **CLI tools for instant Stripe metrics** (stripe-pulse, which explicitly positions itself against Baremetrics' $129/mo and ChartMogul's $199/mo [citation:2]), **auditable metric engines with Excel output** (saas-metrics [citation:13]), **framework-specific packages** (cashier-saas-metrics for Laravel, profitable for Rails `pay`), and **full dashboard applications** (SaaSDashboard with Gemini AI [citation:7]). For teams wanting the fastest path from Stripe to MRR without a subscription, **stripe-pulse** is the most direct option; for finance teams needing auditable definitions and Excel outputs, **saas-metrics** is unmatched; and for Laravel teams, **cashier-saas-metrics** provides the most integrated experience.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
