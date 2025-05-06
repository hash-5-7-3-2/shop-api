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

## 🔗 API Endpoints (Dev)

| API | CloudHub URL | RAML |
|-----|--------------|------|
| Experience | `https://shop-experience-api-awuj9z.5sc6y6-3.usa-e2.cloudhub.io/shop/` | [`raml`](https://anypoint.mulesoft.com/exchange/portals/na-1108/b0b97105-d2a1-4e8e-a560-1560ca4d6660/shop-experience-api/minor/1.0/console/summary/) |
| Process    | `https://order-process-api-7c56my.5sc6y6-1.usa-e2.cloudhub.io/api/`    | [`raml`](https://anypoint.mulesoft.com/exchange/portals/na-1108/b0b97105-d2a1-4e8e-a560-1560ca4d6660/order-process-api/minor/1.0/console/summary/) |
| Orders     | `https://order-system-api-7c56my.5sc6y6-3.usa-e2.cloudhub.io/api/`| [`raml`](https://anypoint.mulesoft.com/exchange/portals/na-1108/b0b97105-d2a1-4e8e-a560-1560ca4d6660/orders-system-api/minor/1.0/console/summary/) |
| Inventory  | `https://inventory-system-api-7c56my.5sc6y6-3.usa-e2.cloudhub.io/api/`| [`raml`](https://anypoint.mulesoft.com/exchange/portals/na-1108/b0b97105-d2a1-4e8e-a560-1560ca4d6660/inventory-system-api/minor/1.0/console/summary/) |
| Customers  | `https://customer-system-api-7c56my.5sc6y6-3.usa-e2.cloudhub.io/api/`| [`raml`](https://anypoint.mulesoft.com/exchange/portals/na-1108/b0b97105-d2a1-4e8e-a560-1560ca4d6660/customer-system-api/minor/1.0/console/summary/) |

---

## 🗄 SQL Schema & Sample Data

The file **[`ddl_seed.sql`](https://github.com/hash-5-7-3-2/shop-api/releases/download/mulesoft/ddl_seed.sql)** creates the three tables and seeds demo rows.

```bash
mysql -u root -p demo_db < docs/ddl_seed.sql
```

---

## 🏷 License  

MIT
