# Determinismo y reproducibilidad

Bugs de concurrencia que "a veces pasan" son los más caros. La idea de frontera es **volver determinista lo no determinista** para poder reproducir y debuggear.

## Herramientas e ideas

- **[hermit](https://github.com/facebookexperimental/hermit)** (Meta) — lanza programas Linux x86_64 en un sandbox herméticamente aislado y convierte comportamiento no determinista en determinista y repetible. Sirve para replay-debugging, artefactos reproducibles y **chaos mode de concurrencia**.
- **[reverie](https://github.com/facebookexperimental/reverie)** (Meta) — framework ergonómico y seguro de intercepción de syscalls en Linux (la base sobre la que se apoyan herramientas como hermit).
- **Controlar el tiempo** — relojes y timers falsos para tests deterministas. En Node: [`@sinonjs/fake-timers`](https://github.com/sinonjs/fake-timers), y los `fakeAsync`/`tick` de Angular.

## Para probar en Node/Angular

Aunque hermit/reverie son nivel SO (y Linux-only), la *idea* es aplicable: inyectar reloj, aleatoriedad y scheduling como dependencias para que los tests sean reproducibles por seed.

## Reading list

- [hermit — deterministic sandbox (Meta)](https://github.com/facebookexperimental/hermit)
- [reverie — syscall interception (Meta)](https://github.com/facebookexperimental/reverie)

## Mini-roadmap

| Idea | Estado | Próximo paso |
|------|--------|--------------|
| Inyección de reloj/azar por seed | 💡 Idea | PoC en un test flaky actual |
| Evaluar hermit para reproducir bugs de concurrencia | 💡 Idea | Ver viabilidad (Linux-only) |
