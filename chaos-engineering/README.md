# Chaos engineering

Inyectar fallas a propósito (latencia, caídas, errores) para validar que el sistema degrada con gracia.

## Herramientas e ideas

- **[Toxiproxy](https://github.com/Shopify/toxiproxy)** (Shopify) — proxy TCP para simular latencia, cortes y condiciones de red malas. Muy cómodo desde tests de Node.
- **[Chaos Toolkit](https://chaostoolkit.org/)** — framework open source, declarativo y extensible (agnóstico de lenguaje vía HTTP).
- **[Pumba](https://github.com/alexei-led/pumba)** — chaos testing para contenedores Docker (matar, pausar, netem).
- **[Chaos Mesh](https://chaos-mesh.org/) / [LitmusChaos](https://litmuschaos.io/)** — chaos engineering nativo de Kubernetes.
- **Gremlin** — plataforma comercial, por si queremos algo más "llave en mano".

## Para probar en Node/Angular

Toxiproxy delante de las dependencias (DB, APIs externas) en tests de integración es probablemente el mejor punto de entrada / mayor ROI.

## Reading list

_(Sumá acá posts, charlas y casos de estudio.)_

## Mini-roadmap

| Idea | Estado | Próximo paso |
|------|--------|--------------|
| Toxiproxy en tests de integración | 💡 Idea | PoC con una dependencia externa |
