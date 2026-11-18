# cumbre

> **Frontier Engineering** — brainstorming y roadmap para el desarrollo de aplicaciones.

Este repo es un espacio vivo para explorar **ingeniería de frontera**: técnicas, herramientas e ideas que todavía no son parte de nuestro día a día, pero que podrían subir la vara en **confiabilidad, performance y velocidad de desarrollo**.

No es un repo de producción. Es un lugar para **pensar en voz alta**, dejar referencias, prototipar y decidir qué vale la pena llevar a nuestros proyectos reales.

Nuestro stack base es **Node** y **Angular**, así que priorizamos lo que aplica ahí — pero **no es una restricción fuerte**: si una idea viene de Zig, Rust o lo que sea, igual nos interesa.

---

## Cómo usamos este repo

1. **Brainstorming** → ideas sueltas, links, preguntas abiertas. Todo vale.
2. **Exploración** → cuando una idea engancha, abrimos una nota/spike con más detalle (qué es, por qué nos importa, cómo lo probaríamos en Node/Angular).
3. **Roadmap** → lo que decidimos empujar hacia nuestros proyectos reales pasa al roadmap.

El repo está **organizado por temática**. Cada carpeta es una línea de exploración con su propio `README` (herramientas, reading list y mini-roadmap). Dentro de cada tema podés dejar notas de brainstorming, spikes con código o resúmenes de referencias.

```
cumbre/
├── README.md                          # este archivo: índice + roadmap global
├── testing-y-correctness/             # PBT, swarm, model-based, mutation, DST
├── determinismo-y-reproducibilidad/   # hermit, reverie, control de tiempo/azar
├── chaos-engineering/                 # inyección de fallas, Toxiproxy, chaos mesh
└── load-y-performance/                # k6, Artillery, autocannon, profiling
```

---

## Temáticas

| Tema | De qué va |
|------|-----------|
| [Testing y correctness](./testing-y-correctness/) | Encontrar bugs antes que producción: property-based, swarm, model-based, mutation y deterministic simulation testing. |
| [Determinismo y reproducibilidad](./determinismo-y-reproducibilidad/) | Volver determinista lo no determinista para reproducir y debuggear bugs de concurrencia. |
| [Chaos engineering](./chaos-engineering/) | Inyectar fallas a propósito (latencia, caídas, errores) y validar que el sistema degrada con gracia. |
| [Load & performance](./load-y-performance/) | Entender el comportamiento bajo carga antes de que lo haga producción. |

---

## Roadmap global

Estado de cada idea a medida que avanza de brainstorming → exploración → adopción.

| Idea | Tema | Estado | Próximo paso |
|------|------|--------|--------------|
| `fast-check` en lógica pura | Testing y correctness | 💡 Idea | Spike sobre un reducer/validador real |
| Swarm testing sobre estructuras propias | Testing y correctness | 💡 Idea | Resumir patrón y ver dónde aplica |
| Mutation testing con Stryker | Testing y correctness | 💡 Idea | Correr sobre un módulo chico |
| Inyección de reloj/azar por seed | Determinismo | 💡 Idea | PoC en un test flaky actual |
| Toxiproxy en tests de integración | Chaos engineering | 💡 Idea | PoC con una dependencia externa |
| k6 para APIs de Node | Load & performance | 💡 Idea | Script base + baseline de un endpoint |

> Leyenda: 💡 Idea · 🔬 Explorando · ✅ Adoptado · ❌ Descartado

---

## Contribuir

- Toda idea es bienvenida, por más cruda que esté.
- Un link + dos líneas de "por qué me parece interesante" ya es un gran aporte.
- Ubicá tu aporte en la carpeta de la temática que corresponda.
- Si algo se probó y no convenció, lo documentamos igual (❌ Descartado) — saber qué *no* sirve también es valioso.
