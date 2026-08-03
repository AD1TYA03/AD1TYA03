<div align="center">

<img src="./assets/banner.svg" width="100%" alt="Aditya Kumar Singh — Backend Engineer · AI Engineer" />

<br><br>

<a href="https://ad1tya.vercel.app"><img src="https://img.shields.io/badge/Portfolio-0B1220?style=for-the-badge&logo=vercel&logoColor=22D3EE&labelColor=0B1220" /></a> <a href="https://linkedin.com/in/adi1tya"><img src="https://img.shields.io/badge/LinkedIn-0B1220?style=for-the-badge&logo=linkedin&logoColor=22D3EE&labelColor=0B1220" /></a> <a href="mailto:saaditya17@gmail.com"><img src="https://img.shields.io/badge/Email-0B1220?style=for-the-badge&logo=gmail&logoColor=22D3EE&labelColor=0B1220" /></a>

<br><br>

<img src="https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&weight=500&size=15&pause=1600&color=22D3EE&center=true&vCenter=true&width=620&height=26&lines=credit+decisioning+%2B+payments+for+12%2B+NBFCs;multi-agent+LLM+systems+at+P%26G+scale;ONDC+%2F+Beckn+%C2%B7+LangGraph+%C2%B7+FastAPI+%C2%B7+Azure" alt="" />

</div>

I build the backend for money movement — and the intelligence layer on top of it. Currently at **Tranzita Systems**, where I own credit decisioning and payments for a digital lending marketplace, and the observability layer for a multi-agent LLM assistant running at **Procter &amp; Gamble** scale.

<br>

## Stack

<div align="center">
<img src="https://skillicons.dev/icons?i=python,ts,js,nodejs,fastapi,express,postgres,mongodb,firebase,gcp,azure,docker,githubactions,react,nextjs,tailwind&theme=dark&perline=8" />
</div>

<br>

<div align="center">

`LangGraph` &nbsp;`LangChain` &nbsp;`RAG` &nbsp;`Azure OpenAI` &nbsp;`Gemini` &nbsp;`Arize AX` &nbsp;`OpenTelemetry` &nbsp;`MCP`

`ONDC / Beckn` &nbsp;`Razorpay` &nbsp;`PhonePe` &nbsp;`Cashfree` &nbsp;`Stripe` &nbsp;`CIBIL` &nbsp;`Experian`

</div>

<br>

## Experience

**Tranzita Systems** — Software Engineer, Backend &amp; AI &nbsp;·&nbsp; <sub>June 2025 – Present · Lucknow</sub>

<table>
<tr>
<td width="50%" valign="top">

**Samridhya** · Digital Lending Marketplace

- Loan aggregator backend for **12+ NBFCs** — offer aggregation, ranking, de-duplication
- **ONDC** buyer app on the **Beckn protocol**, end to end
- AI credit analyser over CIBIL / Experian / Digitap bureau data
- **Spendly AI** — multi-agent financial assistant on Gemini
- Razorpay, PhonePe and Cashfree integrations

</td>
<td width="50%" valign="top">

**Procter &amp; Gamble** · "Digital Colleague"

- **LangGraph** multi-agent HR assistant on FastAPI + Azure OpenAI, serving P&amp;G globally
- Own **LLM observability** end to end — Arize AX + OpenTelemetry tracing and dashboards
- **RAG** over Azure AI Search with a live-traffic evaluation layer
- Conversation persistence on a **PostgreSQL LangGraph checkpointer**

</td>
</tr>
</table>

<br>

## Architecture

<sub>How the P&amp;G "Digital Colleague" assistant fits together — the system I own observability for.</sub>

```mermaid
flowchart LR
    U(["User"]) --> API["FastAPI<br/>Gateway"]
    API --> RT{"LangGraph<br/>Router"}

    RT --> A1["HR Policy<br/>Agent"]
    RT --> A2["Benefits<br/>Agent"]
    RT --> A3["Service Desk<br/>Agent"]

    A1 --> RAG["RAG Retrieval<br/>Azure AI Search"]
    A2 --> RAG
    A3 --> RAG
    RAG --> LLM["Azure OpenAI"]

    RT <--> CP[("PostgreSQL<br/>Checkpointer")]
    LLM -.-> OBS["Arize AX + OpenTelemetry<br/>traces · evals · dashboards"]
    RAG -.-> OBS
    RT -.-> OBS

    classDef edge fill:#0B1220,stroke:#22D3EE,stroke-width:1.5px,color:#E2E8F0
    classDef agent fill:#0E1A2B,stroke:#2DD4BF,stroke-width:1.5px,color:#E2E8F0
    classDef obs fill:#0E1A2B,stroke:#8B5CF6,stroke-width:1.5px,color:#E2E8F0
    class U,API,RT,CP edge
    class A1,A2,A3,RAG,LLM agent
    class OBS obs
```

<details>
<summary><b>How a request actually flows</b></summary>

<br>

1. **Ingress** — request hits the FastAPI gateway; the session is rehydrated from the PostgreSQL LangGraph checkpointer, so chat history survives restarts.
2. **Routing** — the LangGraph router resolves intent and dispatches to the right specialist agent. Ambiguous requests were the subject of a research spike on **LLM agent disambiguation**.
3. **Retrieval** — the agent queries the RAG pipeline over Azure AI Search; retrieved context is scored for **relevance and groundedness on live traffic**.
4. **Generation** — Azure OpenAI produces the response, which is checkpointed back to Postgres.
5. **Observability** — every hop emits OpenTelemetry spans into Arize AX, feeding production dashboards for **agent success rate and latency**.

</details>

<br>

## Selected Work

<table>
<tr>
<td width="50%" valign="top">

**BLIS** · Study Hub Booking Marketplace

Seat-level inventory, subscriptions and QR check-in on a serverless backend. Four-tier RBAC and server-side payment verification. Programmatic SEO drove **500K+ impressions** in three months.

<sub>`Next.js` `Node.js` `Firebase` `Cashfree`</sub>

<a href="https://libraryinseconds.com"><b>libraryinseconds.com&nbsp;→</b></a>

</td>
<td width="50%" valign="top">

**New Life** · AI Fitness App

Play Store app with a Gemini vision pipeline that estimates nutrition from meal photos, plus Apple HealthKit and Android Health Connect sync.

<sub>`React Native` `Expo` `TypeScript` `Gemini`</sub>

<a href="https://ad1tya.vercel.app"><b>ad1tya.vercel.app&nbsp;→</b></a>

</td>
</tr>
</table>

<div align="center">
<sub>
Also on GitHub &nbsp;·&nbsp;
<a href="https://github.com/AD1TYA03/ravana_ai">ravana_ai</a> &nbsp;·&nbsp;
<a href="https://github.com/AD1TYA03/autobot-coldmailer">autobot-coldmailer</a> &nbsp;·&nbsp;
<a href="https://github.com/AD1TYA03/NoteCrypt">NoteCrypt</a> &nbsp;·&nbsp;
<a href="https://github.com/AD1TYA03/cut-tracker-app">cut-tracker-app</a>
</sub>
</div>

<br>

## Education

**B.Tech, Computer Science and Engineering** — SRMCEM, Lucknow &nbsp;·&nbsp; CGPA 8.2/10 &nbsp;·&nbsp; May 2025

<br>

<div align="center">

<sub>Open to backend &amp; AI engineering roles &nbsp;·&nbsp;
<a href="mailto:saaditya17@gmail.com">saaditya17@gmail.com</a></sub>

<br><br>

<img src="https://komarev.com/ghpvc/?username=AD1TYA03&style=flat-square&color=22D3EE&label=profile+views" alt="" />

</div>
