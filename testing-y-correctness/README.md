# Testing y correctness

El norte: **encontrar bugs antes que producción**, especialmente los de concurrencia y estados raros que no aparecen en tests de ejemplo.

## Técnicas e ideas

- **Property-based testing (PBT)** — en vez de escribir casos uno por uno, describís propiedades que siempre deben cumplirse y la herramienta genera cientos de entradas. En JS/TS: [`fast-check`](https://github.com/dubzzz/fast-check).
- **Swarm testing** — en vez de muestrear todas las operaciones con igual probabilidad, primero elegís al azar un *subconjunto* de features y sesgás la distribución. Descubre combinaciones raras que el muestreo uniforme nunca genera.
- **Model-based testing** — correr el sistema real contra un modelo simple ("oráculo") y verificar que se comporten igual bajo cualquier secuencia de operaciones.
- **Mutation testing** — medir si nuestros tests realmente atrapan bugs introduciendo mutaciones en el código. En JS/TS: [`Stryker`](https://stryker-mutator.io/).
- **Deterministic Simulation Testing (DST)** — correr todo el sistema (red, disco, scheduler) sobre un reloj y una fuente de aleatoriedad controlados, de forma 100% reproducible a partir de una seed. Lo que hacen FoundationDB y TigerBeetle.

## Para probar en Node/Angular

Empezar con `fast-check` sobre lógica pura (reducers, validadores, utils, state management de Angular) y agregar `Stryker` para medir la calidad de los tests.

## Reading list

- [Swarm Testing Data Structures — TigerBeetle](https://tigerbeetle.com/blog/2025-04-23-swarm-testing-data-structures/)

### Notas: Swarm Testing (TigerBeetle)

- **PBT + modelo**: corré las mismas operaciones contra la estructura real y contra un modelo simple, y verificá que coincidan bajo cualquier secuencia.
- **Reflección para cobertura de API**: derivar las operaciones a testear directamente de la API pública hace que agregar un método nuevo sin testearlo rompa la compilación/test ("la API pública está testeada" pasa a ser una propiedad).
- **Ojo con la distribución**: muestrear uniforme no da inputs interesantes (ej: para binary search, el caso difícil es un array con todos los elementos iguales, que el random uniforme casi nunca genera).
- **La idea central de swarm**: *muestreá las probabilidades mismas* — elegí al azar un subconjunto de operaciones y sus pesos por cada corrida. Así explorás estados extremos (ej: colas muy largas) que una distribución fija nunca alcanza.

## Mini-roadmap

| Idea | Estado | Próximo paso |
|------|--------|--------------|
| `fast-check` en lógica pura | 💡 Idea | Spike sobre un reducer/validador real |
| Swarm testing sobre estructuras propias | 💡 Idea | Resumir patrón y ver dónde aplica |
| Mutation testing con Stryker | 💡 Idea | Correr sobre un módulo chico |
