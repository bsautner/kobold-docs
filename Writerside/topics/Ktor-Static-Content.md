# Ktor Static Content

You can add static content to your ktor route like this by hand: 

```Kotlin
 routing {
    staticFiles("/", File("build/dist/wasmJs/productionExecutable")) {
      default("index.html")
    }
  }
  ```

Adding a Kobold to your code will generate the same thing:

```Kotlin
@KoboldStatic("build/dist/wasmJs/productionExecutable") @Resource("/")
class StaticRoute() : KStatic
```

This example shows mapping the KMP Wasm output to the `/` path which is all you need to run a Compose web app.