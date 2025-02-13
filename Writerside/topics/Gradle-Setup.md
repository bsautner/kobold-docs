# Gradle Setup

![Maven Central Version](https://img.shields.io/maven-central/v/io.github.bsautner.kobold/kobold-api)

Kobold uses [Kotlin Symbol Processing](https://kotlinlang.org/docs/ksp-quickstart.html) to generate source code based on interfaces and annotations you use from the Kobold API. 

Code is deposited in your project build directory under `/build/generated/ksp`

It's important that the version of KSP matches your version of Kotlin.  You should also add the Serializer plugin here.
 
### Add the KSP Plugin:

```Kotlin
plugins {
    id("com.google.devtools.ksp") 
    id("org.jetbrains.kotlin.plugin.serialization")
}
```

Next, add the required KSP arguments. Setting the project name will be used during code generation. 

For example if you have multiple modules "Foo" and "Bar", your AutoRouter class will be named "FooAutoRouter" and "BarAutoRouter" and you can add both to your ktor server.

```Kotlin
ksp {
	ksp {
		arg("output-dir",  project.layout.buildDirectory.get().asFile.absolutePath + "/generated/ksp")
		arg("project", project.name)

	}
	
}

```

Finally add the dependencies for Kobold KSP and API:

```Kotlin
depencencies {
	api("io.github.bsautner:kobold-api:kobold_version")
	ksp("io.github.bsautner:kobold-ksp:kobold_version")

}

```

Try running your build with `gradlew clean build --info | grep kobold` to see code generation logs.  