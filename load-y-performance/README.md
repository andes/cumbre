# Load & performance

Entender cómo se comporta el sistema bajo carga antes de que lo haga producción.

## Herramientas e ideas

- **[k6](https://k6.io/)** (Grafana) — scripting en JavaScript, excelente DX, ideal para nuestro stack.
- **[Artillery](https://www.artillery.io/)** — nativo de Node, escenarios en YAML/JS.
- **[autocannon](https://github.com/mcollina/autocannon)** — benchmarking HTTP rápido, escrito en Node.
- **[Clinic.js](https://clinicjs.org/)** — diagnóstico de performance de Node (flamegraphs, event loop, etc.).
- **[Gatling](https://gatling.io/)** / **[wrk2](https://github.com/giltene/wrk2)** — alternativas potentes fuera del ecosistema JS.

## Para probar en Node/Angular

k6 para APIs de Node y Clinic.js para profiling del event loop cuando aparezca un cuello de botella.

## Reading list

_(Sumá acá posts, charlas y casos de estudio.)_

## Mini-roadmap

| Idea | Estado | Próximo paso |
|------|--------|--------------|
| k6 para APIs de Node | 💡 Idea | Script base + baseline de un endpoint |
| Clinic.js para profiling de event loop | 💡 Idea | Probar en un endpoint lento conocido |
