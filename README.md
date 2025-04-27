---

# 🐳✨ Kafka Cluster in Docker (KRaft Mode) — Ready to Fly! 🚀

Welcome to your **production-ready Kafka cluster**, running **without ZooKeeper**, powered by **KRaft mode** — all nicely wrapped inside **Docker Compose** containers.  
(Yes, it's as cute and powerful as it sounds! 🐥🔥)

---

## 📦 What's Inside?

- 🛠 **Kafka 3-node cluster** (bitnami/kafka images)
- 🏢 **KRaft mode** (no more ZooKeeper babysitting 🍼)
- 🌐 **External access** (`29092`, `29093`, `29094`) for apps running **inside** or **outside** Docker
- 🎛 **Kafka UI** at `http://localhost:8080` to peek into your topics and messages
- 💪 **Healthchecks** to make sure brokers are alive before connecting
- 🧹 **Resource limits** to avoid eating your whole machine
- 📄 **Simple `.env` config** to set your external IP if needed

---

## 🚀 Quick Start

```bash
# 1. Clone the repo
git clone <your-repo-url>
cd kafka-cluster

# 2. (Optional) Create a .env file
echo "HOST_ADDRESS=192.168.1.100" > .env

# 3. Spin up the cluster
docker compose up -d

# 4. Access the Kafka UI
http://localhost:8080

# 5. Connect your apps!
# Bootstrap servers:
#   - 192.168.1.100:29092
#   - 192.168.1.100:29093
#   - 192.168.1.100:29094
```

✨ *Now your Kafka is purring like a happy kitten.* 🐈

---

## 📋 Requirements

- Docker Engine >= 20.10
- Docker Compose V2 (plugin built into Docker)
- (Optional) `.env` file with your `HOST_ADDRESS` if you’re not on Mac/Windows

---

## 🛠 Services

| Service     | Port | Description                      |
|-------------|------|----------------------------------|
| kafka-1     | 29092 | External access to broker 1     |
| kafka-2     | 29093 | External access to broker 2     |
| kafka-3     | 29094 | External access to broker 3     |
| kafka-ui    | 8080  | Web UI for Kafka management     |

---

## 🧹 Cleanup

When you're done playing:

```bash
docker compose down
```
(*don't worry, the cute brokers will come back when you need them 🐣*)

---

## 📖 Notes

- `kafka-1-data`, `kafka-2-data`, and `kafka-3-data` are volume-mounted for data persistence.
- `.gitignore` makes sure your local Kafka data won't pollute your Git history.
- This setup uses **bitnami/kafka** latest stable image — updated regularly.
- External connectivity via `host.docker.internal` (for Mac/Windows) or your local IP for Linux.

---

## ☁️ Future Upgrades?

- 🛡️ Add SSL/SASL security
- 📈 Add monitoring stack (Prometheus, Grafana)
- ♻️ Automate cluster scaling
- 🔥 KRaft Raft snapshots

---

## 🐣 Final Words

Kafka is scary?  
**Not anymore.**  
Now it’s just a fluffy bird carrying your messages safely across your apps. 🐥💬

**Enjoy building awesome event-driven apps!** ✨

---
