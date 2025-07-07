# Suricata Stack - Ambiente de Segurança com Suricata, ELK e Grafana

Este projeto contém uma stack modular para monitoramento de tráfego de rede e segurança utilizando:

- **Suricata**: IDS/IPS para análise de pacotes e detecção de intrusão
- **Elasticsearch + Kibana**: Armazenamento e visualização dos eventos do Suricata
- **Filebeat**: Agente para envio de logs do Suricata para Elasticsearch
- **Grafana**: Dashboards personalizados para visualização dos dados de tráfego e segurança

---

## Visão Geral

Este ambiente é ideal para quem quer montar uma plataforma de análise de segurança de rede com ferramentas open source, usando containers Docker para fácil implantação.

---

## Pré-requisitos

- Máquina Linux com Docker e Docker Compose instalados
- Acesso SSH à máquina para configurar e executar os containers
- Repositório clonado ou arquivos baixados para o diretório de trabalho

---

## Instruções para rodar o ambiente

1. Clone o repositório (se ainda não tiver clonado):

```bash
git clone https://github.com/ranflerR/suricata-stack.git
cd suricata-stack
2. Inicie os containers com Docker Compose:

```bash
docker compose up -d
```

3. Acesse as interfaces web:

- **Grafana**: [http://localhost:3000](http://localhost:3000)  
  - Usuário padrão: `admin`  
  - Senha padrão: `admin` (troque ao primeiro acesso)

- **Kibana**: [http://localhost:5601](http://localhost:5601)

> Os dashboards do Grafana já estão configurados e importados automaticamente via provisioning.

---

## 🗂️ Estrutura do Projeto

suricata-stack/
├── docker-compose.yml
├── suricata/
│   └── suricata.yaml        # Config do Suricata
├── filebeat/
│   └── filebeat.yml         # Config do Filebeat
├── grafana/
│   └── provisioning/
│       ├── datasources/
│       │   └── datasource.yml
│       └── dashboards/
│           └── dashboard.json


---

## 🛠️ Comandos Úteis

- Verificar status dos containers:

```bash
docker compose ps
```

- Visualizar logs do Suricata:

```bash
docker logs -f suricata
```

- Parar os containers:

```bash
docker compose down
```

---

## 📄 Licença

Este projeto está licenciado sob a licença MIT — veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 📬 Contato

Para dúvidas ou sugestões, abra uma issue neste repositório ou entre em contato:

**Isaac Ranfler** — [iranfler@gmail.com](mailto:iranfler@gmail.com)
