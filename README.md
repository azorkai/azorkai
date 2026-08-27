<div align="center">

# Emirhan Güven

**Full Stack Developer** · .NET 8 · React / Next.js · PostgreSQL

[eguven.dev](https://eguven.dev) · [LinkedIn](https://www.linkedin.com/in/eguvendev/) · [contact@eguven.dev](mailto:contact@eguven.dev)

</div>

---

I build and run production SaaS on my own infrastructure: backend, frontend, database and
deployment. Most of my work is a single operator carrying a system end to end: designing the
schema, writing the API, shipping the UI, and keeping it alive on a server I administer myself.

Currently focused on multi-tenant SaaS, third-party API orchestration, and data pipelines that
have to stay fast under real load.

---

## Selected work

### CRMSolid

[crmsolid.com](https://crmsolid.com)

Omnichannel CRM and outreach platform. Sole developer.

Five services behind Traefik on Docker: a **.NET 8** API (EF Core + PostgreSQL, Redis, SignalR),
a **Next.js 15 / React 19** panel with its own design system, a landing site, a health monitor,
and a **.NET 9 / Photino** desktop agent. Deployed from GitHub Actions with tests as a gate.

A few parts I'd point at in an interview:

- **A 1.79M-row business catalogue built with DuckDB over Overture Maps parquet on S3.**
  Querying the remote parquet directly did not stream: 2.5 GB of RAM and zero rows after
  fifteen minutes. Splitting it into a country download joined province by province brought the
  same query from **277 seconds to 15 milliseconds**. Along the way: Overture ships 109 province
  rows for Türkiye rather than 81, and real company names contain lone surrogates that abort an
  Npgsql binary `COPY` unless they are sanitised first.
- **An MCP server** exposing the CRM's tools and prompts to LLM clients, with published
  `.NET` and Node SDKs.
- **516 unit tests** over the parts that actually break: rate limiting and flood-wait backoff,
  outreach safety, email bounce detection, and agent routing.
- Payments and billing through LemonSqueezy and WeePay; integrations for ikas, WordPress and Zapier.

It is a modular monolith, not microservices. One deployable API with a few separate
services around it. For a single maintainer that was the cheaper correct answer, and I can explain where
I'd split it if the team grew.

### NerioPanel

Multi-tenant white-label platform.

Resellers host branded panels on their own domains from a shared database with row-level
security. Custom DNS orchestration over PowerDNS and Nginx handles automatic SSL and routing,
and the React frontend injects tenant branding at runtime from the request host.

### [huawei-matebook-m1080-linux-audio](https://github.com/azorkai/huawei-matebook-m1080-linux-audio)

Kernel patches that bring up speaker output on the Huawei MateBook HVY-WXX9 (AMD Renoir with an
ES8316 codec the mainline driver does not wire correctly). DKMS packaged, GPL-2.0.

---

## Stack

| | |
| :--- | :--- |
| **Backend** | C#, .NET 8, ASP.NET Core, Entity Framework Core, LINQ, SignalR, Python |
| **Frontend** | TypeScript, React 19, Next.js 15, Tailwind CSS, Vite |
| **Data** | PostgreSQL, MySQL, Redis, DuckDB, SQLite |
| **Infrastructure** | Docker, Traefik, Nginx, GitHub Actions, Let's Encrypt, Linux |
| **Practice** | REST APIs, multi-tenancy, OOP, SOLID, NUnit, structured logging |

---

<div align="center">
<sub>Most of my day-to-day work lives in private product repositories.</sub>
</div>
