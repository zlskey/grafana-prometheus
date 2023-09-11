# Prometheus + Grafana

Docker compose configuration for running [Prometheus](https://prometheus.io) and [Grafana](https://grafana.com) with [node_exporter](https://github.com/prometheus/node_exporter) and [cadvisor](https://github.com/google/cadvisor) for metrics collection.

Grafana dashboard will be secured with [traefik](https://traefik.io) basic auth.

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Traefik](https://traefik.io) (you can use my boilerplate [from here](https://github.com/zlskey/traefik-boilerplate))

### Installing and Running

1. Clone the repo

   ```sh
   git clone https://github.com/zlskey/grafana-prometheus.git
   ```

1. Move into the project directory

   ```sh
   cd grafana-prometheus
   ```

1. Copy the `.env.example` file to `.env` and update the values

   ```sh
   cp .env.example .env
   ```

1. Run docker-compose

   ```sh
   docker-compose up --build -d
   ```

    Your grafana dashboard should be available at `https://grafana.your_domain.com`

1. Login to grafana with the default credentials

   ```sh
   username: admin
   password: admin
   ```

1. Set up a new data source

   - Click on the gear icon on the left sidebar
   - Click on `Add data source`
   - Select `Prometheus` from the list
   - Set the URL to `http://prometheus:9090`
   - Click on `Save & Test`
