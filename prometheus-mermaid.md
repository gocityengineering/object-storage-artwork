```mermaid
flowchart TD
  
  Z(( ))
  M[/Metrics/]

  subgraph "Prometheus chart"
  P[(Prometheus)]
  G[Grafana]
  end

  Z --> M
  G -->|data source Prometheus|P
  P -->|scrape|M
```
