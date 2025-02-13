# Kotlin Multiplatform

To configure a Kotlin Multiplatform project, add the kobold-api library as a dependency to your platform sources but add the ksp processor in the following manner:

```Kotlin
dependencies {
    kspCommonMainMetadata(libs.kobold.ksp)
    add("kspWasmJs", libs.kobold.ksp)
    add("kspJvm", libs.kobold.ksp)

}

```

Add this to the bottom of your build.gradle outside the `kotlin {}` section.  Refer to KSP Documentation for KMP for more.