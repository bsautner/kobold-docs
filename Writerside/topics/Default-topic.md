[Kobold Github Proper](https://github.com/bsautner/kobold) |  [API Docs](https://bsautner.github.io/kobold/api-docs/) | [Documentation (this repo)](https://bsautner.github.io/kobold-docs)

# Kobold

<img src="kobold.webp" alt="" width="250" height="250"  border-effect="line"/>

Kobold was inspired by a Ktor based project where the architecture inspired code generation based on Kotlin Multiplatform, Jetpack Compose and Ktor Type Safe Routing.

Using [KSP](https://kotlinlang.org/docs/ksp-overview.html) and a provided API, Kobold will generate client and server side components of a full stack Ktor application based on class structure and annotations only.

This results in clean Ktor Routing, Forms and Multiplatform Ktor Clients.

### Status

### Multiplatform Code Generation Status

*In this early stage we are focused on Compose WASM and JVM KtorServer

| Platform            | JVM | WASM | Android | iOS | 
|---------------------|-----|------|---------|-----|
| Ktor Server Routing | ✅   | ❌    | ❌       | ❌   |
| Ktor Client Routing | ❌   | ❌    | ❌       | ❌   |
| Compose Forms       | ❌   | ✅    | ❌       | ❌   |