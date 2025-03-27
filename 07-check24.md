# CHECK24

Perfect cloud use for the right reasons

- no maintenance, no machine setup
- quick infra setup
- high one time computation power need (vCPU)
- short-lived project (8 weeks)
- pay as you go
- uncertain amount of resources

predictable daily traffic pattern

- seasonality with higher traffic
- special events with sudden/short term traffic spikes

## Profis (local service)

- single server deployment
  - 40 cores: high parallelism (peak ~60%)
  - 192 GB RAM: half for caching, half for work (never full)
  - 4 x 512GB ssd (NO PEAK)
- why single server?
  - downsides of distributed systems outweight potential benefits of scaling out
  - based on past operational experience and benchmarks
- tech stack
  - nginx
  - php for backend-for-frontend
  - ruby for backend
  - mysql

## Tippspiel (Prediction Game)

- millions of users
- on-premise 96% cheaper than AWS

## Jahresrueckblick

- mass video rendering
-
