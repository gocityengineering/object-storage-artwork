flowchart TD
  Z(( ))
  M[/Metrics/]

  subgraph "Prometheus chart"
  P[(Prometheus)]
  G[Grafana]
  T[Thanos sidecar]
  end

  subgraph "Thanos chart"
  Q[Thanos Query]
  F[Thanos Query Frontend]
  end

  Z --> M
  B[(Thanos bucket)]
  E[Expiration policy]
  B --- E
  P --- T
  G -->|data source Prometheus|P
  T -->|write|B
  Q -->|read|B
  F -->|pull|Q
  G -->|data source Thanos|Q
  P -->|scrape|M
