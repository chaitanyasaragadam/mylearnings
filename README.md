# My Learnings

Engineering knowledge base — deep-dive technical documentation, interactive guides, and architecture references across the ServiceNow platform.

## 📚 Content

### Service Catalog
- **Module Overview** — directory structure, design patterns, order flow
- **Core Domain** — Catalog, Category, CatalogItem, Cart, Request, OrderGuide, Pricing
- **Valve Pipeline** — ProducerValve 5-step chain, CompositeProducer, Script Evaluators, Wizard
- **Variables System** — Runtime models, MRVS persistence, Rhino bridge
- **Cache & Infrastructure** — TypeSafeCacheManager, DB Listeners, Metrics, UI Policy
- **Processors & APIs** — GraphQL, DataLookup, Scoped APIs (CartJS, CatalogItemJS)
- **Builder & Templates** — Catalog Builder LCS algorithm, ExecutionPlan DAG, ATF
- **Interactive Guide** — 5 scenarios × 35 steps with real instance screenshots

## 🚀 GitHub Pages

Served from `docs/` folder. Browse at: `https://chaitanya-saragadam.github.io/mylearnings/`

## 🛠 Local Preview

```bash
cd docs
python3 -m http.server 8080
# open http://localhost:8080
```
