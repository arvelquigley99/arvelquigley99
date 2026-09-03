## Aveline Quigley

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white) ![Location](https://img.shields.io/badge/Manchester-UK-555555?style=flat)

Backend engineer in Manchester. I build Go services that sit in front of Postgres
and push the slow work onto a queue, and I have a strong preference for boring
systems that never page anyone at 3am.

Most of the job is unglamorous. Getting the schema right before there is data in
it, keeping transactions short, making retries idempotent, deleting the endpoint
nobody has called since 2023. The interesting part of backend work is usually the
part users never see.

### Stack

Day to day:

- **Go** — HTTP services, queue workers, the occasional small CLI
- **PostgreSQL** — schema design, query plans, migrations that can be rolled back
- **Redis / NATS** — job queues, rate limits, distributed locks
- **Docker, systemd, Terraform** for the layer underneath

Comfortable enough with:

- Python for one-off scripts and data repair
- SQLite when a service genuinely does not need a database server
- Prometheus and Grafana, plus enough OpenTelemetry to answer "why is p99 bad"

Opinions I hold quietly:

- Foreign keys are not optional
- A queue without a dead-letter path is a data-loss incident waiting for a bad Tuesday
- If a migration cannot be reversed, write down what happens when it fails at 40%
- `SELECT *` in application code will eventually cost you an afternoon

### Projects

**[tickpost](https://github.com/arvelquigley99/tickpost)** — a single-binary CLI
for sticky notes and todos, backed by SQLite. Built it because every note app I
tried wanted an account, and I mostly wanted to type one line and get on with the
deploy.

**[pg-cookbook](https://github.com/arvelquigley99/pg-cookbook)** — the Postgres
snippets I kept re-deriving from scratch: window function patterns, indexing
notes with the query plans that justify them, and a migration template that
survives being run against a live table.

**[go-cloud-skel](https://github.com/arvelquigley99/go-cloud-skel)** — the
minimum viable Go service skeleton. Config from the environment, structured
logging, a health endpoint, and a graceful shutdown that actually drains
in-flight requests instead of pretending to.

None of these are frameworks. They are the files I stopped wanting to rewrite.

### What I am reading about

Currently working through the Postgres 17 release notes properly rather than
skimming them, mostly for the incremental backup and `EXPLAIN` changes. Also
slowly rewriting an internal worker pool now that `errgroup` and structured
concurrency have made most of my old channel gymnastics unnecessary.

### Contact

Open an issue on any of the repositories above, or start a discussion. That is
the fastest way to reach me and it keeps the answer somewhere the next person
can find it.

For anything about a specific repository, please use that repository's issue
tracker rather than emailing. Context lives better next to the code.

---

Manchester, UK · UTC+0/+1 · replies are usually same-day on weekdays and
whenever-I-get-to-it at weekends.
