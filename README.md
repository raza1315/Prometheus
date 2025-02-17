# Prometheus & Grafana Setup using Docker

## Prerequisites
- Create a `prometheus.yml` configuration file in your repository.

## Step 1: Run Prometheus
Run the following command to start Prometheus:
```sh
docker run -d -p 9090:9090 --name=prometheus \
  -v $(pwd)/prometheus.yml:/etc/prometheus/prometheus.yml \
  prom/prometheus
```

- Mounts the local `prometheus.yml` configuration file into the container.
- Uses the official Prometheus Docker image.

## Step 2: Run Grafana
Run the following command to start Grafana:
```sh
docker run -d -p 3000:3000 grafana/grafana
```

## Step 3: Access Grafana
1. Open Grafana in your browser: [http://localhost:3000](http://localhost:3000)
2. Log in with the default credentials:
   - **Username**: `admin`
   - **Password**: `admin`

## Step 4: Import Prometheus Dashboard
1. In Grafana, go to **Dashboards → Import**.
2. Enter the **Dashboard ID: `3662`** (Prometheus 2.0 Stats).
3. Click **Load**.
4. Select **Prometheus** as the data source.
5. Click **Import**.

## Step 5: Verify Setup
- Open Prometheus UI: [http://localhost:9090](http://localhost:9090)
- Open Grafana UI: [http://localhost:3000](http://localhost:3000)
- Check dashboards to ensure Prometheus metrics are visible in Grafana.

