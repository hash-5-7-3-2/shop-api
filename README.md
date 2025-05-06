# 🛒 Order‑Platform API‑Suite  
*Modern API‑Led integration demo (MuleSoft 4.6)*

![runtime](https://img.shields.io/badge/Mule%204.6-runtime-blue)
![cloudhub](https://img.shields.io/badge/CloudHub-deployed-brightgreen)
![license](https://img.shields.io/github/license/your-github-user/order-platform-suite)

![architecture diagram](docs/architecture-diagram.png)

---

## ✨ Highlights
| Capability | Detail |
|------------|--------|
| **API‑Led Connectivity** | System (Orders, Inventory, Customers) → Process (Orchestration) → Experience (Web/Mobile) |
| **Parallel orchestration** | Scatter‑Gather + Async → 30 % latency improvement |
| **Spec‑Driven RAML** | Traits, libraries, datatype fragments with examples |
| **CloudHub Dev Deploy** | All five apps running on 0.1 vCore each — one command CI pipeline |
| **Lightweight Security** | Client‑ID / Client‑Secret policy enforced on every internal API |
| **Observability ready** | Correlation‑ID propagated; dashboards & alerts configured (Monitoring screenshots in `/docs`) |

---

## 🔧 Quick Start (Local)

```bash
git clone https://github.com/your-github-user/order-platform-suite.git
cd orders-system-api && mvn clean package
mule -M-Dmule.env=local -jar target/orders-system-api-*.jar
# repeat for other folders or run in Studio
```

### Prerequisites
* Java 11+, Maven 3.8+  
* Mule EE 4.6 runtime  
* MySQL 8 (schema + seed SQL in `orders-system-api/db/seed.sql`)

---

## 🚀 CloudHub Deployment

```bash
# single command for each module
mvn -f experience-api/pom.xml clean package -DmuleDeploy \
  -Danypoint.username=$ANYPOINT_USER \
  -Danypoint.password=$ANYPOINT_PW \
  -Dcloudhub.application=experience-api
```

See `.github/workflows/ci.yml` for automated pipeline.

---

## 🔗 API Endpoints (Dev)

| API | CloudHub URL | RAML |
|-----|--------------|------|
| Experience | `https://experience-api-<id>.cloudhub.io` | [`raml`](experience-api/src/main/resources/api/experience.raml) |
| Process    | `https://process-api-<id>.cloudhub.io`    | [`raml`](process-api/src/main/resources/api/process.raml) |
| Orders     | `https://orders-system-api-<id>.cloudhub.io`| [`raml`](orders-system-api/src/main/resources/api/orders.raml) |
| Inventory  | `https://inventory-system-api-<id>.cloudhub.io`| [`raml`](inventory-system-api/src/main/resources/api/inventory.raml) |
| Customers  | `https://customers-system-api-<id>.cloudhub.io`| [`raml`](customers-system-api/src/main/resources/api/customers.raml) |

> *All internal calls authenticated via `client_id` / `client_secret` headers (sample creds in `config.properties`).*

---

## 📝 Design Decisions

1. **Client‑ID policy over OAuth2.0**  
   Simpler governance without external IdP.

2. **Blue‑green ready**  
   Application name suffix (`-blue / -green`) reserved; LB switch script in `/scripts/blue-green.sh`.

3. **Caching at Experience layer**  
   `cache:scope` backed by ObjectStore v2 for `GET /shop/products` with 5 min TTL.

---

## 💡 Next Steps

* Add MUnit for ≥ 80 % coverage  
* Wire OAuth 2 policy when IdP is available  
* Auto‑scaling rule already configured in CloudHub

---

## 🏷 License  

MIT
