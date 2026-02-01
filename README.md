# 🛒 Order‑Platform API‑Suite  
*Modern API‑Led integration demo (MuleSoft 4.6)*

---

## ✨ Highlights
| Capability | Detail |
|------------|--------|
| **API‑Led Connectivity** | System (Orders, Inventory, Customers) → Process (Orchestration) → Experience (Web/Mobile) |
| **Parallel orchestration** | Scatter‑Gather |
| **Spec‑Driven RAML** | Traits, libraries, datatype fragments with examples |
| **CloudHub Dev Deploy** | All five apps running on 0.1 vCore each — one command CI pipeline |

---

## 🗺 Architecture

![Architecture](https://github.com/hash-5-7-3-2/shop-api/releases/download/mulesoft/api_architecture.png)

---

---

## 🗄 SQL Schema & Sample Data

The file **[`ddl_seed.sql`](https://github.com/hash-5-7-3-2/shop-api/releases/download/mulesoft/ddl_seed.sql)** creates the three tables and seeds demo rows.

```bash
mysql -u root -p demo_db < docs/ddl_seed.sql
```

---

## 🏷 License  

MIT
